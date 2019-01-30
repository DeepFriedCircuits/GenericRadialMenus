#Extending the Build Menu (Part 2)

## Adding Data

For this system to have any use, we're going to add some data to the submenus.
First we'll need to define our data inside a structure:

[![Image from Gyazo](https://i.gyazo.com/d15a672f602de5c04a7a8414d99139d5.png)](https://gyazo.com/d15a672f602de5c04a7a8414d99139d5)

Now, name and open your data structure. Continuing with the battle chat example,
we're going to need a text line to print. Also, for the actual menu, we'll need
a short name and Texture2d icon.

**Import Note:** _regardless of your use case, the `MultiMenu` logic is going to
need an Icon (`Texture2D`) and a `Text` name. If you have these two, the rest will be
up to your for your needs._

[![Image from Gyazo](https://i.gyazo.com/d01dcedce36930728fc23f4bbf089078.png)](https://gyazo.com/d01dcedce36930728fc23f4bbf089078)

Now go to your `MultiMenu` duplicate, and find the `GetItemData` function.

### UNDERCONSTRUCTION
