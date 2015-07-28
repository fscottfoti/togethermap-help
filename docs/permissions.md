## Accessing Permissions

Permissions are accessed by going to the collection page and clicking on the button for permissions.  Only collection creators and those with owner permissions can change permissions on a collection.

## Kinds of Permissions

There are 4 kinds of permissions in TM.

* owners
* place writers (placers for short)
* post writers (posters for short)
* readers

Owners can edit collection attributes and set permissions, place writers can add places to a collection, post writers cannot add places but can make new topics, comments and vote, and readers can only browse a collection but cannot add or edit any content.

Note that these permissions are hierarchical, i.e. all place writers are post writers and all post writers are readers and all owners have all available permissions.

## Making a Collection Private

After clicking the permissions button, you will see 4 buttons, one for each of the 4 kinds of permissions.  Click each button to see the permission settings for that type of permission.

First you will see a button to make a collection "private."  By default, when created all collections are public place writable (which implies public readable and public post writable).  To give someone permission, the collection first has to be private for that permission.  Click on private to do this.

In this case private collections are hierarchical in the opposite order, i.e. post private collections are all place private and read private collections are all post private (this happens automatically).

## Configurating a Private Collection

Once you've made a collection private you will see widgets to configure permissions.

At the top you will see a list of users that have that permission, each with a remove button which would revoke that permission.

Note: public owner collections do not exist - you must give ownership explicitely.

Giving permissions roughly works the same as Google Docs - i.e. send links to people that to whom you want to give the permission.  To get the link that bestows a given kind of permission, just click the "link" button and the link will be copied to the clipboard for you to, most likely, paste into an email to send to a collaborator.  

Additionally you can click the "generate" button if you think someone has access to the link that you did not intend, and when you click generate all previous links will no longer give access to the bearers of that link.  

Finally, at the bottom will be a button to make the collection "public" again.

## Accepting Permissions

When a user clicks on the link that is copied above (to provide a given permission), they will be taken to a page in TM which provides the description of the collection, allows the user to login, at which point they can click on an "accept" button which bestows the permission.  When a permission is accepted the collection is automatically followed for that user.

## Login Not Required for Read Access

As a small caveat, read access by default does not require the user to login and "accept" permissions.  This is similar to Google Docs, where anyone with a link can view.  

In TM though, for a person to edit a place or make a post to a private collection, they must be logged in and "accept" the permissions.  

An additional button is provided for read permissions to change the default to require that a user be logged in and accept read permission (in this way the user can be tracked and the permission revoked, although this is not common).