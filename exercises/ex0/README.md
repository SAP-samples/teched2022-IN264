# Overview

In this exercise, you will test the access to the SAP Business Platform environment and validate the configuration for your SAP BTP subaccount which will be used throughout the session.

## Validate system access

System / user details:

| Assigned subaccount|Platform user 👷‍♂️(BTP Admin)/Password|Business User 👩‍💼(Task Approver)/Password|
| ------------- |-------------| -----|

**XX = assigned participant number from the speaker team**

1. Access SAP BTP Cockpit using the URL below:

[SAP BTP Cockpit](https://cockpit.eu10.hana.ondemand.com/cockpit/?idp=tdcteched3.accounts.ondemand.com#/globalaccount/62d9c33d-1b44-4afa-9751-2cb0165ba817)

Login with the BTP platform credentials (Platform User) for the pre-created BTP subaccount. 
![](/exercises/ex0/images/btp_ga_login.png)

Access the respective subaccount (name: IN264-xx)
![](/exercises/ex0/images/btp_ga_view.png)
2. Login using the platform user credentials.
![](/exercises/ex0/images/Ex0-1.png)

3. Access the respective subaccount (name: IN264-XX where XX is your assigned user number)
![](/exercises/ex0/images/btp_ga_view.png)

4. From the left-hand navigation choose **"Security > Trust Configuration"** and validate that IAS tenant **"tdcteched3"** is set as custom Identity Provider for applications.
![](/exercises/ex0/images/trust_check.png)

5. Confirm Cloud Foundry environment is enabled for your subaccount.  Click **Cloud Foundry >> Spaces** and confirm that **dev** space is visible.
![](/exercises/ex0/images/cf_check.png)

6. Click **Services >> Instance and Subscriptions** and confirm that you have subscription to the **Launchpad Service**.
![](/exercises/ex0/images/lp_check.png)

## Get required additional files to perform this "Hands-On" successfully

1.  Click on the link below to download a zip file containing additional resources that you will need for later exercises.
[IN264_Resources](https://github.com/SAP-samples/teched2022-IN264/raw/main/exercises/IN264-Resources.zip)

2. Confirm that **IN264-Resources.zip** file is in the downloads folder.
![](/exercises/ex0/images/Ex0-2.png)

3. Right click on **INS264-Resources.zip** and choose **Extract All...** from the context menu.
![](/exercises/ex0/images/Ex0-3.png)

4. Extract the file under the Windows downloads folder.
![](/exercises/ex0/images/Ex0-4.png)

5. Access the IN264-Resources folder and confirm that you see the files and folders shown in the screenshot.  You will need this content for later exercises.
![](/exercises/ex0/images/Ex0-5.png)

> ⚠ In case something is missing in your subaccount set up, please reach out to your session instructors 👩‍🏫.
## Summary

🎉Congratulations! With this first exercise you have successfully validated access to your subaccount and required setup of your BTP subaccount.
Now continue now to the next exercise [Exercise 1 - Enable SAP Task Center](../ex1/README.md)
