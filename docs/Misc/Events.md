# Events

The `UMG_RadialMenu` class currently has three events:

###Selection Changed
  Called when the user has highlighted a new index.

###Entered Deadzone
  Called when the user has moved the cursor or joystick to the center (deadzone) of the widget.

###Exited Deadzone
  Called when the user has moved the cursor or joystick far enough from the center to register as input.

These events can easily be bound to inside the UMG editor by clicking the radial menu and finding the *Events* section.

![](https://gyazo.com/e8c13b6ccb62e593e7fa440bc194ca70.png)

Typically, you'd then use the `Selection Changed` event and route it out into another event, or the actually logic to use
that index. For instance, each index represents and item in your inventory list. You would use the `Selection Changed` event
to call SetWeaponIndex function on your player, or maybe event call custom dispatcher event on the widget.
