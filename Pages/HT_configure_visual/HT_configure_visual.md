# How to? Configure the visual rendering

SCANeR studio is able to render the simulated scene on many display configuration, including single or multiple screens, projection system or head-mounted display.

This guide helps you configure the visual rendering for your display system.

* Step 1. Add a new visual module
* Step 2. Initiate the configuration
* Step 3. View geometry
* Step 4. Quality VS performance
* Step 5. Add a mirror
* Step 6. Multi-screen

## Step 1. Add a new visual module

The visual rendering of the simulation is managed by the module "Visual.exe", usually called "VISUAL" when creating a new [configurations](../HT_Create_custom_work_environment/HT_Create_A_New_Workspace.html).

In order to have your own visual module configuration, start by [adding a new visual module in your configuration](../HT_Add_module/Add_module.md)*.
* The *executable* of the module should be `${STUDIO_PATH}/SCANeRstudio_2021/bin/x64/visual.exe`
* The *process name* of the module is your choice.  
  Prefer capitalized names without white space.  
  For clarity, start with "VISUAL_" followed by the name of your simulator, work station or display system.
* The *configuration file* can be any text file. We recommand using the default name `observer.cfg`, or at least one that starts with `observer...`.
> **Tip:** In the *Process Editor*, click *VISUAL* in the list of SCANeR modules in order to pre-fill the process parameters. Then adjust to your liking.

![Add a new visual module](./assets/v1.png)

## Step 2. Initiate the visual configuration

In the *Process Editor*, click the file icon ![Icon Edit File](./assets/icon_edit.png) in front of the configuration file in order to open and edit it.

> **Note:** If you are using a new file, start by copy-pasting the contents from `SCANeRstudio_2021/data/DEFAULT/observer.cfg`.

The file is divided in sections.
```
[Common]
; settings that will be applied to all visual modules using that use this configuration file.

[VISUAL]
; settings that will be applied to the visual module called "VISUAL"
[VISUAL:1]
; settings that will be applied to the pipe #1 of "VISUAL"
[VISUAL:1.1]
; settings that will be applied to the channel #1 of pipe #1 of "VISUAL"

; [...]
```
Unless a setting is defined in a lower hierarchy level, the value is inherited from higher level of hierarchy.  
`[Common]` > `[VISUAL]` > `[VISUAL:1]` > `[VISUAL:1.1]`

Below the existing sections, create new sections that matches your own visual module name.

```
; [...]

[VISUAL_SHOWSIM]

[VISUAL_SHOWSIM:1]

[VISUAL_SHOWSIM:1.1]

; [...]
```

## Step 3. View geometry

## Step 4. Quality VS performance

## Step 5. Add a mirror

## Step 6. Multi-screen

## Hint : Use a sample configuration
