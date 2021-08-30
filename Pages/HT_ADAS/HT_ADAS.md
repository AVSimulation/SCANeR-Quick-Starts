# How to? evaluate and validate an ADAS system

This guide explains how to design an experimentation to evaluate and validate an ADAS system with SCANeR studio.

This tutorial requires the [Foundation](https://www.avsimulation.com/pack-foundation/) and [AD/ADAS](https://www.avsimulation.com/pack-ad-adas/) packs. If you don't have them already, [get your Trial version of SCANeR](../HT_Download_Trial_SCANeR/HT_Install_Trial_SCANeR.md) and follow this walk-through.

# Principle

SCANeR studio hosts the model of vehicle, sensors and the interfaces that allow to connect your ADAS model.

The *SCANeR API* is the interface. It allows to read the vehicle status, driver inputs and sensors outputs.

![Interface Principle](./assets/adas_interface_principle.png)

For the current tutorial, we are going to focus on a simple *Automated Emergency Braking* (AEB).
The brakes should be activated when a pedetrian is detected too close ahead of the host vehicle.

We will need
* Step 1. A sensor
* Step 2. The ADAS model
* Step 3. A scenario

Before starting, create a [dedicated workspace](HT_Create_custom_work_environment/HT_Create_A_New_Workspace.md) called `TUTO_ADAS` for instance.

## Step 1. Sensor model

### Sensor model

In this step, we will use the `radar` sensor functional model (L1).

SCANeR comes with a set sensor models to help you to begin. To view and edit sensor models go to `RESOURCES` tab `Sensors`.

> **Note:** SCANeR functional models are part of [AD/ADAS Pack](https://www.avsimulation.com/pack-ad-adas/). They use simulation logical content and 3D world model to determine a sensor's outputs. These are perfect models returning perfect targets' list. You can add noise to simulate signal perturbation. SCANeR functional models are made for you if you want to focus on the ADAS system himself or simulate without effort any of the 6 Levels of Vehicle Autonomy. If you want to focus on sensor processing check our [Physics Based Sensors Pack](https://www.avsimulation.com/pack-physics-based-sensors/).
![](./assets/sensorFunctionalModel.png "Functional models (L1)")

1. Right click on a radar model and select `Edit as new...`, the `Save sensor as...` GUI appears
> **Note:** Here we will edit as new `LongRangeRadarSensor` model to begin

2. Save as `LRRS1` your new radar model (xml format). The `Sensor model edition` GUI appears
> **Note:** We advise to use the same sensor model name as the market so you'll find it easily later from SCANeR resources.

This dialog enables to control any sensor's parameters as beam (e.g. quantity, shape, range, etc.).
Let's add `Predestrian` mobile obstacle to detection capatibilities.

3. Click on `Edit Targets`, check `Predestrian` and click on `OK`. Click on `Save and close` to get back to SCANeR studio supervision view.

Your `LRRS1` radar model is ready and available from SCANeR resources :thumbsup:

Let's build our scenario (and use `LRRS1` radar model on EGO :wink:)

### Sensor Module

During the simulation, the radar sensor model is managed by the module `SENSORS`.

Add the module to your configuration with `menu CONFIGURATION` > `Configuration manager` > `Add Process` > `SENSORS` > `Add`.
Then `Close` the *Add Process* window, `Apply` the new configuration settings and leave with `OK`.

## Step 3. Scenario

In this step, we will design our experimentation by defining the environment (the proving ground), the actors, the sensors and the story and the KPI/Metrics we would like to get for post-treatment.

We will use default models included in SCANeR:
* Environment/Proving ground: Community
* Actors: Ego (CALLAS SmallFamilyCar), Pedestrian (Kid_Boy_02)
* Sensor: LRRS1
* Story: Ego will be equiped with LRRS1 model and will be driven by a virtual driver at a contineous speed of 50kmh. Kid_Boy_02 will be deactivated by default. When EGO will be at less than 20 meters of Kid_Boy_02 then the ADAS model will activate and force Kid_Boy_02 to cross the road without paying attention to EGO.

### Initiate

1. Create a new scenario.  
Go to `menu FILE`> `New Scenario`, select `Community` environment and click on `OK`
2. Add an Ego vehicle.  
Find `RESOURCES panel` > `Vehicles tab` > `Cars (Callas)` > `SmallFamilyCar` and drag and drop it onto a straight road in the main view.
3. Add a pedestrian
Find `RESOURCES panel` > `Pedestrians tab` > `Kid_Boy_02` and drag and drop it onto the sidewalk, about 50 meters ahead of Ego.

### Ego's driver

By default, CALLAS vehicles are driven by a *Human Driver* (using the keyboard, game controller or simulator). In order to add some repetability, we will change to *Virtual Driver*.

> **Note:** A *Virtual Driver* acts as a *Human Driver* by using the vehicles inputs (pedals, steering wheel, ...) although these are automated. The Virtual Driver can be asked to follow specific trajectory and speed. It strictly follows the inputs it is given, and nothing else.

> An *Autonomous Driver* would follow traffic rules by simulating realistic human driving behavior. It would stop upon meeting the pedestrian, and our ADAS wouldn't be triggered. Although it is possible to configure this human driving emulation at a high level, it does not offer as much control as a *Virtual Driver*.

We want to force our Virtual Driver to follow a straight line with a speed of 50 kmph.

* In the main view, right click on the Ego vehicle > `Edit instance...`.
* From tab `Driver` set `Type` field value to `Virtual driver (automatic)`.
* From tab `Steering wheel control` set `Steering input` field to `Straight line`.
* From tab `Longitudinal control` set `Pedals control` field to `Follow a speed target specified in the command data`.
* From tab `Command data` section `Command type\Point by point` click on `Edit`.
  * Set column `Time(s)` row `1` to `0` and  row `2` to `60`.
  * Set column `Speed (km/h)` row `1` to `50` and  row `2` to `50`.
  * Set column `Gearbox ratio` row `1` to `1` and  row `2` to `1`.
* Click on `OK` to close `Command type\Point by point` edition and click on `OK` to apply changes and close instance edition

### Ego's sensor configuration

Earlier we have defined a *sensor model* "LRRS1". We can now attach it to the car, at a specified position on the front bumper.

* Find `RESOURCES panel` > `Sensors tab` > `LRRS1` and drag and drop it *on* the Ego vehicle in the main view.
* SCANeR asks you to create a sensors' configuration on this Vehicle. Aswer `Yes`. The `Sensor configuraiton edition` GUI appears.
> **Note:** A sensor's configuration is a set of sensor models to attach on a vehicle. From this dialog you'll be able to define each sensor's position/orientation, outputs, etc.
  * Set Position X to 3.5 m
  * Set Position Z to 0.5 m
> **Note:** The vehicle dimensions diagram at the bottom of the window helps to find this position.
* Click on `Save and close`. The `Save sensor configuration as...` GUI appears.
* Save as `SmallFamilyCar_AEB` your new sensor's configuration (xml format). The sensor's configuration including LRRS1 is now linked to `SmallFamilyCar`
> **Note:** Since each vehicle model has its own dimensions we can assume that a sensor's configuration will be dedicated to a specific vehicle model. So we advise to include the name of your vehicle in the sensor configuration's name.

### Pedestrian's activation

The pedestrian should not move until Ego is closer than 20 meters. In order to force the pedestrian to stay put, we should deactivate it.

* In the main view, right click on the pedestrian > `Edit instance...`.
* In tab `Vehicle`, set `Status` field value to `Inactive` and click `OK`.
> **Note:** *Inactive* means the pedestrian will not move, but is still part of the simulation. It is detected by the sensors. *Invisible* on the other hands, would remove the pedestrian from the simulation until it is switched back to *Inactive* or *Active*.

### Pedestrian crossing

The pedestrian should start moving, and cross the road when Ego gets closer than 20 meters.
A combination of *Trigger* and *Scripting* will allow us to do that.

Start by setting up the trigger.
* Find `RESSOURCES panel` > `Traffic tools tab` > `Trigger`

## Step 2. ADAS model

## Conclusion

Congratulations in connecting your ADAS model.

Check the other samples for ADAS:
* [Lateral control]()
* [Longitudinal control]()
* [LKA & ACC]()

Here are some suggestions to customize and enhance the sample:
* Edit a component of the CALLAS Ego vehicle dynamics: [How to? edit CALLAS dynamics model]()
* Use an external Edo vehicle dynamic model instead of CALLAS (CarSim, Vi-CRT, CarMaker, etc.): [How to? interface my dynamics model]()
* Set key performance indicators & metrics to use in post examination: [How to? configure KPI & metrics]()
