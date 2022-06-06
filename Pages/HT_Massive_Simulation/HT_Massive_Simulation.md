---
group: Massive Simulation
short: Introduction
order: 0
---

# How to run a massive simulation to test and validate an ADAS

This guide will walk you through the Massive Simulation workflow in SCANeR:
* [Part 1. Prepare SCANeR workspace on Windows](HT_Prepare_SCANeR_workspace_under_Windows.md)
* [Part 2. Generate test cases on Windows](HT_Generate_test_cases.md)
* [Part 3. Port SCANeR workspace on Linux](HT_Port_SCANeR_workspace_under_Linux.md)
* [Part 4. Run test cases on Linux](HT_Validate_test_cases_under_Linux.md)
* [Part 5. SCANeR Analytics](HT_Analytics.md)

[*Bonus:* Run SCANeR within Docker](HT_Docker_build_run.md)

## Requirements

* [Foundation Pack](https://www.avsimulation.com/pack-foundation/)
* [AD/ADAS Pack](https://www.avsimulation.com/pack-ad-adas/)
* [Massive Simulation Pack](https://www.avsimulation.com/pack-massive-simulation/)

Don't have these already? [Get your Trial version of SCANeR](https://www.avsimulation.com/free-download/).

> **Tip:** Get the SCANeR ready-to-use environment from our github space: [Samples-Pack README](https://github.com/AVSimulation/SCANeR-Samples-Pack)  
> For this guide we'll use `SAMPLE_COMPUTE_LOCAL` and `SAMPLE_COMPUTE_HPC`.

You will also need an HPC platform. For the exercise, a simple Linux computer or VM is enough. :thumbsup:

## Principle of operations

![](./assets/SCANeRProducts1.png "SCANeR Products")

SCANeR compute is a solver for SCANeR, it enables you to run SCANeR simulations on HPC (High Performance Computing) architecture.  
It is compatible with any HPC platform (e.g. Azure, AWS, Alibaba) and supports any container solution (e.g. Docker, Kubernetes).  
To generate known and unknown test cases, use SCANeR explore (it takes input from a SCANeR studio test case).
