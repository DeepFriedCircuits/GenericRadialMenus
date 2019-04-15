# Setting up the Build Tables

For the categories to show your custom data, you'll need to first make a table using the `PTCategory` structure.

![](https://gyazo.com/ac84c5e28fc622dc41f2331c2d69b092.png)

Then add your categories, and make a data table for each one, using your custom data structure. Be sure your use the
same structure type for each otherwise the template would need serious modification.

![](https://gyazo.com/6f3e90328c41d7886a327a198e55e50b.png)

Once you've added your categories and tables, you need to set the table to be used by your copy of the `UMG_MultiMenuTemplate`
class. Once the `CategoryTable` is set, the menu should now display your icons.
