---
group: ADAS
short: SAMPLE_ADAS_AEB
order: 20
---

# SAMPLE_ADAS_AEB

This is a description and user manual of the sample included in the [Samples Pack](https://github.com/AVSimulation/SCANeR-Samples-Pack).

Contents:
* **Goal** of the sample.
* **How to use** with a compiled C++ ADAS model.
* **Use the Python** ADAS model instead.
* **Explanation**.

## Goal

This sample shows how to control an Ego vehicle with your ADAS system.  
The Ego vehicle drives on a straight road until a pedestrian crosses ahead. The ADAS AEB is in charge of performing the emergency braking in order to avoid collision.

This one is as simple as it gets for you to practice or to start from for your own projects.  

## How to use

1. Load the SCANeR configuration SAMPLE_2022_ADAS_AEB ([how?](../HT_Change_work_environment/HT_Change_work_environment.md)).  

   *The required modules start automatically.*
   
   > Notice the custom module `ADAS_C` in group `SENSORS`.

2. Open the scenario `pedestrian_crossing.sce`.

3. Start the simulation.

   *Set the default AEB trigger distance.*  
      
   > This is an interactive variable set in the MICE script.

   *The Ego vehicle drives itself thanks to a Virtual Driver.*

   *When Ego reaches the trigger object (in red), the pedestrian starts crossing the road.*
   
   > This is the result of the MICE script's rule "Pedestrian cross road".

   *When the distance between Ego and the pedestrian is lower than the trigger distance, the vehicle brakes."*
   
   > This is the result of the `ADAS_C` custom module.

   *The simulation stops automatically after 20 seconds.*
   
   > This is the result of the Stop Criteria "Final Time" in Ego's Vehicle Instance Setup.

## Use Python instead

1. Stop the simulation.

2. Stop the `ADAS_C` module.  
   (`Right Click > Stop process`, or simply double-click on it)

3. Start the `ADAS_PY` module instead.  
   (`Right Click > Start process`, or simply double-click on it)
     
4. Start the simulation

    *From there the behaviour is the same as with the compiled module `ADAS_ACC`.*

## Explanation

### ADAS_C

* Find the Visual Studio C++ 2019 project of the interfaced ADAS here: `SCANeR-Samples-Pack-2022\APIs\samples\evaluation.sln` > `ADAS\ADAS_AEB'.  

Checkout out the tutorial: [How to evaluate and validate an ADAS system](./HT_ADAS.md).  
This sample is a direct application :)

### ADAS_PY

* The SCANeR module executable is set to `${STUDIO_PATH}/SCANeRstudio_2022/bin/x64/python/python.exe`, i.e. the Python installation delivered in SCANeR.  
* The extra arguments `${LOCAL_STUDIO_PATH}\SCANeR-Samples-Pack-2022\APIs\samples\ScanerAPI\EVAL_ADAS\python\eval_adas.py` point to the script itself.  
* The script includes the same contents as ADAS_C project, using the SCANeR API in Python instead of C++.
