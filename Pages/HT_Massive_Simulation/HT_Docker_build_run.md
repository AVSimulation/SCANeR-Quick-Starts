---
group: Massive Simulation
short: Docker run
order: 60
---

# How to run SCANeR within Docker

SCANeR Standalone method supports any container solutions (e.g. Docker, Kubernetes).  

With this guide we'll see
- Step 1.	Build a SCANeR Docker image
- Step 2.	Run the SCANeR Docker image

**Prerequisite**: Have a valid installation of Docker Engine 😉  
More information on: [https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)  
> Tip: SCANeR is currently compatible with Ubuntu Focal 20.04 (LTS) and Centos 7

## Step 1. Build a SCANeR Docker image

Great news! SCANeR installer comes with all the files you need 😊  

To build the SCANeR image read: `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\build\README.txt`  

To use the SCANeR environment we made within previous steps follow the specific steps below:  
1. Rename `.\APIs\DockerCompute\run\sample` to `.\APIs\DockerCompute\run\sample_old`
2. Create a new empty folder `sample` under `.\APIs\DockerCompute\run\`
3. Add 2 new empty folders within this new folder: `config` and `data`
4. Copy `configurations.cfg` from `.\APIs\DockerCompute\run\sample_old` to `.\APIs\DockerCompute\run\sample`
5. Copy content of `.\config\SAMPLE_COMPUTE_HPC\` to `.\APIs\DockerCompute\run\sample\config`
8. Copy content of `.\data\SAMPLE_COMPUTE_HPC\` to `.\APIs\DockerCompute\run\sample\data`
9. Copy and replace `datafile.cfg` from `.\APIs\DockerCompute\run\sample_old\datafile.cfg` to `.\APIs\DockerCompute\run\sample`
10. Edit `.\APIs\DockerCompute\run\sample\config\Process.xfg` and update the path to your System Under Test used within the Docker image. In our case you should update it from `${LOCAL_STUDIO_PATH}\SCANeR-Samples-Pack-2022\data\SAMPLE_COMPUTE_HPC\bin\ubuntu\20.04\SUT_AEB` to `${LOCAL_STUDIO_PATH}\data\bin\ubuntu\20.04\SUT_AEB`

Once the SCANeR Docker image is built, let's run it!

## Step 2. Run the SCANeR Docker image

Great news! SCANeR installer comes with THE file you need 😊  
To run the SCANeR image read: `.\APIs\DockerCompute\run\README.txt`
