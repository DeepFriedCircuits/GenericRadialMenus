# Radial Menu Settings

The radial menus have multiple settings for you to tweak and use.

[![Image from Gyazo](https://i.gyazo.com/088467f99d0e8d383af9aa571b86e87b.png)](https://gyazo.com/088467f99d0e8d383af9aa571b86e87b.png)

###Segments

The default number of segments in the radial menu.

###Material Base

What material to use in the radial menu. Check `PieMenus/Materials` for different options.

###Allow Resizing

By setting this to true, the radial menu will add more sections as you add items. This can get a little cramped
if you add too many items.

###Joystick to Use

Which joystick for the menu to listen to.

###Mouse Deadzone

Determines the distance the mouse needs to travel from the center of the screen before registering as input.
This variable doesn't need much changing, but is there for tweaking if necessary.

###Joystick Deadzone

Same as the mouse deadzone, except for the joystick.

###Selection Changed Sound

The sound made when a new section is selected on the menu.
If no sound is desired, set to nothing.

###Auto Rotate for up

If true, will always make the first section on the menu point upwards.
This may not be necessary or even desired, but can be a more logical way for handling input.
For example, a 4 piece menu with this setting would have a section point in each direction:
_up, down, left and right_, making input more intuitive on a controller.

# Advanced settings

###Default Player Index

In the situation where you have supplied no owning parent to the parent widget,
this will be the controller index the menu will use in the `GetPlayerController`
node. For most situations 0 will be all that's needed.
