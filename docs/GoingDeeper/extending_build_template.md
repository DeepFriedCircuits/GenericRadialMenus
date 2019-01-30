#Extending the MultiMenu Template

The `MultiMenuTemplate` is an example of 2 radial menus in each other. The first ring selects the category. Once the category is chosen,
the first ring shrinks down and the second ring expands and fills with the data for that category.
Replacing the data with your own can work two ways:

* Filling in some data tables,
* By replacing some functions

To start with, the best option is to make a copy of the `MultiMenuTemplate` class
and put the duplicate into another folder outside the asset package folders.

[![Image from Gyazo](https://i.gyazo.com/a6cf859f9203ae4691728b1eef33d0ed.png)](https://gyazo.com/a6cf859f9203ae4691728b1eef33d0ed.png)

For debugging purposes, we can add the widget to the viewport inside the level script blueprint.

[![Image from Gyazo](https://i.gyazo.com/10147d9fdbacd665336a4154919289ea.png)](https://gyazo.com/10147d9fdbacd665336a4154919289ea)

With this in place, on `BeginPlay` the widget will be made and useable. This will
allow us to quickly test to make sure our Blueprint logic is working.

In the situation where having a table of categories and each category containing a "subtable" works for your
needs, then very little is needed to get this menu working for you.

For this method, we'll need to make a new table of categories.

[![Image from Gyazo](https://i.gyazo.com/3abfdb3a8e35a091c6cea5eb28d16905.png)](https://gyazo.com/3abfdb3a8e35a091c6cea5eb28d16905)

From the dropdown, select `PTCategory` and hit *ok*.

[![Image from Gyazo](https://i.gyazo.com/58dcdef3b69a7a4e4559f7cd88c45e28.png)](https://gyazo.com/58dcdef3b69a7a4e4559f7cd88c45e28)

Now open your newly created table and start adding your categories. To add a new entry to
the table, press the *+* on the far left.

[![Image from Gyazo](https://i.gyazo.com/1169c5df71a470153ba60aace89cb6bc.png)](https://gyazo.com/1169c5df71a470153ba60aace89cb6bc)

For this example, I'll be making an player battle chat selector. So I'll add a
*Team*, *Objective*, and *Banter* category. For the example, random engine
icons will be used. The result looks like this:

[![Image from Gyazo](https://i.gyazo.com/5966ce3f9d0e01a204e0d206462c0638.png)](https://gyazo.com/5966ce3f9d0e01a204e0d206462c0638)

Next we need to assign the actual table to the new `MultiMenu` we made. To do so,
open your duplicate `MultiMenu` class, and find the class defaults. The simplest way
to do this in a widget is to click the root of the hierarchy on the left,

[![Image from Gyazo](https://i.gyazo.com/894bfeb8795b7dbcfe97a55e6d41b8bf.png)](https://gyazo.com/894bfeb8795b7dbcfe97a55e6d41b8bf)

then find the details panel on the right. Inside the details panel, you'll want to
replace the details category with your new table.

[![Image from Gyazo](https://i.gyazo.com/eed9471c7a3c459dd9c0da3f71cd1b1c.png)](https://gyazo.com/eed9471c7a3c459dd9c0da3f71cd1b1c)

Now your `MultiMenu` should show your categories on the initial menu! In the
next step, we'll cover adding the subitems.
