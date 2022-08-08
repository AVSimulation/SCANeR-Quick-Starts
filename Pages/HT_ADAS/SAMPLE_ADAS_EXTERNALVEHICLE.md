---
group: ADAS
short: SAMPLE_ADAS_EXTERNALVEHICLE
order: 40
---
# Sample_ADAS_EXTERNALVEHICLE

This guide explains how to use the Sample "ADAS_EXTERNALVEHICLE" available in the [Samples Pack](https://github.com/AVSimulation/SCANeR-Samples-Pack).

## Goal

This sample shows how to synchronize a Simulink dynamic vehicle model with an ADAS with SCANeR studio in non-real time running at 2000 hz.

## How to use it

Once in the SAMPLE_ADAS_EXTERNALVEHICLE configuration:

> Tip: [How to switch between workspaces](https://avsimulation.github.io/SCANeR-Quick-Starts/Pages/HT_Change_work_environment/HT_Change_work_environment.html)

* Open the scenario “EVAL_ADAS_EXTERNALVEHICLE.sce”,

![scenario](./assets/sce.PNG)

* Open MATLAB and the Simulink model “\SCANeR-Samples-Pack-20xx\APIs\samples\VehicleDynamics\RemoteVehicleModel\EVAL_ADAS_EXTERNALVEHICLE\RemoteVehicleModel_Callas.slx”,

> If it's your first time using MATLAB with SCANeR, an additional step is required. You will find more information in SCANeR’s User Manual, chapter `2.3.3.3.1. First time installation`. This step will add necessary pathes to the MATLAB Set Path and prepare Simulink libraries according to current MATLAB version.

* Run the Simulink model and configuration modules,

* Play the scenario.

> In this scenario, the UDP communication port used for the remote model is 8842. Using a firewall/antivirus may block the communication. To prevent this, you may simply allow it or modify it in the sample. ("right click/Edit model..." on the EGO vehicle to display the vehicle in the VEHICLE mode and edit it.)
>
> ![UDPremoteModel](./assets/UDPremoteModel.PNG)

### During the simulation

You will then be able to visualize that the simulink model with ADAS is synchronised with SCANeR.

> Due to the S-function, the vehicle will start after few seconds.

The SCANeR API is accessible in Simulink within the Vehicle Dynamics ComUDP API through RT Gateway and its filter.

> More information in SCANeR’s User Manual: `2.16. UDP RTGateway protocol`

The operating frequencies of the modules are orchestrated by the Offline Scheduler.

> More information in SCANeR’s User Manual: `7.28.1. Offline Scheduler`

![Capture](./assets/Article_GitHub_Sample-EVAL-ADAS-EXTERNALVEHICLE.PNG)

_______________________________________________

###### :car: Do not hesitate to look at other samples of the [Samples Pack](https://github.com/AVSimulation/SCANeR-Samples-Pack). :car:
