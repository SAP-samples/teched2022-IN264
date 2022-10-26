# Overview

In this exercise, you will test access to the SAP Business Platform environment and validate the configuration for your SAP BTP subaccount which will be used throughout the session.

## Validate system access

System / user details:

| Assigned subaccount|Platform user 👷‍♂️(BTP Admin)/Password|Business User 👩‍💼(Task Approver)/Password|
| ------------- |-------------| -----|
| IN264-xx| IN264-xx-P/Welcome123| IN264-xx/Welcome123|

**xx = assigned participant number from the speaker team**

Please enter the SAP BTP Cockpit URL using the **Platform** user:

[SAP BTP Cockpit](https://cockpit.eu10.hana.ondemand.com/cockpit/?idp=tdcteched3.accounts.ondemand.com#/globalaccount/62d9c33d-1b44-4afa-9751-2cb0165ba817)

Login with the BTP platform credentials (Platform User) for the pre-created BTP subaccount. Access the respective subaccount (name: IN264-xx)
![](/exercises/ex0/images/btp_ga_view.png)


To ensure the successful execution, please validate the trust setup.
From the left-hand navigation choose **"Security > Trust Configuration"**

Please validate that IAS tenant **"tdcteched3"** is set as custom Identity Provider for applications.

![](/exercises/ex0/images/trust_check.png)

Furthermore, please validate that Cloud Foundry environment is enabled for your subaccount. Within Cloud Foundry you should be able to access Cloud Foundry Space **"dev"**

![](/exercises/ex0/images/cf_check.png)

And also check that **Launchpad Service** application is subscripted in your subaccount.

![](/exercises/ex0/images/lp_check.png)

> ⚠ In case something is missing in your subaccount set up, please reach out to your session instructors 👩‍🏫.

## Summary

🎉Congratulations with this first exercise you have successfully validated access to your subaccount and required setup of your BTP subaccount:
Continue now to the next exercise "Run the BTP Booster for setting up SAP Task Center"- [Exercise 1 - Exercise 1 Description](../ex1/README.md)
