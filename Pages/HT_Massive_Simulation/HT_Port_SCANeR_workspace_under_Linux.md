:arrow_left: [Guide 2. Generate test cases thanks to SCANeR explore under Windows](../HT_Prepare_SCANeR_workspace_under_Windows.md)

# How to? Port SCANeR workspace under Linux

The SCANeR workspace we made up to now is for Windows (`SAMPLE_COMPUTE_LOCAL`).  
Use an HPC architecture with a Linux distribution requires to port the Windows SCANeR workspace to Linux.  
The goal of this guide is to give you the procedure to do it.  

- Step 1.	Install SCANeR under Linux using the Standalone method
- Step 2.	Port the Windows SCANeR workspace to Linux
- Step 3.	Compile your system under test under Linux

## Step 1. Install SCANeR under Linux using the Standalone method

Two kinds of Linux installations are available:
* Hybrid: supervise SCANeR simulation from Windows and distribute SCANeR execution on Linux and/or Windows. It comes as a Windows Add-on installer.
* Standalone: runtime method, to run SCANeR studio or compute without server X11. Used to distribute SCANeR on HPC/Cloud, it and supports any container solutions (e.g. Docker, Kubernetes).

For Massive Simulation application we’ll use the Standalone one.  
To install SCANeR in Standalone mode you’ll the Standalone package: `SCANeRstudio_202X.X-rXX.tar.bz2`  
If you do not have it simply ask us 😊  
Once you get it extract the contents of the tar archive and follow steps in the delivered [`README-202X.Linux`](./assets/README-2022.Linux)

> Tips, it is available under: `.\SCANeRstudio_202X.X-rX.tar.bz2\SCANeRstudio_202X.X-rX.tar\AVSimulation\`

In this README you’ll learn:
* How to do a SCANeR installation under Linux
* SCANeR dependencies you’ll need to install
* SCANeR license installation and setup
* Execute SCANeR under Linux
* Compile SCANeR SDK under Linux
* Use SCANeR in headless mode

## Step 2. Port the Windows SCANeR workspace to Linux

Once the installation of SCANeR is done under Linux you have to make accessible your SCANeR Windows workspace.  
As each IT infrastructure is different there is no specific method, choose your favorite one.  

In our case we’ll simply share the Windows drive with Linux and copy/paste the Windows SCANeR workspace under Linux before to customize it.  
We use Ubuntu 20.04 LTS x64.  
In our case we

1. Copy/paste the content of Windows SCANeR workspace to Linux SCANeR workspace (`SAMPLE_COMPUTE_LOCAL`).

![](./assets/Linux1.png)

To make it clear we rename the `SAMPLE_COMPUTE_LOCAL` to `SAMPLE_COMPUTE_HPC` under:
* `.\APIs`: contains your system under test interface
* `.\config`: contains your SCANeR environment
* `.\data`: contains your SCANeR data

![](./assets/Linux2.png)

2. We add its name and path into 'configurations.cfg'

![](./assets/Linux3.png)

3. Let’s edit our new SCANeR workspace 'SAMPLE_COMPUTE_HPC' under Linux and update SCANeR process paths: from your shell call 'SCANeRconfigurator'

![](./assets/Linux4.png)

It gives your access to SCANeRconfigurator HMI

![](./assets/Linux5.png)

For each SCANeR module available into your SCANeR workspace update its executable path:
In `SAMPLE_COMPUTE_LOCAL` you had
![](./assets/Linux6.png)
Update it into `SAMPLE_COMPUTE_HPC` to
![](./assets/Linux7.png)

Repeat it for all your SCANeR modules 👍🏻

> Tips, to do so do not forget to setup your shell environment for SCANeR by calling the SCANeR setenv (more details are available into the `README-202X.Linux`)
> ![](./assets/Linux8.png)

## Step 3. Compile your system under test under Linux

> Tips, SCANeR SDK is the same between Windows and Linux. So what? That’s good news, you do not have to modify your existing System Under Test’s software interface with SCANeR, you simply have to rebuild it 👍🏻

In our case the sample we deliver is under: `.\APIs\samples\ScanerAPI\SUT_AEB`

> Tips, all details you need to build up your system under Linux are available into `README-202X.Linux`

To add a project into the compilation list simply:
1. Edit '.\APIs\samples\ScanerAPI\CMakeLists.txt' and add the line
```C ADD_SUBDIRECTORY(<your_project_name>)```

> Tips, `<your_project_name>` is `SUT_AEB` in our case

2. Create in your project a new CMake file `.\APIs\samples\ScanerAPI\SUT_AEB\CMakeLists.txt` and add the following lines

```C
SET(TARGET_NAME “SUT_AEB”)  
ADD_EXECUTABLE(${TARGET_NAME}  
<your_c_file.cpp>  
)  
TARGET_LINK_LIBRARIES(${TARGET_NAME}  
${SCANeR_API_LIB})  
```

Your system under test is now ready to build under Linux!  
To compile it, go to SCANeRstudio_202X/APIs and execute  
```C cmake . ```  
![](./assets/cmake.png)
```C make ```  
![](./assets/make.png)

The default output of the executable is under `.\APIs\bin\Linux\<distribution>\<version>\`  
In our case `<distribution>` is ubuntu, `<version>` is 20.04.  
Copy and paste the executable into your SCANeR workspace  

![](./assets/executable.png)

> Tips, this architecture is a generic one. As each IT infrastructure is different you can of course decide to implement it in another way 😉 should you have any related question please feel free to ask us! Put the system under test under SCANeR workspace is convenient for later application when running SCANeR in a container. But let’s see that later.

After these steps, you can make sure that you’re all set by editing SCANeRconfigurator.  
You should have the following result if you use the configuration we deliver.  

![](./assets/SCANeRWorkspaceDone.png)

:arrow_right: [Follow the Guide 4: Validate the new SCANeR workspace under Linux before to run it on HPC](../HT_Validate_test_cases_under_Linux.md)
