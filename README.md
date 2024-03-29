[![REUSE status](https://api.reuse.software/badge/github.com/SAP-samples/teched2022-IN264)](https://api.reuse.software/info/github.com/SAP-samples/teched2022-IN264)

# IN264 - Enable, Configure, and Integrate a Central Inbox on SAP BTP

## Description

This repository contains the material for the SAP TechEd 2022 session "IN264 - Enable, Configure, and Integrate a Central Inbox on SAP BTP."

## Overview

These Hands-On exercises will guide you in setting an end-to-end scenario with SAP Task Center and connecting different task providers.

## Scenario

In this Hands-On we will integrate two "Task Providers":

- SAP S/4HANA
- SAP Build Process Automation

In addition other BTP components are used and will be configured for successfully running this scenario end-to-end.

![SAP BTP Solution Diagram - SAP Task Center](images/0_btp_taskcenter_teched_scenario.png)

## Requirements

In order to follow the exercises in this repository, you should have knowledge about:

- [SAP Business Technology Platform concepts](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/73beb06e127f4e47b849aa95344aabe1.html)
- [SAP Launchpad service](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/9db48fa44f7e4c62a01bc74c82e74e07.html)
- [SAP Cloud Identity Services](https://help.sap.com/docs/SAP_CLOUD_IDENTITY)

> **NOTE:** *SAP Launchpad Service* is part of the SAP Build portfolio. In early 2023, we launch a new experience with the new name **SAP Build Work Zone, standard edition**. You can learn more in the [Roadmap Explorer](https://roadmaps.sap.com/board?PRODUCT=73554900100800003081&PRODUCT=73555000100800002781&range=CURRENT-LAST#Q3%202022). Please be aware that some screenshots or systems in this Hands-on material might still contain the former name *SAP Launchpad Service*.
> <p align="center"><img src="./images/sap-build-work-zone.jpg" width="65%" /></p>

## Exercises

- [Getting started & check your hands-on environment ](exercises/ex0/README.md)

- [Exercise 1 - Enable SAP Task Center](exercises/ex1/README.md)
    - [Exercise 1.1 - Enable SAP Task Center manually](exercises/ex1/README.md#exercise-11-enable-sap-task-center-manually)
    - [Exercise 1.2 - (Alternative) Run the BTP Booster for setting up SAP Task Center](exercises/ex1/README.md#exercise-12-run-the-sap-task-center-booster-for-your-reference-only---skip-this-exercise-and-proceed-exercise-13)
    - [Exercise 1.3 - Integrate the SAP Task Center service into SAP BTP Launchpad service](exercises/ex1/README.md#exercise-13-integrate-the-sap-task-center-service-into-sap-btp-launchpad)
    - [Exercise 1.4 - Enable Single-Sign-On (SSO) for SAP Task Center](exercises/ex1/README.md#exercise-14-enable-single-sign-on-sso-for-sap-task-center)
    - [Summary](exercises/ex1/README.md#summary)
- [Exercise 2 - Integrate SAP S/4HANA on-premise as a task provider](exercises/ex2/README.md) 
    - [Exercise 2.1 - Create SAP S/4HANA Destination](exercises/ex2/README.md#exercise-21-create-sap-s4hana-destination)
    - [Exercise 2.2 - Check SAP S/4HANA connectivity via Task Center Admin app](exercises/ex2/README.md#exercise-22-check-sap-s4hana-connectivity-via-task-center-admin-app)
    - [Exercise 2.3 - Update user UUID in SAP S/4HANA](exercises/ex2/README.md#exercise-23-update-user-uuid-in-sap-s4hana)
- [Exercise 3 - Integrate SAP Build Process Automation as task provider](exercises/ex3/README.md)
    - [Exercise 3.1 - Create SAP Build Process Automation Destination](exercises/ex3/README.md#exercise-31-create-the-destination-to-the-sap-process-automation-instance-from-a-remote-subaccount)
    - [Exercise 3.2 - Check SAP Build Process Automation connectivity via Task Center Admin app](exercises/ex3/README.md#exercise-32---check-sap-build-process-automation-connectivity-via-task-center-admin-app)
    - [Exercise 3.3 - Execute the API request to start a SAP Build Process Automation process](exercises/ex3/README.md#exercise-33---execute-the-api-request-to-start-a-sap-build-process-automation-process)
- [Exercise 4 - Check the Workflow as business user (task approver) 👩‍💼](exercises/ex4/README.md#exercise-4---check-the-task-workflow-as-business-user-task-approver-👩‍💼)

- [Exercise 5 - Connect SAP Mobile Start 📱](exercises/ex5/readme.md) 

- [Demo: BTP Setup Automator](https://github.com/SAP-samples/btp-setup-automator)
- [Additional resources](exercises/additional/README.md)

## How to obtain support

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../issues) tab.

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
