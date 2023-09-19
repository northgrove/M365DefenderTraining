# Microsoft Defender Evaluation lab



If you are going to use the Evaluation LAB machine as your test machine, you need to disable NLA.To be able to Add the machine to Azure AD and Endpoint Manager – *NB! Only needed for VM in Azure or Evaluation LAB*.

  
**DISABLE NETWORK LEVEL AUTENTICATION (NLA) – NOT RECOMMENDED IN PRODUCTION**
Open Remote Desktop and Log in to the device with the Provided Username and Password.

Run this powershell script in and administrator elevated powershell prompt:
```
Write-Output 'Configuring registry to disable Network Level Authentication (NLA).'
$path = 'HKLM:\SYSTEM\CurrentControlSet\Control\Terminal Server\WinStations\RDP-Tcp'
Set-ItemProperty -Path $path -Name SecurityLayer -Type DWord -Value 0
Set-ItemProperty -Path $path -Name UserAuthentication -Type DWord -Value 0
Set-ItemProperty -Path $path -Name fAllowSecProtocolNegotiation -Type DWord -Value 0
Write-Output 'Restart the VM for the change to take effect.'
```
Reboot the machine


**RUN A EVALUATION LAB TEST SCENARIO**
In the evaluation lab page select the “Simulations” pane
Click “Create simulation”

![EvalLAB](../img/simul1.png)

Choose:  
AttackIQ and Persistence methods as the simulation, and run it on your lab machine
Click “Create simulation”


**LAB SIMULATION QUESTION**

*ATTACKIQ - PERSISTENCE METHODS*
1.	What is the IP from where the RDP brute-force happened?
2.	Describe the changes made to file association on the computer?
3.	What script language executable was used to run the commands?
a.	What was the name of the script file?
4.	What is the Registry key, Value name, value data and value tape for the registry changed for logon script registration?
a.	What was the previous values?
5.	Which URL does ai_exec_server.exe connect to?
6.	What is the InitiatingProcessCommandLine for the process creating the attackiq_appcert_dll.dll file?
7.	What is the remote IP and URL that pyhton.exe establishes an outbound connection to?

*SAFEBRACH AND KNOWN RANSOMWRE INFECTION:*
1.	What is the original name of the initial file first run with malware to the computer?
a.	What kind of malware was detected?
2.	What is the IP and TCP port to the host the SafeBreach simulator is connecting to?
3.	What is the name of the activity group associated to this attack?
4.	What is the filename for the WannaCrypt ransomware detected?
a.	What is the Virus Total ratio for this file?
