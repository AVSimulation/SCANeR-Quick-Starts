:arrow_left: [First launch](../HT_FirstLaunch/HT_FirstLaunch.md)

# How to create a new workspace

In SCANeR studio, the different workspaces you can have are called `Configurations`.  In the context of simulation, these different `Configurations` will help you organize your data and simulation parameters between your different projects. For instance, if you run the simulation on a Workstation, the running modules will not be exactly the same as in a large Simulator environment. That's why you can use different `Configurations` in order to save your parameters and data according to the use case.

This guide explains how to create a specific `Configuration` in SCANeR studio and switch to it.

- Step 1. Open the Configuration Manager
- Step 2. Create a new Configuration
- Step 3. Switch to the newly created Configuration

There is a `DEFAULT` configuration that comes with the software's install.

> Note: We recommend not to alter this `DEFAULT` configuration, as it is the configuration that will be used to create new basic custom configurations.

Each `Configuration` has a specific set of settings and data that will be used when you switch to it. This helps you setup the environment according to the experiments you want to conduct. For instance, the Configuration you will use to make a simulator run will not be composed of the same modules as the Configuration used on your workstation. In this case, having two separate configurations helps you differentiate the configuration files, the launched modules and the data file used in the simulation.

Enough chatter, let's jump into the guide! 😁

## Step 1. Open the Configuration Manager

​	Click on `"CONFIGURATION" -> "Configuration Manager..."` and a window allowing you to manage you different Configurations will appear.

![Configuration Manager Access](./assets/configurationManagerAccess.png)

​	You can see your different available configurations here and switch between them.

![Configuration Manager](./assets/configurationManager.png)
> Tips, When a module has its "Selected" checkbox ticked it'll start when the supervisor will click on the run simulator button. When a module has its "Auto Start" checkbox ticked it'll automatically start when the configuration is loaded (click on OK).

## Step 2. Create a new Configuration

1.  To create a new configuration you have to click on the "New Configuration" button located in the bottom left of  the Configuration Manager. The window that appears is the Configuration Creation Wizard. The first thing you have to choose is the source configuration, meaning the settings files that will be copied to create your new configuration. If you don't have specific configuration yet, you can use the `DEFAULT` configuration as source.

![Configuration Creation Wizard 1](./assets/configCreationWizard-1.png)

2.  After that, you can name the configuration you are creating and choose its path. If you do not modify the path, it will be : 
    - `<SCANeR Install Path>\config\<Your_Config_Name>\`.

![Configuration Creation Wizard 2](./assets/configCreationWizard-2.png)

3.  The last thing you have to choose is the path of the data for your configuration. If you do not modify it, the path will be :
    - `<SCANeR Install Path>\data\<Your_Config_Name>\`.

![Configuration Creation Wizard 3](./assets/configCreationWizard-3.png)

## Step 3. Switch to your Configuration

​	You can now select your newly created Configuration in the list and click on "Apply" in the bottom right corner of the window.

​	If you need more help about this step, you can check the guide about this topic [here](../HT_Change_work_environment/HT_Change_work_environment.md).

**Congratulations! You now have your own custom Configuration!**

:arrow_right: [Navigate the user interface](../HT_Navigate/HT_Navigate.html)
