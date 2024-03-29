# Defender for Endpoint

## Setup and Configuration

Pre-requisite for testing Defender for Endpoint is that you have a Newly installed Virtual machine or physical machine (Local, ESXI, Hyper-V etc.). 

If you don’t have a machine you can use the Microsoft Defender Evaluation lab and provision a Windows client there. Look in Module 6 to find a walkthrough.

### Intune integration and configuration policies

Open the Endpoint manager console with the URL – https://endpoint.microsoft.com

![Endpoint](../img/endpoint.png)

**Security Baselines**

1.	Navigate to Endpoint Security, click on Security Baselines - > Click "Security Baseline for Windows 10 and later" .
2.	Click on Create profile.
3.	Provide a Name and Click Next

 ![securitybaseline](../img/securitybaseline.png)

4.	Click Next on configuration settings
5.	Click Next on Scope tags
6.	Click Next on Assignments (dont add any users/devices)
7.	Click Create.


**Security Policies**

1.	Navigate to Endpoint Security, click on Antivirus
2.	Click Create Policy
3.	In the Dropdown box select Windows 10 and later
4.	Windows Security Experience and Click Create
5.	Provide a Name and Click Next
6.	Make Sure the following is enabled (Tamper Protection and Hide Family Options)

 ![Tamperprotection](../img/tamper%20protection.png)

7.	Click Next on Configuration settings
8.	Click Next on Scope tags
9.	On Assignments - Click "Add all users" - Click Next
10.	Click Create

Back in the Console

1.	Click Create Policy
2.	In the Dropdown box select Windows 10 and later
3.	Microsoft Defender Antivirus and Click Create
4.	Provide a Name and Click Next
5.	Make sure the following is enabled.

 ![AntivirusSettings](../img/AntivirusSettings.png)

 ![AntivirusSettings](../img/AntivirusSettings1.png)

 ![AntivirusSettings](../img/AntivirusSettings2.png)
  
6.	Click Next on Configuration settings
7.	Click Next on Scope tags
8.	On Assignments - Click "Add all users" - Click Next
9.	Click Create

**Endpoint Detection and Response**

Go to "Microsoft Defender for Endpoint" in the Endpoint Security menu

Make sure to enable at least "Connect Windows Devices version 10.0.15063 and above to Microsoft Defender for Endpoint" and "Allow Microsoft Defender for Endpoint to enforce Endpoint Security Configurations"

Include also any other settings you may want to test out later

![EnableMDE](../img/enableMDE.png)

Click "Save"

**Endpoint Detection and response policy**
1.	Navigate to Endpoint Security, click on Endpoint Detection and Response
2.	Click Create Policy
3.	In the Dropdown box select Windows 10 and later
4.	Select Endpoint Detection and Response Click Create
5.	Provide a Name and Click Next
6.	Select the following and click Next
![EDR Policy](../img/MDE-EDRPolicy.png)
8.	Click Next on Configuration settings
9.	Click Next on Scope tags
10.	On Assignments - Click "Add all users" - Click Next
11.	Click Create

**Attack surface reduction**
1.	Navigate to Endpoint Security, click on Attack Surface Reduction 
2.	Click Create Policy
3.	In the Dropdown box select "Windows 10, Windows 11 and Windows Server"
4.	Select Attack Surface Reduction Rules, Click Create
5.	Provide a Name and Click Next
6.	Select the following and click Next
 ![ASR-policy](../img/ASR-policy.png)
7.	Click Next on Configuration settings
8.	Click Next on Scope tags
9.	On Assignments - Click "Add all users" - Click Next
10.	Click Create

