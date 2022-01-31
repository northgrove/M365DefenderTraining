# Microsoft 365 Defender Training Workshop

Attendees will get an opportunity to try their hands at configuration, detection and security analysis using MS tools such as the Defender XDR products and Azure Sentinel.
The workshop is aimed at security analysts and technical staff looking to learn or get more out of the security consoles provided within the Microsoft E5 suite.
Best Practices for configuration of Defender for Endpoints, Defender for Office and Cloud App Security will be covered, as well as analysis and mitigation of real attack scenarios.
<br>
<br>
The workshop is created by Kent Husvik and Kjetil Nordlund from Microsoft Norway. 

<br>
<br>
<br>

## Preparation and prerequisites
---
There will be required to do some necessary preparation in forehand of attending the workshop. 

During the workshop you must have access to a trial environment not used before.   
<b>This should not in any circumstances be an existing production environment</b>

<br>
Pre-requisite for completing the LAB/Course there is a requirement for having access to two Machines.  

One for accessing the Portals and another for testing purposes.  

For Portal Access you will need a supported Browser installed, Microsoft Egde (Chomium based) or Google Chrome is supported, Firefox can work but is not supported.   

<h4>For completing LAB/Tests a Windows 10/11 Pro or Enterprise is required. The machine must be newly installed physical machine or Virtual machine (Local, ESXI, Hyper-V etc.) The machine is going to be enrolled in to Intune (MDM), make sure to not domain join or adding the machine to any other MDM tool before the course.  </h4>

Make sure that **no sensitive or critical information** is stored on your LAB machine, and that it's **not part of any production environment**. After the LAB this machine should be deleted and scraped.

<br>
<br>

### Registration of an trial tenant
---
Create a New Email account, like Outlook.com or any other that you like.  
Create a [M365 E5 Trial](https://signup.microsoft.com/Signup?OfferId=f6f20264-e785-4749-bd8e-884bab076de4&ali=1) and connect it to the newly created Email account  
Use the newly created email account in the registration form  
  

![trial1](./img/trial1.png)  
![trial2](./img/trial2.png)  
![trial1](./img/trial3.png)  
![trial1](./img/trial4.png)  
![trial1](./img/trial5.png)  
![trial1](./img/trial6.png)  


Complete the wizard.  
Click on Get Started complete the steps required on Data storage location. If any service error message are being displayed, wait a few minutes on the backend provisioning and try again.  
<br>
<br>

### Security Console Welcome wizard
---
Navigate in a supported browser to [Security.microsoft.com](https://security.microsoft.com) and complete the wizard.  
Make sure you are loged in with the user you just created a trial teant with.  

Browser requirements: https://docs.microsoft.com/en-us/microsoft-365/security/defender-endpoint/minimum-requirements?view=o365-worldwide  
<br>
<br>

### Turn on preview features and other features
---
Turn on the preview experience setting to be among the first to try upcoming features.
1.	In the navigation pane, select Settings > Endpoints > Advanced features > Preview features.  
   ![preview](./img/preview1.png)
   ![preview](./img/preview2.png)  <br>

2.	Toggle the setting between On and Off and select Save preferences.
3.	Reload the console and find your way back to Settings > Endpoints > Advanced features 
4.	Activate all features Except “Restrict correlation to within scoped device groups”

<br>
<br>

### Turn on auditing
---
1.	If auditing is not turned on for your organization, you can turn it on in the Microsoft 365 compliance center or by using Exchange Online PowerShell. It may take several hours after you turn on auditing before you can return results when you search the audit log.
2.	Use the compliance center to turn on auditing
3.	Go to compliance.microsoft.com and sign in.
4.	In the left navigation pane of the Microsoft 365 compliance center, click Audit.
5.	If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.  
![audit](./img/audit.png)  
7.	Click the Start recording user and admin activity banner.
8.	It may take up to 60 minutes for the change to take effect.

<br>
<br>

### Test users and groups
---
Create at least three regular users in your Azure AD tenant in addition to your Global Administrator user created when activated the tenant.  
Create at least three Azure AD groups in your Azure AD tenant.
<br>
<br>

### Turn of Security Defaults
---
To be able to test Conditional Access policies, the default enabled “Security Defaults” need to be turned off first.
Disabling Security Defaults: https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults    
  
![SecurityDefaults](./img/securitydefaults.png)  
To disable security defaults in your directory:
1.	Sign in to the Azure portal as a security administrator, Conditional Access administrator, or global administrator.
2.	Browse to Azure Active Directory > Properties.
3.	Select Manage security defaults.
4.	Set the Enable security defaults toggle to No.
5.	Select Save.

<br>
<br>

### Enable Basic Conditional Access Policies
---
To maintain the security level in your Azure AD tenant, create one Conditional Access policy enforcing MFA for all your users.  
NB! Make sure your Global Admin users (and other test users) is enrolled with MFA information before you activate MFA requirement for all users.
https://mysignins.microsoft.com/security-info   
  
Follow these steps to create a Conditional access policy requiring MFA for all users:   
https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa#create-a-conditional-access-policy  

In addition, create one Conditional Access policy to block use of all Legacy authentication protocols in your tenant.
