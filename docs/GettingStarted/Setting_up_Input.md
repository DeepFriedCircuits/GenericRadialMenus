# Setting Up Input

Unreal Engine 4 uses the `PlayerController` class as a mediator of input between players and the game.
While pawns and other actors *can* recieve input, the player controller is the best place for things like menu input and other universal inputs such as pause and play, since they do not
rely on a player pawn and may need to be used in a situation where a pawn doesn't exist. One such scenario would be when the player isn't spawned yet, but some settings must be selected, or the player wants to back out of a match.
So naturally, this is the most convenient place to put the radial menu input.

There are two methods of getting input. Implementing an interface or inheriting from a base class. Both will do the same thing, but inheriting requires only one step.

If you are already fluent in the workings of UE4 and the blueprint system, the steps are these:

**Method 1:**

* Inherit from the **BP_RadialInputPlayerController**

**Method 2:**

* Implement the **IRadialInput** interface in your player controller. Next, implement the "GetJoystickDirection" method.

* Fill out the method with the contents from the
BP_RadialInputPlayerController "GetJoystickDirection" method.

***Important:***
_If you already have a player controller that inherits from another controller,_
_maybe one from another plugin or asset, the interface method may be easier, and more logical._

# Method 1: Inheritance

Open your `PlayerController` blueprint (or to make a new one, see step one of the next method.) and go to class settings.

[![Image from Gyazo](https://i.gyazo.com/d141842adb0c5b447a3fef1c2a5e6119.png)](https://gyazo.com/d141842adb0c5b447a3fef1c2a5e6119.png)

then click parent class option button,

[![Image from Gyazo](https://i.gyazo.com/11d4444147ba6a42f37bf95956c5fb3b.png)](https://gyazo.com/11d4444147ba6a42f37bf95956c5fb3b.png)

and choose `BP_RadialInputPlayerController`. You may have to search to find it, depending on the contents of your project.

[![Image from Gyazo](https://i.gyazo.com/f5e3bc2c1636ad795b73be9a3a344227.png)](https://i.gyazo.com/f5e3bc2c1636ad795b73be9a3a344227.png)

Now make sure your `PlayerController` is being used in your gamemode, and joystick input should now be active for your radial menus!

[How to assign a player controller for use.](../Misc/HowToAssignA_PlayerController.md)

# Method 2: Implementing the IRadialInput Interface

This method will work with any `PlayerController` and makes it possible to add input completely non-destructively to your current class heirarchy.
Interfaces are merely a coding tool to allow you to declare what methods a class will have, allowing other classes to communicate with those functions
without needing to cast to your specific class. It's a great way to handle many different things that may have completely different classes but similar
functions, such as interactable objects.

_If you've never used interfaces before, check out the UE4 documentation here:_ <a href="https://docs.unrealengine.com/en-us/Engine/Blueprints/UserGuide/Types/Interface/UsingInterfaces" target="_blank">Unreal Interface Documentation</a>

### Step 1: Create a PlayerController blueprint

First locate the *Add New* button in the content browser, then select to create a new blueprint class.
[![Image from Gyazo](https://i.gyazo.com/d236a084ae6ff9fe7f6d513a3294f821.png)](https://gyazo.com/d236a084ae6ff9fe7f6d513a3294f821.png)

Then select *PlayerController*. This will create your new player controller class.
[![Image from Gyazo](https://i.gyazo.com/9e671947cbe17664210075d3af46f862.png)](https://gyazo.com/9e671947cbe17664210075d3af46f862.png)

### Step 2: Adding the interface

Once inside your new ***PlayerController*** blueprint, select `Class Settings`.

[![Image from Gyazo](https://i.gyazo.com/d141842adb0c5b447a3fef1c2a5e6119.png)](https://gyazo.com/d141842adb0c5b447a3fef1c2a5e6119.png)

Then go to the interface section, and press the `Add` button,

[![Image from Gyazo](https://i.gyazo.com/0edbe5b02d8f514dda4acfcb865d98f4.png)](https://gyazo.com/0edbe5b02d8f514dda4acfcb865d98f4.png)

Then search and select the `IRadialInput` interface. This will make your PlayerController compatible with the radial menu system.

[![Image from Gyazo](https://i.gyazo.com/2bcbf68fcb6cc5af929065f04d92b331.png)](https://gyazo.com/2bcbf68fcb6cc5af929065f04d92b331.png)

### Step 3: Implementing input functionality

Now that you're PlayerController is implementing the `IRadialInput` interface, it's time to fill in the functionality!

Find the tab marked `My Blueprint` and locate the interface section. Then double click the `GetJoystickDirection` method.

[![Image from Gyazo](https://i.gyazo.com/1e01ebff7d6f5870fa423a71ee06647b.png)](https://gyazo.com/1e01ebff7d6f5870fa423a71ee06647b.png)

Upon opening, you should be greeted with this:

[![Image from Gyazo](https://i.gyazo.com/a2b0d0a46d5cf4dd0e57993c727084e9.png)](https://gyazo.com/a2b0d0a46d5cf4dd0e57993c727084e9.png)

###Note:
***If you don't want to make the nodes yourself, just check out the*** `GetJoystickDirection` ***method on the*** `BP_RadialInputPlayerController` ***class.***
***You can just copy the nodes and paste them into your new function, just make sure you get all of the connections setup as they were from***
***the original version.***


Right click the graph area and search for `thumbstick axis`. This should show the following nodes:

[![Image from Gyazo](https://i.gyazo.com/6f8beed5dde847b234e0c2f3b77c2b31.png)](https://gyazo.com/6f8beed5dde847b234e0c2f3b77c2b31.png)

Add all four nodes and arrange them as seen here:

[![Image from Gyazo](https://i.gyazo.com/c11770b2e5a6a743785e8f16bf3bbdd8.png)](https://gyazo.com/c11770b2e5a6a743785e8f16bf3bbdd8.png)

Now add a switch off of the `Joystick` input of the function,

[![Image from Gyazo](https://i.gyazo.com/1067090720d0c2c51d8aea20a4bb7662.png)](https://gyazo.com/1067090720d0c2c51d8aea20a4bb7662.png)

Now select all four nodes, and set the settings on each nodes to match this:

[![Image from Gyazo](https://i.gyazo.com/47dffe568d2bb4a05d842c532d159936.png)](https://gyazo.com/47dffe568d2bb4a05d842c532d159936.png)

By disabling `Consume Input` we prevent the controller from removing input from the camera and motion controls, and `Execute when Paused` will allow the radial menus
to be used in pause menus.

Now add two `Make Vector2D` nodes, then connect x and y for each stick to their own `Vector2D` x and y inputs. Arrange them like so, making sure to ***multiply the Y axis of the left stick by -1***.
It should look like this once completed:

[![Image from Gyazo](https://i.gyazo.com/4ffd99431caa2da52fea089c8bfb2d03.png)](https://gyazo.com/4ffd99431caa2da52fea089c8bfb2d03.png)

Now your player controller should be ready for use. If you haven't assign the player controller to your game mode yet, now is the time to do so.


[How to assign a player controller for use.](../Misc/HowToAssignA_PlayerController.md)
