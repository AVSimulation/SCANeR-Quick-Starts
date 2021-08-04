# How to? Evaluate and validate a radar sensor

You have access to SCANeR studio and would like to includes radar sensors in your simulations ? 

This guide explains how to design an experimentation to evaluate and validate a radar sensor.

AVSimulation provides 3 levels of radar sensor models: 

- Level 1 Functional radar
- Level 2 Real time physics radar - This model integrates generic processing which enables to provide a Radar point cloud in real-time that exhibits all typical EM phenomenon like coupling between targets or with the environment, multiple reflections, ghost target, etc.
- Level 3 Full physics radar - This model delivers RAW data to enable real signal processing integration and produces Range-doppler maps. :warning: To make full use of this radar model, users need to have access to real sensor processing algorithms.

>Level 1 radar sensor is part of the AD/ADAS Pack. Using this radar sensor model, engineers are able to define the radar parameters (Beams, range, targets, etc.) and retrieve the outputs to validate an ADAS System.
>
>Level 2 and 3 are part of the Physics based Sensors Pack. Our physics based sensors models are developped in collaboration with Oktal-SE and are fully integrated into SCANeR studio. Thoses radar models allow the users to validate their sensors model
>
>Don't have them yet ? Feel free to request [SCANeR trial version](https://www.avsimulation.com/scaner-studio-trial/)

## Step 1 SCANeR workspace 
Edit configuration
Add Sensors modules - Sensors handles ...
done 
## Step 2 Prepare a radar model


## Step 3 Design your experiment
Once the workspace is ready, we can start designing the experiment in SCANeR.
During this step we will define:
- The proving ground
- The actors
- The radar model 
- The situations we want to face
- The metrics we are interested in

Our goal is to evaluate the ability of our ADAS system to prevent collision between our EGO car and a pedestrian crossing the road in a city environment. SCANeR comes with a default dataset to help you get started. We will use these data to design the experiment:
- Proving Ground: 
- Actors: EGO (SmallFamilyCar) and a Pedestrian (kid____)
- Radar model: ___
- Situation: EGO will be equiped with LRRS1 model and drive by a virtual driver at a contineous speed of 50kmh. Kid_Boy_02 will be deactivated by default. When EGO will be at less than 20 meters of Kid_Boy_02 then we will activate and force Kid_Boy_02 to cross the road without paying attention to EGO.
- Metrics: KPI/Metrics: Thanks to our ADAS system that we'll connect in Step 4. we'll connect LRRS1 outputs to our AEB inputs. We expect that EGO avoid colision.

## Step 4 Interface the ADAS System
