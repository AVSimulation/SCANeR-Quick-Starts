# How to? run a massive simulation to test and validate an ADAS

Thanks to this guide you'll see how to
* Step 1. Execute SCANeR simulations with SCANeR compute
* Step 2. Display SCANeR results within an analytic web page

This tutorial requires
* [Foundation Pack](https://www.avsimulation.com/pack-foundation/)
* [AD/ADAS Pack](https://www.avsimulation.com/pack-ad-adas/)
* [Massive Simulation Pack](https://www.avsimulation.com/pack-massive-simulation/)

You don't have these already? [Get your Trial version of SCANeR](../HT_Download_Trial_SCANeR/HT_Install_Trial_SCANeR.md).

> Tips, If you do not have yet all of the above content no worries ;)
> You can download and use our prepared one: [AEB test case]()
> This is the data we'll use in steps below :thumbsup:

## Principle of operations

![](./assets/SCANeRProducts1.png "SCANeR Products")

SCANeR compute is SCANeR studio solver, it enables to run SCANeR simulation on HPC architecture.
It is compatible with any HPC platform (e.g. Azure, AWS, Alibaba) and supports any container solutions (e.g. Docker, Kubernetes).
To generate known and unknow test cases use SCANeR explore.

This Quick Starts will guide you to

* 1.	Prepare SCANeR workspace under Windows
* 2.	Generate test cases thanks to SCANeR studio, explore under Windows
* 3.	Port SCANeR workspace under Linux
* 4.	Make accessible test cases under Linux
* 5.	Run test cases thanks to SCANeR compute under Linux
* 6.	SCANeR Analytics

:arrow_right: [Follow the Guide: 1. Prepare SCANeR workspace under Windows](../HT_Prepare_SCANeR_workspace_under_Windows.md)
