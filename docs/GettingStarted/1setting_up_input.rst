================
Setting Up Input
================

Unreal Engine 4 uses PlayerControllers as a mediator of input between player and the game.
While pawns and other actors *can* recieve input, the player controller is the best place for things like menu input and other universal inputs such as pause and play, since they do not
rely on a player pawn and may need to be used in a situation such as the player isn't spawned yet, but some settings must be selected, or the player wants to back out of a match.
So naturally, this is the most convenient place to put the radial menu input.

There are two methods of getting input. Implementing an interface, or inheriting from a base class. Both will do the same thing, but inheriting requires only one step.

# Method 1: Inheritance

Open your `PlayerController` blueprint (or make a new one, see step one of the next method.) and go to class settings.

[![Image from Gyazo](https://i.gyazo.com/d141842adb0c5b447a3fef1c2a5e6119.png)](https://gyazo.com/d141842adb0c5b447a3fef1c2a5e6119)

then click parent class,

[![Image from Gyazo](https://i.gyazo.com/11d4444147ba6a42f37bf95956c5fb3b.png)](https://gyazo.com/11d4444147ba6a42f37bf95956c5fb3b)

and choose `RIPlayerController`.

[![Image from Gyazo](https://i.gyazo.com/c13338f198fc3c96c71d4ae7d5de331d.png)](https://gyazo.com/c13338f198fc3c96c71d4ae7d5de331d)

Now make sure your controller is being used in your gamemode, and joystick input should now be active for your radial menus!

## Step 1: Create a PlayerController blueprint

First locate the *Add New* button in the content browser, then select to create a new blueprint class.
[![Image from Gyazo](https://i.gyazo.com/d236a084ae6ff9fe7f6d513a3294f821.png)](https://gyazo.com/d236a084ae6ff9fe7f6d513a3294f821)

Then select *PlayerController*. This will create your new player controller class.
[![Image from Gyazo](https://i.gyazo.com/9e671947cbe17664210075d3af46f862.png)](https://gyazo.com/9e671947cbe17664210075d3af46f862)

## Step 2: Adding the interface

Once inside your new ***PlayerController*** blueprint, select `Class Settings`.

[![Image from Gyazo](https://i.gyazo.com/d141842adb0c5b447a3fef1c2a5e6119.png)](https://gyazo.com/d141842adb0c5b447a3fef1c2a5e6119)

Then go to the interface section, and press the `Add` button,

[![Image from Gyazo](https://i.gyazo.com/0edbe5b02d8f514dda4acfcb865d98f4.png)](https://gyazo.com/0edbe5b02d8f514dda4acfcb865d98f4)

Then search and select the `IRadialInput` interface. This will make your PlayerController compatible with the radial menu system.

[![Image from Gyazo](https://i.gyazo.com/2bcbf68fcb6cc5af929065f04d92b331.png)](https://gyazo.com/2bcbf68fcb6cc5af929065f04d92b331)

## Step 3: Implementing input functionality

Now that you're PlayerController is implementing the `IRadialInput` interface, it's time to fill in the functionality!

Find the tab marked `My Blueprint` and locate the interface section. Then double click the `GetJoystickDirection` method.

[![Image from Gyazo](https://i.gyazo.com/1e01ebff7d6f5870fa423a71ee06647b.png)](https://gyazo.com/1e01ebff7d6f5870fa423a71ee06647b)

Upon opening, you should be greeted with this:

[![Image from Gyazo](https://i.gyazo.com/a2b0d0a46d5cf4dd0e57993c727084e9.png)](https://gyazo.com/a2b0d0a46d5cf4dd0e57993c727084e9)

Right click the graph area and search for `thumbstick axis`. This should show the following nodes:

[![Image from Gyazo](https://i.gyazo.com/6f8beed5dde847b234e0c2f3b77c2b31.png)](https://gyazo.com/6f8beed5dde847b234e0c2f3b77c2b31)

Add all four nodes and arrange them as seen here:

[![Image from Gyazo](https://i.gyazo.com/c11770b2e5a6a743785e8f16bf3bbdd8.png)](https://gyazo.com/c11770b2e5a6a743785e8f16bf3bbdd8)

Now add a switch off of the `Joystick` input of the function,

[![Image from Gyazo](https://i.gyazo.com/1067090720d0c2c51d8aea20a4bb7662.png)](https://gyazo.com/1067090720d0c2c51d8aea20a4bb7662)

Now select all four nodes, and set the settings on each nodes to match this:

[![Image from Gyazo](https://i.gyazo.com/47dffe568d2bb4a05d842c532d159936.png)](https://gyazo.com/47dffe568d2bb4a05d842c532d159936)

By disabling `Consume Input` we prevent the controller from removing input from the camera and motion controls, and `Execute when Paused` will allow the radial menus 
to be used in pause menus.
and a `Make Vector2D` off of the return node.

[![Image from Gyazo](https://i.gyazo.com/1067090720d0c2c51d8aea20a4bb7662.png)](https://gyazo.com/1067090720d0c2c51d8aea20a4bb7662)

Then connect x and y for each stick to their own `Vector2D` and arrange them like so, making sure to ***multiply the Y axis of the left stick by -1***.
It should look like this once completed:

[![Image from Gyazo](https://i.gyazo.com/4ffd99431caa2da52fea089c8bfb2d03.png)](https://gyazo.com/4ffd99431caa2da52fea089c8bfb2d03)