## A Tour of the UI

Most of the basic menu operations happen by clicking the "Hamburger" in the upper left of the navbar.  This pulls out a left-side menu like many mobile sites.  You can then click "Collections" to get access to the list of collections, or "New" for a new colleciton, or "Import" to bring in external shape data.

You also login using the left-hand side menu.  You must be logged in to create or edit content on TM so we can associate your data with your account.  If you're logged in to a private collection, we'll make every effort to keep your data secure (assuming you don't make the collection public).

## The Map View

The map view has a few small widgets which control the map pane.  Along the right hand side is the "sidebar" which fills with content depending on your most recently performed action.  Most of the basemaps use data from [OpenStreetMap](https://www.openstreetmap.org/).

Along the left hand side are the zoom in and zoom out buttons and the geocoding widget.  The geocoder lets you put in an address and when you select a matching address takes you to that location.

## Collection Page

Navigation typically happens by clicking "Collections" from the left-side menu.  You can then browse to collections you own, collections you follow, and other public collections (which are kept in the gallery).  When a collection is clicked, you get up to 100 places in the map view for that collection (the one's closest to the map center), and the sidebar contains a description of the collection.  If there are more than 100 places in the map view where you are, you might need to pan around to load more places.  

If you click the button for "Recent" you will get the most recent comments for the collection (to get recent places, click the sort button and "recent" to sort by the most recent places).

If you have "owner" permissions on the collection, you will be able to edit the collection configuration and set the permissions, which will be explained in the [customization](customization.md) and [permissions](permissions.md) pages respectively.  

If you do *not* own the collection, you will have the option to follow the collection, and if you are already following the collection you will have the option to unfollow the collection.  

The collection page also includes a scrollable list of all the places currently loaded for the collection.  Whenever you mouse over the "card" for a place, that place will be highlighted with a darker color in the map view.  Additionally, if the place is a marker it will bounce to show you which place this "card" represents on the map.  You can also click the location arrow in the upper right hand corner to pan to the place, and click again to zoom in on the place.

## Place Pages

Click on a place, either in the map view or in the place list in the collection view, and you will arrive on the place page.  The place page mainly is to provide the place (pun intended) to have a conversation about the place.  

Below the place description is a list of current comments about this place.  From this page you can also vote the place up or down or edit the place properties, including marker icon, color, and size (small, medium, and large), as well as set a default image for the place.

## Adding Places

If you have place adding permissions for a given collection (which you always have if you created or own the collection), then you will see a toolbar at the bottom left hand corner of the map (you will not see this toolbar if you don't have permissions).  From the bottom, the icons are for delete, edit, marker add, polygon add, and line add.  The last 3 add the main 3 kinds of shapes in any geographic information system and TM is no expection.

TM uses the wonderful library [Leaflet](http://leafletjs.com/) as it's mapping library, and this drawing toolbar is the [Leaflet Draw](https://github.com/Leaflet/Leaflet.draw) widget.  A pretty great blog to understand the breadth of this plugin is provided [here](http://www.d3noob.org/2014/01/using-leafletdraw-plugin-for-leafletjs.html).

But we think its use is pretty simple.  The shape creation buttons use tooltips to show how to use them.  As a quick reminder, click the last point twice to finish drawing a line, and click the first point a second time to close a polygon.

If you click the edit button on the toolbar, you now enter a mode where you can drag any marker on the map to a new location, which is always fun but use wisely.  The delete button allows you to remove places from the map with a click.  The should *definitely* be used wisely.  Places can also be deleted by clicking the edit button on the place page and then the delete button.  As a reminder, only owners of the collection or the creators of each place will have the permissions to delete each place.

## Adding Places Redux

There are two other super easy ways to add places.  If you're on the desktop, just right click and use the context menu to add a place.  Or you can click on "Settings" in the left-side menu (or just Ctrl-d) to turn double clicking into marker adding (as opposed to its default function, which is to zoom in).

## Adding Places on Mobile

If you're on mobile, this all gets simpler, but less powerful.  On mobile, when you have place adding permissions you can only add markers, and there will be a single button on the map with the marker icon to add a place.  Once you click this button, a marker will "float" in the middle of the map; move the map until the marker is in the appropriate location and click the save button (or the "x" to cancel adding the marker).
