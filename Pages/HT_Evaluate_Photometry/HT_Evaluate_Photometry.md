# How to evaluate and validate a photometry with SCANeR studio

In this guide we'll get started with the basic features for Headlight simulation.

We'll use features from the [Headlights Pack](https://www.avsimulation.com/pack-headlights/), and also from the base [Foundation Pack](https://www.avsimulation.com/pack-foundation/).  
More details about the Software packs on this link: https://www.avsimulation.com/pack-foundation/.

As always you can get these for free by requesting a [Trial version of SCANeR studio](https://www.avsimulation.com/scaner-studio-trial/).

* Step 1. Prepare the workspace
* Step 2. Design the headlamp system
* Step 3. Evaluate the photometry
* Step 4. Manage the environment materials

## Step 1. Prepare the workspace

> **Tip:** I advise you to use a dedicated workspace for headlight studies.  
> :leftwards_arrow_with_hook: [How to create a workspace](HT_Create_custom_work_environment/HT_Create_A_New_Workspace.md)

In addition to default modules, two additional are useful
* `NIGHTTESTMANAGER` is mandatory
* `VISUAL_HL` is the same as `VISUAL`, but with preset settings for night rendering.
* `AFSMANAGER` is only useful for AFS (Advanced Frontlight System) simulation. We won't use it in the current guide.

<!---
> **Note:** For AFS simulation, check out the dedicated guide.
> :leftwards_arrow_with_hook: [How to evaluate a command law for AFS](../HT_Evaluate_and_validate_AFS/HT_Evaluate_and_validate_AFS.md)
--->

Add these modules to your current configuration.
`CONFIGURATION` > `Configuration Manager` > `Add Process`

> **Note:** you will find `NIGHTTESTMANAGER` in the list, but `VISUAL_HL` needs to be renamed from `VISUAL`. 
> It is indeed the same process but with a different name.  
> (First select `VISUAL` in the list to auto-fill the process parameters, then change the process name to "VISUAL_HL" and `Add` the module)
> 
> The change of name is important, as it will activate a different section of the configuration file `observer.cfg`.  
> In the section `[VISUAL_HL]` of the `observer.cfg` you will find the setting `RenderingMode = LightingSimulation`.  
> If you want to do headlights simulation on any visual module, make sure this setting is activated for the said visual module.
> 
> More details about the visual configuration in the dedicated guide:  
> :leftwards_arrow_with_hook: [How to configure the visual rendering](../HT_configure_visual/HT_configure_visual.md)

## Step 2. Design the headlamp system

## Step 3. Evaluate the photometry

## Step 4. Manage the environment materials
