# Enable SAP Task Center service on SAP Business Technology Platform

In this exercise, you will manually setup SAP Task Center service on your subaccount to enable SAP Task Center.  
> ℹ It is also possible to run a booster in SAP BTP cockpit to setup SAP Task Center, but this procedure is not in the scope of this hands-on.  For your reference, steps to setup SAP Task Center using a booster can be found [here](#exercise-12-execute-the-sap-task-center-booster-for-your-reference-only---skip-this-exercise-and-proceed-exercise-13).  
After SAP Task Center is enabled in your BTP subaccount we will configure the SAP Launchpad service running on SAP BTP to integrate the SAP Task Center apps.
Finally we will configure "Single-Sign-On" (SSO) for the end user to get the access to the SAP Task Center Web app without need of using basic authentication.

Content in this exercise:

- [Enable SAP Task Center manually](README.md#exercise-11-enable-sap-task-center-manually)
- [Run the BTP Booster for setting up SAP Task Center](README.md#exercise-12-run-the-sap-task-center-booster-for-your-reference-only---skip-this-exercise-and-proceed-exercise-13)
- [Integrate the SAP Task Center service into SAP BTP Launchpad](README.md#exercise-13-integrate-the-sap-task-center-service-into-sap-btp-launchpad-service)
- [Enable Single-Sign-On (SSO) for SAP Task Center](README.md#exercise-14-enable-single-sign-on-sso-for-sap-task-center)
- [Summary](README.md#summary)

## Exercise 1.1 Enable SAP Task Center manually

To ensure that the BTP subaccount is well prepared we need to check the availability of the following BTP services:

- [SAP Task Center](https://discovery-center.cloud.sap/serviceCatalog/sap-task-center?region=all)
- [SAP BTP Launchpad](https://discovery-center.cloud.sap/serviceCatalog/launchpad-service?region=all)

Please perform the following steps to validate the required entitlements:

1. Enter your SAP BTP subaccount and choose the **Entitlements** entry from the left hand navigation.

2. Search for "Task Center" to ensure the service is entitled for the subaccount:
<br>![](/exercises/ex1/images/manual_check_stc_entitlem.png)

3. Additional search for "Launchpad" to validate also that this service is entitled for the subaccount.
<br>![](/exercises/ex1/images/manual_check_lp_entitlem.png)

After all prerequisites are met, we can now start to setup SAP Task Center.

> ℹ The enablement of CloudFoundry was already performed before.

Switch now to **Instances and Subscriptions**  to get started (you will identify **SAP Launchpad Service** is already subscribed) press now the **Create** button:

<br>![](/exercises/ex1/images/start_create_sub_and_instances.png)

2.  To create the Task Center instance click on the **Create** button and select the SAP Task Center service.
    Please specify an "Instance Name" and create the instance:

  <br>![](/exercises/ex1/images/stc_inst_create.png)

  Afterwards the creation starts similar to the SAP BTP Launchpad:

  <br>![](/exercises/ex1/images/stc_inst_create_prc.png)

  And should be finished after a couple of minutes:

  <br>![](/exercises/ex1/images/stc_inst_create_success.png)


3. (Optional) If you want to call the [SAP Task Center API](https://api.sap.com/package/SAPTaskCenter/rest) for example via Postman you need to create a "Service Key":

  <br>![](/exercises/ex1/images/stc_inst_create_sk.png)

The last step for this exercise is now to create a new destination to integrate SAP Task Center in the BTP Launchpad.

### Create a destination to get SAP Task Center HTML5 apps

1. Please switch to the **Destinations** menu entry:

  <br>![](/exercises/ex1/images/destination.png)

2. We will now create a new destination for the integration of SAP Task Center into the SAP BTP Launchpad. In the Destination Configuration section choose **Service Instance** and add the following:  

| Property | Value |
| ------------- |-------------|
| Service Instance:| ***Name from the previous created "Service Instance"***|
| Name:| ***sap_task_center_lp***|
| Description: | ***Description of your choice***|

  <br>![](/exercises/ex1/images/stc_dest_lp_int.png)
  
  Switch now to **Security > Role Collection**. 

### Create and assign authorization 

3. To get access to the SAP Task Center Admin application we need to create a new **Role Collection**:

  <br>![](/exercises/ex1/images/create_rc.png)

  Choose **Edit**:

  <br>![](/exercises/ex1/images/edit_rc.png)
  
  Assign now the following roles: 

  - **TaskCenterAdmin**
  - **TaskCenterTenantOperator**

  Save your changes:

  <br>![](/exercises/ex1/images/assign_roles.png)


4. Finally assign this new **Role Collection** to your **Business User** (without "-P"), switch to **Users**, select the user and assign the new **Role Collection**:

  <br>![](/exercises/ex1/images/assign_rc.png)
  
  If you switch now back to the **Role Collection**, the assignment should now look like this:

  <br>![](/exercises/ex1/images/rc_assigment_check.png)

**Congratulations**! You've now completed all necessary steps for the initial setup of SAP Task Center. In the next [exercise](README.md#exercise-13-integrate-the-sap-task-center-service-into-sap-btp-launchpad) we will learn how to access the SAP Task Center applications by setting up the SAP Launchpad Service.

## Exercise 1.2 Run the SAP Task Center Booster (*for your reference only - skip this exercise and proceed Exercise 1.3*)

> ⚠ For TechEd session IN264 please skip this exercise and proceed with [Exercise 1.3 Integrate the SAP Task Center service into SAP BTP Launchpad](#exercise-13-integrate-the-sap-task-center-service-into-sap-btp-launchpad) It's possible to setup SAP Task Center using a booster, but this requires admin access to the Global Account.  This access is not available to the participants in the TechEd systems so the steps below are for your reference only and can only be performed in your own system environment where you might have SAP BTP Global Account Admin privileges.

1. To run the SAP BTP booster for SAP Task Center , choose from the left-hand navigation (ensure that you are on the BTP Global Account level and not inside the SAP BTP subaccount):

    <br>![](/exercises/ex1/images/booster01.png)

2. Search now by typing **"Task Center"** for the SAP BTP booster and press the **Start** button on the tile:

    <br>![](/exercises/ex1/images/booster02.png)

    In the upcoming window, you should now get the result from the prerequisite check, this must be passed (if not please inform the TechEd session team):

    <br>![](/exercises/ex1/images/booster03.png)

3. Press the **Next** button in the lower right corner to move to the next phase of the BTP Booster.
  In this step verify the used and entitled services (SAP Launchpad service and SAP Task Center), select the BTP subaccount and press the **Next** button.
  The SAP Task Center setup will be executed in this subaccount: 
  
  <br>![](/exercises/ex1/images/booster04.png)

4. In the last step check again the subaccount and start the execution by finally pressing **Finish**.

    <br>![](/exercises/ex1/images/booster05.png)

    In the upcoming screen you should now see the execution of the different actions and the status:

    <br>![](/exercises/ex1/images/booster06.png)

After the successful execution you get a popup with the option to configure the destinations or to jump in the SAP Help documentation.

<br>![](/exercises/ex1/images/booster07.png)

Pleas click on the first link to enter your subaccount. 

<br>![](/exercises/ex1/images/destinations_overview.png)

**Congratulations**! With the successful execution of this exercise we can now go further with the SAP Task Center integration by setting up the Launchpad service to access the SAP Task Center application.

## Exercise 1.3 Integrate the SAP Task Center service into SAP BTP Launchpad service

In the upcoming exercise we will add the SAP Task Center apps to your SAP BTP Launchpad, you can find [here](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/3a499676e7ae4282af84092f778e3737.html#procedure) also the official SAP Help documentation for more details. 

1. To get started select from the SAP BTP cockpit, got to the **Instances and Subscriptions** entry from the BTP navigation, by clicking the icon you will enter the site manager to configure the SAP Launchpad service:

<br>![](/exercises/ex1/images/lp_site_manager_access.png)

2. In the next step click on the **Channel Manager** icon and refresh the "HTML5 Apps" channel by clicking the refresh icon:

    <br>![](/exercises/ex1/images/lp_site_manager_channel_manager_refresh.png)

   The status should be changed to "updating" and then finally "updated":

    <br>![](/exercises/ex1/images/lp_site_manager_channel_manager_updating.png)

    To validate that the SAP Task Center apps are now available we'll check the "Content Manager":

    <br>![](/exercises/ex1/images/lp_site_manager_main_page.png)

4. In the upcoming screen select the second tab (Content Explorer) and click on the **HTML5 Apps** tile:

    <br>![](/exercises/ex1/images/lp_site_manager_content_manager.png)

    <br>![](/exercises/ex1/images/lp_site_manager_html5_apps.png)

    As a result you should now see two entries/apps:

    - Task Center
    - Task Center Administration

    <br>![](/exercises/ex1/images/lp_site_manager_content_manager_stc-apps.png)

5. Select now all entries and press the **Add to My Content** button. 
   If you now select the first tab to validate the result, you should now identify the Task Center apps are added to the items list:

    <br>![](/exercises/ex1/images/lp_site_manager_my_content.png)

6. The last step is now to create a group and the apps to the pre-defined "Everyone" role ([SAP Help documentation](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/baeaf6ee364e48ac95dc09470281f174.html)).

7. To enable the visibility of the SAP Task Center apps in the BTP Launchpad we need to create a new **Group** in the **Content Manager**.
   You can add new content by clicking the **+ New** button afterwards select **Group**:

    <br>![](/exercises/ex1/images/lp_site_manager_create_group.png)

   Provide a title, description and click (**Important**) in input field in the upper right corner, you will otherwise not see the apps. Finally press for each app the **+** button and save your changes:

    <br>![](/exercises/ex1/images/lp_site_manager_group_add_apps.png)

8. Assign now the SAP Task Center apps to "everyone" role, if you want to create an own "custom" role have a look in the [official SAP Help documentation](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/baeaf6ee364e48ac95dc09470281f174.html) to follow the required steps.

    <br>![](/exercises/ex1/images/lp_site_manager_role_add_apps.png)

9. The last step is now to create the SAP Launchpad site by creating a new **site** in the **Site Manager**.
    Please navigate to the **Site Directory** in order to do this: 

    <br>![](/exercises/ex1/images/lp_site_manager_site_directory.png)

10. Create a "new" site:

    <br>![](/exercises/ex1/images/lp_site_manager_site_directory_new_site.png)

11. Afterwards you will be able to see all settings for your newly created SAP Launchpad site. In order to access the "SAP Task Center" as business user (task approver), please open the URL in "Incognito"-mode browser session or logout all your sessions for the platform user (BTP Admin):

    <br>![](/exercises/ex1/images/lp_site_manager_site_edit.png)

> ℹ You can also bookmark the URL for your Launchpad site for later reference.

12. After providing the credentials of the "**business user**" you should now identify the "Task Center tiles":

    <br>![](/exercises/ex1/images/lp_site_launch.png)

13. By entering the first (Task Center) tile you should now see the (empty) SAP Task Center application:

    <br>![](/exercises/ex1/images/tc_final.png)

14. (optional) by changing the theme of your BTP launchpad site you can also adapt the site to the new "**SAP Horizon Theme**". 

    Select the settings from your profile (upper right corner) and select "**Settings**":

    <br>![](/exercises/ex1/images/theme_01.png)

    Choose now one of the available "Horizon" themes: 

    <br>![](/exercises/ex1/images/theme_02.png)

    And check the result (example: SAP Evening Theme):

    <br>![](/exercises/ex1/images/theme_03.png)

**Congratulations**! with this you can now access the SAP Task Center applications via the SAP BTP Launchpad service. 
In the next exercise we will configure "Single-Sign-On" (SSO) with SAP Cloud Identity Services.


## Exercise 1.4 Enable Single-Sign-On (SSO) for SAP Task Center

To enable SSO we need to enter the "profile" page from the SAP Cloud Identity services tenant:

URL: https://tdcteched3.accounts.ondemand.com

User: IN264-xx (xx = your assigned number)

Password: Welcome123

<br>![](/exercises/ex1/images/user_profile_logon.png)

Click on the "Generate" Button:

<br>![](/exercises/ex1/images/user_profile_generate_cert.png)

Specify a password:

<br>![](/exercises/ex1/images/user_profile_cert_pw.png)

Afterwards a download of the "new" certificate will start, please store the file in a known place at the file system and **open** (double click) the file.
In the upcoming wizard proceed through all steps without changing the defaults:

<br>![](/exercises/ex1/images/user_profile_cert_import1.png)

Provide here also the password which you have defined before and import the certificate:

<br>![](/exercises/ex1/images/user_profile_cert_import2.png)

By entering now the SAP BTP Launchpad site URL you should now able to select a certificate:

<br>![](/exercises/ex1/images/cert_based_logon.png)

And now you have successfully logged on to the BTP Launchpad site with the SAP Task Center applications:

<br>![](/exercises/ex1/images/cert_based_logon_lp.png)

**Congratulations**! Now that you have completed the last step, you have finished the entire "[Exercise 1](README.md)" after completing this last step.
You can now switch back to main page of the hands-on or directly start with "[Exercise 2](../ex2/README.md)"

## Summary

You've now ...

- enabled SAP Task Center in your TechEd subaccount successfully <img src="/exercises/ex1/images/Checkmark_R_green.png" height="40" width="40" >

- configured the BTP Launchpad service & integrated the SAP Task Center applications <img src="/exercises/ex1/images/Checkmark_R_orange.png" height="40" width="40" >

- set up Single-Sign-On to use the certificate based logon for the BTP Launchpad service to access the SAP Task Center applications <img src="/exercises/ex1/images/Checkmark_R_purple.png" height="40" width="40" >

<br><img src="/exercises/ex1/images/hero.png" height="100" width="100" >


Continue to - [Exercise 2 - Integrate SAP S/4HANA as task provider](../ex2/README.md)

