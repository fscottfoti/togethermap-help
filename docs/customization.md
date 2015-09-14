## Customization

All the customization discussed here will be made on the collection settings page, which can be reached by clicking the "Edit" icon on the collection page.  The "Edit" icon will only be avialable if you have owner permissions on the collection.  Once you're on the "Edit" page you will need to click the down arrow at the button of the page to get to the expert settings discussed here.

As a word of warning, a modest amount of programming is requried to customize the templates in TogetherMap.  This will likely be configurable in the interface in the future, but programming is the only completely general solution that takes advantage of some wonderful open source tools that have been made available on the web.  As you will soon see, the basics can be done with no previous programming knowledge, and with only the basics you can do some very powerful things in TM.

## Shapefiles

Shapefiles are the lifeblood of GIS.  Although TM isn't GIS, we can start with shapefiles because shapefiles are the most common way to 1) define a shape and 2) associate attributes with a shape.  That's good because we *will* want to associate attribtues with a shape.  In our example, let's say we have a set of shapes, each of which has a name, description, and image url.

## JSON

Instead of shapefiles, the vernacular of the web is JSON.  JSON is essentially a Javascript object which is a key value dictionary that is human readable.  For our example, you need only deal with one object at a time.  TogetherMap takes care of reading the places from the database, synchronizing updates between users and many other things.  Here is a sample place.

```javascript
{
	shape: [-37.7792, 122.4191],
	name: "San Francisco City Hall",
	description: "This is the City Hall of SF",
	image_url: "http://imgur.com/ABCD"
}
```

## GeoJSON

OK, that's easy enough, but what about the shape arribute?  In fact, there is a whole specification for representing shapes in JSON called [GeoJSON](http://geojson.org/) and this is the preferred way to represent shapes on the web rather than shapefiles.  TM uses GeoJSON.  In practive, you will never, ever have to know how shapes are stored.  TM does this for you.  You only need to know how to turn the attributes into text or into marker themes.

## JSON in TM

Let's imagine a coworker sent you a shapefile and you imported it into TM.  You don't even really know what attributes are in the shapefile.  Worry not.  Once the data is in TM, that is now our problem.  Under the first text area is a button with a "code" icon on it.  Click it and it will give you a formatted sample object from this collection.  One is printed below so that you won't be too worried when you see a place with it's full complexity.  

So what do you need to know about this?  Not as much as you'd think.  The magic is all in the "properties" sub-dictionary, and you will see "properties" come up a lot in TM templates.  "properties" is part of the GeoJSON spec and allows us to conform with existing conventions - this is where all of the attributes go.  There are also some higher level attributes which TM adds, like createDate, updateDate, and creator which might be of some use, but for the most part, everything you need is under "properties".  

Here you see name, image_url, and we'll use "caption" instead of "description."  Note that the "name" attribute on the place is what gets filled in the text box when you edit a place, and the "description" is filled in by the text editor.  The other attributes you can edit when on the place edit page are "icon", "icon_size", and "color".  Note that these correspond to the 5 html form elements that you see on every place edit page.

```javascript
{
  "_id": "7yqXaYKi3ZbaLCemM",
  "geometry": {
    "type": "Point",
    "coordinates": [
      -122.429913,
      37.766286
    ]
  },
  "type": "Feature",
  "bbox": {
    "type": "Point",
    "coordinates": [
      -122.429913,
      37.766286
    ]
  },
  "properties": {
    "description": "",
    "color": "#63d7b2",
    "name": "2175 Market",
    "caption": "Formerly a 76 gas station, 2175 Market will bring new housing units to transit-heavy Market Street. It will include 88 one- and two-bedroom units spread out over six stories. The development will also add 7,300 square feet of ground floor-retail along Market. ",
    "image_url": "http://cdn.cstatic.net/images/gridfs/51f008c6f92ea172190269bf/2175 Market Rendering - Corner.jpg",
    "url": "http://www.2175market.com",
    "address": "2175 Market Street, San Francisco, CA 94114, USA",
    "icon_size": "m",
    "icon": "building"
  },
  "creatorUID": "x2nRy8FNcpG32By4k",
  "creator": "Fletcher Foti",
  "createDate": "2015-06-20T06:19:29.957Z",
  "updateDate": "2015-06-20T06:19:29.957Z",
  "collectionId": "ecGPcWi4XRDvMHLSp"
}  
```

## Templates

Templates are how you turn JSON to HTML.  Your web browser visualizes only HTML but JSON is the data which "backs" the HTML.  For instance, we'll want to format and display the name as a header, the description as normal text, and the image_url as an image.  You can see the actual collection we're trying to create [here](https://togethermap.com/collection/ecGPcWi4XRDvMHLSp).

The first template that we can configure is the "Place Template (for Place Detail)".  This is the template that is used on the place page.  The actual template for the collection above is shown here.  Here we're substituting in the name, url, image_url, and caption properties into a small html snippet.

The name is rendered as header, the url as a link, caption as normal text, and the image url as an image.  It's pretty much that simple.  Note that the double curly braces mean to substitute that attribute as text and the triple curly braces mean that attribute is *already* html and should be rendered as html.

**Keep in mind that each template has a "test" button that allows you to test the template on a randomly chosen place to see what it looks like.**

```html
<h2>{{properties.name}}</h2>

{{#if properties.url}}
<a href="{{properties.url}}" target="_blank">View on Curbed</a>
<br><br>
{{/if}}

{{{properties.caption}}}

<br><br>

<img src="{{properties.image_url}}" style="width: 100%;">
<br><br>
```

That's really all you need to know to make a nicely formatted page, and a place page created by this template is shown below.  If you're an intermediate to advanced web programmer, you should know that these templates are rendered with [handlebarsjs](http://handlebarsjs.com/) which is a very powerful templating library, and everything it can do TM can do.
<br>
<div align="center">
<img src="../img/place.png" style="width: 350px">
</div>
<br>
The user also controls the template for the "Place List" which is the list of places below the collection description, and the one for our sample collection looks like this:

```html
<h4>{{properties.name}}</h4>

{{#if properties.url}}
<a href="{{properties.url}}" target="_blank">View on Curbed</a>
<br><br>
{{/if}}

{{{properties.caption}}}

<br><br>

<img src="{{properties.image_url}}" style="width: 300px;">
<br><br>
```

This is almost the same template as the place detail template except that the name is rendered with a small header (h4 instead of h2) and the image is not as wide to make scrolling easier.

The final template is for the label that pops up when you mouse over a place.  The one for our sample collection looks like this:

```html
<h4>{{properties.name}}</h4>
<img src="{{properties.image_url}}" style="width: 100px;">
<br>
```

Short and sweet.  The popup doesn't have much room, so we display the name and a thumbnail version of the image.  That's it, there's nothing more to it.

## Autoform

Now let's assume your friend didn't send you a shapefile that had shapes and attributes and you need to create that information directly in TM.  We already know how to make the shapes from the discussion on [Adding Places](basics.md).  What's new in this section is how your users can easily enter attributes on TM, which we do this using HTML forms. 

TM does this in a spcial way which uses the [Autoform](http://autoform.meteor.com/) package from the Meteor framework.  Using this package you no longer have to painstakingly write the HTML by hand, you just configure the form with a JSON spec and TM will take care of rendering the form.  

For instance, let's say you want to record the number of residential units (a number), the number of non-residential square feet (another number), and a drop down for "has bike parking" which can take the values of yes, no, and maybe.  No problem.  The code to create that form is shown below, which includes some extra formatting information for how to label each element in the form, and to make sure we don't allow negative numbers for the counts we want to record.  

There's actually quite a bit more configuration that can be done with autoform, and we suggest you go directly to the [autoform playground](http://autoform.meteor.com/quickform) to build your form on their website.  You can then copy the JSON back to the text area on TM and we will add a form on *the edit page* of every place to collect attributes about that place.  These attributes can then be rendered in the HTML templates described above, or the themes described below, or even exported into a shapefile for further analysis outside of TM.

```javascript
{
  residentialUnits: {
    label: "Number of residential units in development:",
    type: "Number",
    min: 0
  },
  nonResidentialSqft: {
    label: "Number of non-res square footage:",
    type: "Number",
    min: 0
  },
  hasBikeParking: {
    type: "String",
    label: "Has bike parking:",
    allowedValues: [
       "Yes", "No", "Don't know"
    ]
  }
}
```
<br>
...which creates the form that looks like this:

![](img/data.png)

...and can be seen in action on [this](https://togethermap.com/collection_edit/fpT5BHZtx9CjnymQN) collection.

## Theming Functions

Now let's say your friend sent you a shapefile with some numbers already entered (probably the old way, using some desktop GIS tool), and these numbers represent new buildings in San Francisco.  The buildings can be office buildings, residential buildings, and can vary in size from just a few townhomes to hundreds and hundreds of upscale condos.  

In fact, with web maps we can change the size of markers, the colors, and the icons, and our goal is to make each building show up on a web map as a marker with a certain "theme" - in other words, we want to map certain attributes in the shapefile to certain traits of the markers.  

We do that in TM with "theming functions" which are next in the collection edit page.  There is a theming function for the icon (the picture that's inside the marker), the marker size, and the color for the marker (click the buttons above the text area to specify each function).  Theming functions are actual Javascript functions so are the only thing that's actual code in TM.  Still, Javascript is a pretty easy language to use so it shouldn't be too challenging to get through the basics.

As an example, we're trying to build the theme shown in the screenshot below.  This is available as a live demo [here](https://togethermap.com/collection_edit/-JiizFSQYiP6dtHLTqV5).  This data is the actual development pipeline provided by the San Francisco Planning Department for late 2012 and early 2013.

![](img/themed.png)

First we specify the icon.  TM uses the Maki icons which are described (and can be searched) [here](https://www.mapbox.com/maki/).  All you have to do to specify the icon is to return the name of one of the icons that's shown at the link above.  In this example, we want to to use the icon for "building" when there are residential units and "commercial" when there are not.

To do this we use the ternary (question mark) operator in Javascript.  Note that in our functions the variable "p" is set to the "properties" dictionary we discussed above (the one that contains the attributes we always care about).  What this code says is that if the attribute "Units" is greater than zero, return the string "building", otherwise return "commercial", and TM takes care of the rest for you.

Two things to remember since this is Javascript.  First, it's very easy to create errors because this is relatively free-form coding, and second, you can open the console in the Chrome browser to see those errors and get a hint as to what you might be doing wrong.  Since this is coding, you won't get it right the first time and will have to hone in on the desired behavior by trial and error.  We promise we will make this easier in the future, but until then I feel confident you can do it!

*Remember that you have to refresh the page in order to re-render the markers, so every change you make in the theming functions you will need to refresh to see the results.*

```javascript
return p.Units > 0 ? "building" : "commercial";
```

Next comes icon size.  This function must return one of the strings 's', 'm', and 'l' for small, medium, and large markers respectively.  Yep, that's all there is to it.  The function below returns 'l' when Units is greater than 80 or when the TotalSqftEstim attribute is greater than 150k.  I think this code should be fairly easy to understand once you understand that "||" means "or" in Javascript.

```javascript
if(p.Units > 80 || p.TotalSqftEstim > 150000) return 'l';
if(p.Units > 30 || p.TotalSqftEstim > 25000) return 'm';
return 's';
```

Next is the icon color function.  This is very similar to the others but returns a color value.  These colors can be hex numbers - you can search Google for a hex "color picker" and use your favorite from the web and just copy the value in here.  It can also return simple colors like "blue", "red", "yellow", etc, but these colors are less nuanced obviously.

This function says, first check if there are no residential units, if so return a blue color.  After that we know that the building is residential, but if it *also* contains commercial (the next line), we return purple.  Then if it's a *large* building return red and otherwise return yellow.  And that's how we choose the colors you see in the image above.

The one thing worth noting on this example is that you can use the `p.Units` notation if the attribute doesn't have weird characters in it, but you have to use `p['WHATEVER']` notation if it does, which is why we have to do `p['Total GSF (Commercial)']`.  Otherwise you should have seen all this before.

```javascript
if(!p.Units) return '544FDB';
if(p['Total GSF (Commercial)'] > 500) return '9D28E0';
return p.Units > 120 ? 'E02850' : 'E0DD28';
```

That's pretty much it.  With the above configuration, you can do pretty much anything in TM - you can record information from your users, you can use that data to theme the map, and you can use the same data to make html templates in the place detail view, the place list view, and the labels.  Please feel free to ask questions - we'd love to help!

## Drop Markers

There are a few other on/off attributes in the collection edit view that will be discussed briefly here.  "Drop markers" can be turned on for an effect that drops the markers from the sky in animated fashion whenever markers are added to the map.  This is a question of taste though, so is user configuratble.

## Turning off the Geoindex

The "geoindex" can also be turned on and off.  The geoindex is the functionality that limits the places that are loaded to only those shown in the map view.  If you had hundreds of thousands of city markers worldwide, you would just want to load the few cities that are in the map view, so this is turned on by default.  If you have less than a hundred places or so, it's usually fine to turn this off, which loads all the places in the collection immediately and can be handy for subsequent responsiveness and also so that all the places are in the list view all the time which is perhaps easier for users to understand on small collections.  At any rate, it's up to the collection owner how they choose to set this.

