# HOW TO? Create a new Workspace in SCANeR Studio

In SCANeR Studio, the different workspaces you can have are called **Configurations**. 

This guide explains how to create a specific **Configuration** in SCANeR Studio and switch to it.

- Step 1. Open the Configuration Manager
- Step 2. Create a new Configuration
- Step 3. Switch to the newly created Configuration

There is a **DEFAULT** configuration that comes with the software's install. This **DEFAULT** configuration is used as a basis for all the custom ones you will be creating by using SCANeR Studio. We recommend not to alter this **DEFAULT** configuration.

Each **Configuration** has a specific set of settings and data that will be used when you switch to it. This helps you setup the environment according to the experiments you want to conduct. For instance, the Configuration you will use to make a simulator run will not be composed of the same modules as the Configuration used on your workstation.

Enough chatter, let's jump into the guide! 😁

##### Step 1. Open the Configuration Manager

​	Click on **"CONFIGURATION" -> "Configuration Manager..."** and a window allowing you to manage you different Configurations will appear.

![Configuration Manager Access](./assets/configurationManagerAccess.png)

​	You can see your different available configurations here and switch between them.

![Configuration Manager](./assets/configurationManager.png)

##### Step 2. Create a new Configuration

1.  To create a new configuration you have to click on the "New Configuration" button located in the bottom left of  the Configuration Manager. The window that appears is the Configuration Creation Wizard. The first thing you have to choose is the source configuration, meaning the settings files that will be copied to create your new configuration. If you don't have specific configuration yet, you can use the **DEFAULT** configuration as source.

![Configuration Creation Wizard 1](./assets/configCreationWizard-1.png)

2.  After that, you can name the configuration you are creating and choose its path. If do not modify it it will be the name of your Configuration in the "config" folder of your SCANeR install path.

![Configuration Creation Wizard 2](./assets/configCreationWizard-2.png)

3.  The last thing you have to choose is the path of the data for your configuration. If do not modify it it will be the name of your Configuration in the "data" folder of your SCANeR install path.

![Configuration Creation Wizard 3](./assets/configCreationWizard-3.png)

##### Step 3. Switch to your Configuration

​	You can now select your newly created Configuration in the list and click on "Apply" in the bottom right corner of the window.

**Congratulations! You now have your own custom Configuration!**
