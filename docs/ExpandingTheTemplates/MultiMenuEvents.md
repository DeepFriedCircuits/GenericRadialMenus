# MultiMenu Template Events

The Multi Menu Template contains the following events:

### SubmenuCommit 
_This event will supply the Category and the sub item selection, and be called once a category and an item is chosen_

The most common way of using this event would be to bind from the blueprint that creates the
widget to a custom event like so:

![](https://gyazo.com/f9336fa06c2acb3f21b13e04511e484d.png)
![](https://gyazo.com/2747bb4da2591dc7c653a2d35e50f86e.png)
_Note: Make sure the table you access here is the same one you set in your copy of the UMG_MultiMenuTemplate_

Use the category parameter to locate the proper table and use the `Sub Item` for the
actual data for gameplay.

### Cancel
_Will be called when the user wants to exit the menu and not make a selection _
