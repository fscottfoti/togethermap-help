## Search

When the user clicks the "Hamburger" and "Search", a search will be performed for places in the map view.  (This is an option when deploying TM so might not occur in all TM instances.)  At the time of this writing, search will search places in any collection for which the user has read permissions, but will only search the "name" attribute.  Changing search to be more general is one of the planned tasks for improving TM.

## Settings

The following settings can be configured in TM:

* the meaning of double clicking the map (as mentined in the [Adding Places Redux](basics.md)) can be changed from "zoom in" to "add place" and back.

* the "pan to place" setting can be enabled which will pan to each place as you hover the mouse over the "card" in the Collection page.  Normally the place will be highlighted, but this enables you to quickly pan to the place if it's not shown in the current map view.

## Email updates

At this time, email updates are sent as nightly digest emails.  An email will arrive in your inbox each morning with the 10 most recent places and comments which occurred in each of the collections you own or follow.

If no updates were made in the previous 24 hours on your collections, no email will be sent.  In this way, emails are used to alert the user whenever there has been activity on one of their collections.

Additional configuration options for email will be implemented and made available in the future.