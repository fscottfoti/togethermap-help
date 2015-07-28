## A Tour of the UI

The navbar across the top is similar to a file menu in most desktop applications.  "Go" contains links to create a new collection, search or browse collections, import new data, or read this very documentation.

Next to that is the "Mine" drop down which contains the collections you created, and next to that is the "Followed" drop down which contains - you guessed it - the collections you've followed.

Along the right hand side is where you login to the website.  You must be logged to create or edit content on TM so we can associate your data with your account, which is true of any online service.  If you're logged in to a private collection, your data is as secure as your online bank.

## The Map View

The map view has a few small widgets which control the map pane.  Along the right hand side is the "sidebar" which fills with content depending on your most recently performed action.  In the upper right hand corner is the layer switcher, which lets you change basemaps (e.g. to aerial photographs and a few others).  Most of the basemaps use data from [OpenStreetMap](https://www.openstreetmap.org/).

Along the left hand side are the zoom in and zoom out buttons, the share widget, the geocoding widget and the location widget.  In reverse order, the location widget takes you to where you are in the world, the geocoder lets you put in an address and when you select a matching address takes you to that location, and the share widget lets you share on social media, and importantly, gives you the html snippet to embed a TogetherMap on your website.

## Embedding

Let's give that a header.  The share widget contains the html snippet to embed a TogetherMap on your website.  Please do!

## Collection Page

Navigation typically happens by clicking on a collection, either in the "Mine" list, the "Followed" list, or via the "Browse" link.  When a collection is clicked, you get up to 100 places in the map view for that collection, and the sidebar contains a description of the collection.  If there are more than 100 places in the map view where you are, you might need to zoom in to load more places.  TM will let you know if you're looking at all possible places with the statement "All places in visible area are available."  

If you click the button for "Recent" you will get the most recent places, posts and comments for the collection.  You may also up or down vote the collection here.  If you have "owner" permissions on the collection, you will be able to edit the collection configuration and set the permissions, which will be explained in the [customization](customization.md) and [permissions](permissions.md) pages respectively.  

If you do *not* own the collection, you will have the option to follow the collection, and if you are already following the collection you will have the option to unfollow the collection.  

The collection page also includes a scrollable list of all the places currently loaded for the collection.  Whenever you mouse over the "card" for a place, if the place is a marker it will bounce to show you which place this "card" represents on the map.  You can also click the location arrow in the upper right hand corner to pan to the place, and click again to zoom in on the place.

## Place and Post Pages

Click on a place, either in the map view or in the place list in the collection view, and you will arrive on the place page.  The place page mainly is to provide the place (pun intended) to have a conversation about the place.  

Below the place description is a list of current posts about this place.  Create a new topic or respond by commenting on another topic.  To comment click on the "Read More" button to arrive at the post page, or click "Post New Topic" to - you guessed it - post a new topic.

From this page you can also vote the place up or down, copy it to another collection, or edit the place properties, including marker icon, color, and size (small, medium, and large).

## Adding Places

If you have place adding permissions for a given collection (which you always have if you created or own the collection), then you will see a toolbar at the bottom left hand corner of the map.  From the bottom, the icons are for delete, edit, marker add, polygon add, and line add.  The last 3 add the main 3 kinds of shapes in any spatial information system and TM is no expection.

TM uses the wonderful library [Leaflet](http://leafletjs.com/) as it's mapping library, and this drawing toolbar is the [Leaflet Draw](https://github.com/Leaflet/Leaflet.draw) widget.  A pretty great blog to understand the breadth of this plugin is provided [here](http://www.d3noob.org/2014/01/using-leafletdraw-plugin-for-leafletjs.html).

But we think its use is pretty simple.  The shape creation buttons use tooltips to show how to use them.  As a quick reminder, click the last point twice to finish drawing a line, and click the first point a second time to close a polygon.

If you click the edit button, you now enter a mode where you can drag any marker on the map to a new location, which is always fun but use wisely.  The delete button allows you to remove places from the map with a click.  The should *definitely* be used wisely.  Places can also be deleted by clicking the edit button on the place page and then the delete button.  As a reminder, only owners of the collection or the creators of each place will have the permissions to delete each place.

## Adding Places Redux

There are two other super easy ways to add places.  If you're on the desktop, just right click and use the context menu to add a place.  Or you can click on "Go" and "Settings" (or just Ctrl-d) to turn double clicking into marker adding (as opposed to its default function, which is to zoom in).
