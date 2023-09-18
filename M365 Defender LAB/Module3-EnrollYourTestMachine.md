# Enroll Your Test machine to Intune

Verify that autoenrollment in Azure AD is enabled: Azure Active Directory > Mobility (MDM and MAM) > Microsoft Intune
 ![MDM-Scope](../img/MDM-Scope.png)
Set ”MDM user scope” to all. Click Save

Login to your testmachine with “Administrator1” and the provided password.

Go to: Start -> Settings -> Accounts -> Access Work or School
Click “Connect”
 ![AAD-Join](../img/AAD-join.png)
Make sure to click on ”join this device to Azure Active Directory”

Enter the email address to your first Azure AD account, and login
  ![AAD-Join](../img/AAD-join2.png)
Click join
Click done
  ![AAD-Join](../img/AAD-join3.png)
Verify that your computer is connected to your environment (both Azure AD and Intune)

Restart your computer

![AAD-Join](../img/AAD-join4.png)
Login to the computer with your first Azure AD account
To be able to login you must type azuread\ in front of your email address

Wait for intune configuration profiles to be delivered
