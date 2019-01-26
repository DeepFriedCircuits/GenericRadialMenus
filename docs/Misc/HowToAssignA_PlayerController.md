# How to assign a Custom Player Controller

If you're unsure how to assign a custom player controller, make sure you've got a game mode assigned, and do the following:

Click the `Blueprints` tab on the main toolbar of the level editor.

[![Image from Gyazo](https://i.gyazo.com/775d884c3ba6f723fbcd6aa51f7f807e.png)](https://gyazo.com/775d884c3ba6f723fbcd6aa51f7f807e.png)

Next, mouse over _World Override GameMode -> PlayerController -> Select PlayerController Class -> Select your controller_.

[![Image from Gyazo](https://i.gyazo.com/ae553c6e61e15392182b6ab4dc1f63f8.png)](https://gyazo.com/ae553c6e61e15392182b6ab4dc1f63f8.png)

Another method is inside your custom `GameMode` blueprint. Simply open your `GameMode` blueprint, and inside the details panel, find the `PlayerControllerClass` property. This is where you'll set your player controller.

[![Image from Gyazo](https://i.gyazo.com/8b097cd47f2a2b5c6b61777a9ff51055.png)](https://gyazo.com/8b097cd47f2a2b5c6b61777a9ff51055.png)
