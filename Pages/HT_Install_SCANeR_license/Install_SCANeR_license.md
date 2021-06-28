### HOW TO? Update your SCANeR license

You already have a SCANeR license and you have purchased new packs, or a modification on your license has been recommended. 

This guide explains how to update your SCANeR license
- Step 1. Receive the new license
- Step 2. Open the web service / Sentinel Admin Control Center(SACC)
- Step 3. Apply the update to your license
- Having troubles

>**Important notes:**  
>Updates are incremental, so you must apply each delivered ones.  
>The license update procedure is the same for a Nomadic or a Fixed license.  
>If you install a license update on a machine where SCANeR is installed an internet connection is not required, otherwise it is.  
>For Nomadic license only: We recommend to apply a dongle update on a machine where SCANeR is installed. If you need to apply a license update from a computer where SCANeR is not installed then you must first make sure that the license’s driver is installed. To do so, try to access to the [SACC](http://localhost:1947) on the machine. If you cannot access to the SACC then the dongle’s driver must be installed on the machine before to start (administrator privileges are required).  
>For Fixed license only: The dongle update procedure must be followed on the software licenses’ server where the software license has been installed.  

#### Step 1. Receive the new license 

1. Open your favorite mail service, you should receive and email from [support-scaner](mailto:support-scaner@avsimulation.fr)
![](./assets/support-scaner_email.png)
2. Download the `V2C` file attached to this mail, and save it on your computer.
First step is done, pretty easy 👍
>**Note:**
>`V2C` means Vendor To Client. On the other hand, `C2V` means Client To Vendor. 

#### Step 2. Open the web service (SACC) 

1. Open your favorite internet browser, and write the following address: [http://localhost:1947](http://localhost:1947). You should be on the license service : Sentinel Admin Control Center
![](./assets/SACC.png)
This webpage is where you can manage SCANeR license, you can visualize which licenses are recognize by your computer and if they`re used.

2. If your license is a Nomadic one, plug the USB dongle in your computer. You can check if your dongle is plugged by clicking on `Sentinel Keys`
![](./assets/DonglePlugged.png)
If you have several dongle plugged in your computer, you can make them blink to identify which is which 🤩

3.  Click on `Update/Attach`, you`ll be redirected on the following page:
![](./assets/UpdateLicense.png)

#### Step 3. Apply the update to your license

1. Click on `Browse` button, and selected the previously saved V2C file.
2. Then click on `Apply File`
![](./assets/UpdateLicense.png)

Congratulations ! 💪  
Your license is now updated, you can ejoy your new SCANeR products ! 😊

#### Having troubles

##### Common mistakes
If for any reason you have applied a license update and the `Update/Attach` page shows an error it could be:
|Error           	 |Diagnostic                     |
|--------------------|-------------------------------|
|HASP_UPDATE_TOO_OLD |This means that this V2C file has already been installed. In most cases there is no license problem when you see this error. To make sure that everything is fine check the license details currently installed on the key: [SACC Features](http://localhost:1947/_int_/features.html). If  the  details  don`t  match  what  you  expect  check  your  e-mails  from [support-scaner@avsimulation.fr](mailto:support-scaner@avsimulation.fr) and see if you already have a more recent V2C file. After checking these points if you still face an issue please generate and send a C2V file to [support-scaner@avsimulation.fr](mailto:support-scaner@avsimulation.fr).|
|HASP_UPDATE_TOO_NEW |This  means  that  a  previous  V2C  file  for  the  protection  key  has  not  yet  been installed. V2C files need to be installed in the order in which they are provided. To solve this problem first install the missing updates for the key(check e-mails from [support-scaner@avsimulation.fr](mailto:support-scaner@avsimulation.fr)).If you do not have the previous V2C license update file(s) then please generate a new C2V file and sent an email with the problem description and the C2V file to [support-scaner@avsimulation.fr](mailto:support-scaner@avsimulation.fr).|
|HASP_KEYID_NOT_FOUND|This  means  that  the  related  license  of  the  update  file  was  notfound  on  the machine from where you apply the update.To solve this problem,ensure the correct physical license is plugged or you are on the machine where the software license has been installed.|
|OTHERS				 |For all other errors please generate a new C2V fileand sent an email with the problem description and the C2V file to [support-scaner@avsimulation.fr](mailto:support-scaner@avsimulation.fr).|

##### Generates a C2V file
###### Step 1. Launch the tool
Find in `%STUDIO_PATH%/third party/` the service `RUS_QAKOG.exe`. You must launch it as **Administrator**
###### Step 2. Create your C2V file
Go to tab `Collect Key Status Information` and click on `Collect information` button
![](./assets/GenerateC2V.png)
###### Step 3. Share it!
Once the C2V is generated, rename it (e.g. `Your_Company.C2V`) and send it to [support-scaner](mailto:support-scaner@avsimulation.fr).