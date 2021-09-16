:arrow_left: [Navigate in the user interface](../HT_Navigate/HT_Navigate.md)

# How to run a SCANeR simulation: the good practices

You are using SCANeR everyday to manage your experimentation but do you use it in the proper way ? 🤔

This guide explains how to manage the execution of your simulation
- Step 1. Run modules
- Step 2. Run the simulation
- Step 3. Stop the simulation
- Step 4. Stop modules 

## Step 1. Run modules

1. Click on the `Start Simulator` button (double blue triangles) to launch all the previously selected modules
![](./assets/LaunchModules.png)  

2. Verify the status of the modules thanks to symbol in the green circle next to the modules.  
![](./assets/ModuleStates.png)  
The correct status of the module should be `Loaded`  

>All selected modules will automatically start (some of these have GUI, as ACQUISITION, VISUAL, etc.)
>Would you like to create your own module, and learn more about their states? [How to? API creation]()

## Step 2. Run the simulation
Click on the `Play Scenario` button (black triangle in a green circle) to launch the simulation  
![](./assets/LaunchSimu.png)  
The correct status of the module should be `Running`  

>When you run a scenario for the first time SCANeR creates information into cache memory to accelarate the futur runs. The first it'll take a bit more time, thank you for your patience 
>If you have set parameters in your scenario you can set the value of these parameters at the start of the simulation. Click on the grey triangle next to the `Play Scenario` button and choose `Play Scenario with Parameters`. Would you like to design parametric simulation? [How to? Design scenario for SCANeR Explore]()

## Step 3. Stop the simulation
Click on the `Stop Simulation` button (black square in a red circle)  
![](./assets/StopSimu.png)

⚠ This is the right way to stop the simulation, any others button should be used to stop the simulation. ⚠  
Pause the simulation is also possible, click on the `Pause Simulation` button while while the simulation is running 😊

## Step 4. Stop modules
Click on the `Stop Simulator` button (white cross in a red circle)  
![](./assets/StopModules.png)

This button close, and kill the SCANeR modules in a clean way. If you stop the simulation with this button inconsistencies can appear (e.g. at the reload of the next simulation).  
  
We rely on you to run your simulation as it should be 😉

:arrow_right: [Replay a simulation](../HT_Replay_Simulation/HT_Replay_Simulation.md)
