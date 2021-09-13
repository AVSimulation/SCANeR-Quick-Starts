# How to? Configure the visual rendering: Advanced

This guide is for advanced configuration of the visual rendering in SCANeR. It follows the guide for [basic configuration of the visual rendering in SCANeR](./HT_configure_visual.md).

## Step 5. Add a mirror

### View port

## Step 6. Multi-display

As mentioned in the *Important considerations* of the [basic guide](./HT_configure_visual.md), it is recommended to use one Visual module per high definition screen.

For a three-display configuration, you are therefore likely to end up with 3 Visual modules, and 3 configuration sections accordingly.

```
[VISUAL_SHOWSIM_MIDDLE]
;[...]
[VISUAL_SHOWSIM_LEFT]
;[...]
[VISUAL_SHOWSIM_RIGHT]
;[...]
```

### Camera position

The camera position by default is the drivers' head position defined in the ego vehicle's properties. It is possible to add a position offset relative to this position:
* *PositionOffset = X Y Z*
* *RotationOffset = H P R*

```
[VISUAL_SHOWSIM:1.1]
PositionOffset			= 0.0 0.0 0.0
RotationOffset			= 0.0 0.0 0.0
;[...]
```

For multi-displays, left and right screens should have a *RotationOffset* in order to match their actual angle in front of the user.
For instance if the FOV of each screen is 30 degrees, rotating the left and right screens by 30 degrees will ensure continuity between the screens:

```
[VISUAL_SHOWSIM_LEFT:1.1]
PositionOffset			= 0.0 0.0 0.0
RotationOffset			= -30.0 0.0 0.0
;[...]
[VISUAL_SHOWSIM_RIGHT:1.1]
PositionOffset			= 0.0 0.0 0.0
RotationOffset			= 30.0 0.0 0.0
;[...]
```

> **Note:** If your goal is to adjust the driver's head position for the middle or only screen, you should change it in the ego vehicle's properties.
> This way you don't have to repeat the offset for all channels.  
> For a single display, the position and rotation offset should remain null in principle.
