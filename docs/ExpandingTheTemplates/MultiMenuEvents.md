# MultiMenu Template Events

When the template confirms a selection, it fires an events called:

### SubmenuCommit 
_This event will supply the Category and the sub item selection._

The most common way of using this event would be to bind from the blueprint that creates the
widget to a custom event like so:

![](https://gyazo.com/2747bb4da2591dc7c653a2d35e50f86e.png)
_Note: Make sure the table you access here is the same one you set in your copy of the UMG_MultiMenuTemplate_

Use the category parameter to locate the proper table and use the `Sub Item` for the
actual data for gameplay.
