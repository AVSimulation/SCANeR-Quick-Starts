# How to? run SCANeR simulation within Docker?

Thanks to this guide you'll see how to
* Step 1. Build a Docker image to run SCANeR
* Step 2. Run the Docker container

This guide assumes that you already have a clean Docker Engine isntallation.

This tutorial requires
* [Massive Simulation Pack](https://www.avsimulation.com/pack-massive-simulation/)

You don't have it already? [Get your Trial version of SCANeR](../HT_Download_Trial_SCANeR/HT_Install_Trial_SCANeR.md).

> Tips, we provide with SCANeR installer all files you need to build and run SCANeR within Docker
> This is the data we'll use in steps below :thumbsup:
> Once you'll have installed SCANeR template files and README are available under `.\SCANeRstudio_202X\APIs\DockerCompute`

## Principle of operations

![](./assets/docker_scaner_overall.png.png "SCANeR with Docker")

SCANeR compute can be easily “dockerized”.  
The generated docker image is fully reusable and independent of the tested system.  
By using docker mount points, SCANeR workspace (configuration, data and System Under Test) are injected at runtime.  

The proposed method is a generic one.  
Depending of your IT architecture feel free to customize it according to your workflow and setup.

## Build a Docker image to run SCANeR
To build the SCANeR image, put the wanted SCANeR Standalone installer `SCANeRstudio_202X.XrXX.tar.bz2` in `.\SCANeRstudio_202X\APIs\DockerCompute\build`.  
If using AVSimulation license server, customize the `hasp_84230.ini` to match your environment.  
Launch the script with release number of the source file as argument to build the image.  
```C
$ ./build.sh XX
```
The resulting image will be tagged: `avsimulation/compute:202X.XrXX`  
Your image is ready :thumbsup:

## Run the Docker container

Using the SCANeR docker image:
* config    : folder that host the running configuration, will be mounted as docker volume to `config/<your_SCANeR_workspace>` within the container
* data      : folder that host the data (experiments and system under test): will be mounted as docker volume to `data/<your_SCANeR_workspace>` within the container
* out       : results ouput folders, will be mounted as docker volume to `/AVSimulation/OUT` within the container
* launch.sh : script for lauching the container

Copy wanted SCANeR configuration folder in `config` directory.  
Copy wanted SCANeR data in `data` directory.
start `launch.sh`
get results within `out` folder.

The default setup is to launch all scenario of the `<your_SCANeR_workspace>`.
To customize behaviour, change the `compute.sh` script in `.\SCANeRstudio_202X\APIs\DockerCompute\build`and rebuild.
