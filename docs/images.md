### Images

If Pinterest has taught us anything, it's that images are the lifeblood of the web, and TogetherMap is no exception.  We highly reccommend adding images wherever possible in TM to liven things up a bit, but this is entirely up to the user.  

The easiest way to add images to TM is by clicking the image button on every collection edit or place edit page.  When you click this button, this will open up the image selection dialog that is provided to us by [filepicker.com](https://www.filepicker.com/).  This part should be fairly easy to figure out, but note that filepicker connects you to your account for Box, Dropbox, Facebook, Google Drive, Flickr, Instagram, and Picasa all within this easy-to-use interface.  

Note that this does *not* give us access to your accounts, you simply choose which content you want to move to TM so that you can organize and view it on a map.

### Other Image Sources

**Not to be underestimated is the "web images" option which allows you to quickly do a web search for images and find a picture of a place to add to TM.**

If you already know of an image on the web (or prefer using the Google image search), you can use the "link" option.  

**Also keep in mind that if you go to to TM on mobile, you can use filepicker to upload directly from your phone's camera, which is by far the easiest option available for map based travel diaries.**

## Importing an entire Flickr Album

You can also import an entire album from Flickr into TogetherMap.  Since the concept of a Flickr *album* maps pretty perfectly to the concept of a TogetherMap *collection*, this works quite well.  (Note that Picasa also has albums but they do not publicly release the geotags on the pictures which does not work well for import into TM.)

To import a Flickr collection, simply click "Import" in the left-side menu and look for the text box labeled "Flickr Link."  In this text box, paste the link to your album on Flickr - it will be of the form `https://www.flickr.com/photos/133431672@N05/sets/72157653474631614` but the long strings of characters will be different.  Then click import.  That's all there is to it.  

Every image will now be added to TogetherMap with a marker, and the collection and place pages will work the same as any other collection on TM.  As with any other collection, you can add place names and descriptions, which you can use to annotate your photo collection from Flickr (possibly even easier than you can do so on Flickr). 
Finally, there is one additional feature: under any Flickr collection, after you click to edit the collection, there is a *refresh* button, which when clicked will import any *new* photos that are not present in the current collection.  This allows you to continually add photos to the Flickr album and synchronize to TM without losing any of the edits you've made on TM.

### Setting the permissions correctly on the Flickr Album

Unfortunately there's one caveat.  Although the TM side of an import is utterly trivial, setting up permissions on the Flickr side to make the album public, and to make the geocodes public is slightly less then trivial.  (Note that to use Flickr import in TogetherMap, the album must be public.  If it's private you can still import indidivdual photos using the process described above.)

First, you have to tell Flickr that's it's OK to publicly release the built-in geotags on your photos (made by your mobile phone or possibly your modern digital camera).  These geotags are essential for TM to map the photos (stands to reason).  All these steps happen on Flickr, not on TogetherMap.

* Go to your account (click your image or default image in the upper right hand of the page)
* Click on privacy and permissions along the top (but under the black menu bar)
* Make sure "Hide your EXIF data" is set to "No" and set "Import EXIF location data" to "Yes"

Second, you have to make the images in the album public.  The best way I can find to do this is within Organizr.  Click on the album and then find the link for "Edit in Organizr".  Select all the images, click on "Batch Edit" and "Change Permissions" and set to "Anyone".

I recognize this is a painful process and if any fo these instructions are unclear or need to be updated please let us know so we can make the necessary changes.

