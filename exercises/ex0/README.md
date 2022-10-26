# Overview

In this exercise, you will test access to the SAP Business Platform environment and validate the configuration for your SAP BTP subaccount which will be used throughout the session.

## Validate system access

System / user details:

| Assigned subaccount|Platform user 👷‍♂️(BTP Admin)/Password|Business User 👩‍💼(Task Approver)/Password|
| ------------- |-------------| -----|
| IN264-XX| IN264-XX-P/Welcome123| IN264-XX/Welcome123|

**XX = assigned participant number from the speaker team**

1. Access SAP BTP Cockpit URL using the URL below:

[SAP BTP Cockpit](https://cockpit.eu10.hana.ondemand.com/cockpit/?idp=tdcteched3.accounts.ondemand.com#/globalaccount/62d9c33d-1b44-4afa-9751-2cb0165ba817)

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

7.  Click on the link below to download a zip file containing additional resources that you will need for later exercises.

[IN264_Resources](https://github.com/SAP-samples/teched2022-IN264/raw/main/exercises/IN264-Resources.zip)

8. 

> ⚠ In case something is missing in your subaccount set up, please reach out to your session instructors 👩‍🏫.

## Summary

🎉Congratulations with this first exercise you have successfully validated access to your subaccount and required setup of your BTP subaccount:
Continue now to the next exercise "Run the BTP Booster for setting up SAP Task Center"- [Exercise 1 - Exercise 1 Description](../ex1/README.md)
