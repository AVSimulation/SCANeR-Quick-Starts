---
group: Massive Simulation
short: Docker run
order: 60
---

# Guide 6. (Optional) How to run SCANeR within Docker

SCANeR Standalone method supports any container solutions (e.g. Docker, Kubernetes).  

With this guide we'll see
- Step 1.	Build a SCANeR Docker image
- Step 2.	Run the SCANeR Docker image

## Step 1. Build a SCANeR Docker image

Great news! SCANeR installer comes with all files you need :)  
To build the SCANeR image read: `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\build\README.txt`  
To use the SCANeR environment we made within previous steps follow specific steps below:  
1. Rename `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\sample` to `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\sample_old`
2. Create a new empty folder `sample` under `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\`
3. Add to this new folder 2 empty folders: `config` and `data`
4. Copy `configurations.cfg` from `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\sample_old` to `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\sample`
5. Copy content of `$STUDIO_PATH\SCANeRstudio_202X\config\SAMPLE_COMPUTE_HPC\` to `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\sample\config`
6. Copy content of `$STUDIO_PATH\SCANeRstudio_202X\data\SAMPLE_COMPUTE_HPC\` to `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\sample\data`

Once the SCANeR Docker image is built, let's run it!

## Step 2. Run the SCANeR Docker image

Great news! SCANeR installer comes with THE file you need :)  
To run the SCANeR image read: `$STUDIO_PATH\SCANeRstudio_202X\APIs\DockerCompute\run\README.txt`