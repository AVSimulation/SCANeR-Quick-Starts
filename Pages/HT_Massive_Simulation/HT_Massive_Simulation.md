# How to? run a massive simulation to test and validate an ADAS

Thanks to this guide you'll see how to
* Step 1. Execute SCANeR simulations with SCANeR compute
* Step 2. Display SCANeR results within an analytic web page

This tutorial requires
* [Foundation Pack](https://www.avsimulation.com/pack-foundation/)
* [AD/ADAS Pack](https://www.avsimulation.com/pack-ad-adas/)
* [Massive Simulation Pack](https://www.avsimulation.com/pack-massive-simulation/)
You don't have these already? [Get your Trial version of SCANeR](../HT_Download_Trial_SCANeR/HT_Install_Trial_SCANeR.md).

This tutorial assumes you already have
* Designed with studio a scenario with sensors, explore parameters, stop criteria, etc.
* Setup with studio a SCANeR workspace for HPC including the System Under Test (SUT)
* Prepared with explore a test plan and generated known and unknown scenarios

> Tips, If you do not have yet all of the above content no worries ;)
> You can download and use our prepared one: [AEB test case]()
> This is the data we'll use in steps below :thumbsup:

## Principle

![](./assets/SCANeRProducts1.png "SCANeR Products")

SCANeR compute is SCANeR studio solver, it enables to run SCANeR simulation on HPC architecture.
It is compatible with any HPC platform (e.g. Azure, AWS, Alibaba) and supports any container solutions (e.g. Docker, Kubernetes).

Tips, learn more about [SCANeR explore]()

## Step 1. Execute SCANeR simulations with SCANeR compute

### Functional sensor model

In this step, we will use the `radar` sensor functional model (L1).

> **Note:** SCANeR functional models are part of [AD/ADAS Pack](https://www.avsimulation.com/pack-ad-adas/). They use simulation logical content and 3D world model to determine a sensor's outputs. These are perfect models returning perfect targets' list. You can add noise to simulate signal perturbation. SCANeR functional models are made for you if you want to focus on the ADAS system himself or simulate without effort any of the 6 Levels of Vehicle Autonomy.

## Step 2. Display SCANeR results within an analytic web page

### Read & write

Now the values can actually be read from and written to SCANeR simulation buses using the handles. This is typically done in a main loop.

```C
short targetsCount = Com_getShortData(radar_300000, "targetsArrayCount"); //read member "targetsArrayCount" of "ISensor/SensorMovableTargets"
if (targetsCount > 0)
{
  char distanceToCollisionTmp[50];
  sprintf_s(distanceToCollisionTmp, "targetsArray[%d]/distanceToCollision", Com_getShortData(radar_300000, "nearestTarget"));
  distanceToCollision = Com_getFloatData(radar_300000, distanceToCollisionTmp);
}
```