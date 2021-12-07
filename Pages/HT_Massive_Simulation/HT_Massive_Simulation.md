---
group: Massive Simulation
short: Introduction
order: 0
---

# How to run a massive simulation to test and validate an ADAS

This guide will walk through the Massive Simulation workflow in SCANeR:
* [Guide 1. Prepare SCANeR workspace on Windows](HT_Prepare_SCANeR_workspace_under_Windows.md)
* [Guide 2. Generate test cases on Windows](HT_Generate_test_cases.md)
* [Guide 3. Port SCANeR workspace on Linux](HT_Port_SCANeR_workspace_under_Linux.md)
* [Guide 4. Run test cases on Linux](HT_Validate_test_cases_under_Linux.md)
* [Guide 5. SCANeR Analytics](HT_Analytics.md)

It requires
* [Foundation Pack](https://www.avsimulation.com/pack-foundation/)
* [AD/ADAS Pack](https://www.avsimulation.com/pack-ad-adas/)
* [Massive Simulation Pack](https://www.avsimulation.com/pack-massive-simulation/)

You don't have these already? [Get your Trial version of SCANeR](https://www.avsimulation.com/free-download/).

> **Tip:** If you do not have yet all of the above content no worries 😉  
> You can get the SCANeR ready-to-use environment from our github space
> ```C
> git clone -b 2022 https://github.com/AVSimulation/SCANeR-Quick-Starts.git
> ```
> For this guide we'll use `SAMPLE_COMPUTE_LOCAL` and `SAMPLE_COMPUTE_HPC` :thumbsup:

You will also need a HPC platform. For the exercise, a simple Linux computer is enough.

## Principle of operations

![](./assets/SCANeRProducts1.png "SCANeR Products")

SCANeR compute is SCANeR studio solver, it enables to run SCANeR simulation on HPC (High Performance Computing) architecture.  
It is compatible with any HPC platform (e.g. Azure, AWS, Alibaba) and supports any container solutions (e.g. Docker, Kubernetes).  
To generate known and unknow test cases use SCANeR explore (it takes as an input a SCANeR studio test case).
