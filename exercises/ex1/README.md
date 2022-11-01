# Exercise 1 - Enable SAP Task Center

In this exercise, you will manually setup SAP Task Center service on your subaccount to enable SAP Task Center.  
> ℹ It is also possible to execute a booster in SAP BTP cockpit to setup SAP Task Center, but this procedure is not in the scope of this hands-on.  For your reference, steps to setup SAP Task Center using a booster can be found [here](#exercise-12-execute-the-sap-task-center-booster-for-your-reference-only---skip-this-exercise-and-proceed-exercise-13).  
After SAP Task Center is enabled in your BTP subaccount we will configure the BTP Launchpad service to integrate the SAP Task Center apps.
Finally we will configure "Single-Sign-On" (SSO) for the "end user" to get access to SAP Task Center web application without need of using basic authentication.

Content in this Exercise:

- [Enable SAP Task Center manually](README.md#exercise-11-enable-sap-task-center-manually)
- [Run the BTP Booster for setting up SAP Task Center](README.md#exercise-12-execute-the-sap-task-center-booster)
- [Integrate the SAP Task Center service into SAP BTP Launchpad](README.md#exercise-13-integrate-the-sap-task-center-service-into-sap-btp-launchpad)
- [Enable Single-Sign-On (SSO) for SAP Task Center](README.md#exercise-14-enable-single-sign-on-sso-for-sap-task-center)
- [Summary](README.md#summary)

## Exercise 1.1 Enable SAP Task Center manually

To ensure that the BTP subaccount is well prepared we need to check the availability of the following BTP services:

- [SAP Task Center](https://discovery-center.cloud.sap/serviceCatalog/sap-task-center?region=all)
- [SAP BTP Launchpad](https://discovery-center.cloud.sap/serviceCatalog/launchpad-service?region=all)

Please perform the following steps to validate the required entitlements:

1. Enter your BTP subaccount and choose from the left hand navigation the **Entitlements** entry.

2. Search now for "Task Center" to ensure the service is entitled for the subaccount:
<br>![](/exercises/ex1/images/manual_check_stc_entitlem.png)

3. Additional search for "Launchpad" to validate also that this service is entitled for the subaccount.
<br>![](/exercises/ex1/images/manual_check_lp_entitlem.png)

After all prerequisites are met, we can now start to setup SAP Task Center.

**[Info]** The enablement of CloudFoundry was already executed

Switch now to **Instances and Subscriptions**  to get started (you will identify **SAP Launchpad Service** is already subscribed) press now **create** button:

<br>![](/exercises/ex1/images/start_create_sub_and_instances.png)

2.  To create the Task Center instance click on the **create** button and select the SAP Task Center service.
    Please specify an "Instance Name" and create the instance:

  <br>![](/exercises/ex1/images/stc_inst_create.png)

  Afterwards the creation starts now similar to the BTP Launchpad:

  <br>![](/exercises/ex1/images/stc_inst_create_prc.png)

  And should be finished after a couple of minutes:

  <br>![](/exercises/ex1/images/stc_inst_create_success.png)


3. (Optional) If u want to call the [SAP Task Center API](https://api.sap.com/package/SAPTaskCenter/rest) for example via Postman you need to create a "Service Key":

  <br>![](/exercises/ex1/images/stc_inst_create_sk.png)

The last step for this exercise is now to create a new destination to integrate SAP Task Center in the BTP Launchpad.

1. Please switch now to **Destinations** and create a **New Destination**:

  <br>![](/exercises/ex1/images/destination.png)

2. We'll now create a new destination for the integration of SAP Task Center into the BTP Launchpad, Choose from the 'Destination Configuration":

  - **Service Instance**

| Property | Value |
| ------------- |-------------|
| Service Instance:| ***Name from the previous created "Service Instance"***|
| Name:| ***sap_task_center_lp***|
| Description: | ***Description of your choice***|

  <br>![](/exercises/ex1/images/stc_dest_lp_int.png)
  
  Switch now to **Security > Role Collection**. 

3. To get access to the SAP Task Center Admin application we need to create a new **Role Collection**, choose **edit**:

  <br>![](/exercises/ex1/images/edit_rc.png)
  
  assign & add the roles adn save your changes:

  <br>![](/exercises/ex1/images/assign_roles.png)


4. Finally assign this new **Role Collection** to the **Platform User**, switch to **Users**, select the user:

  <br>![](/exercises/ex1/images/assign_rc.png)

**Congratulations** (!) You've now completed all necessary steps for the initial setup of SAP Task Center. In the next [exercise](README.md#exercise-13-integrate-the-sap-task-center-service-into-sap-btp-launchpad) we will learn how to access the SAP Task Center applications by setting up the BTP Launchpad Service.

*TODO add creation and assignment for TC role collection

## Exercise 1.2 execute the SAP Task Center Booster (*for your reference only - skip this exercise and proceed Exercise 1.3*)

> ⚠ For TechEd session IN264 please skip this exercise and proceed with [Exercise 1.3 Integrate the SAP Task Center service into SAP BTP Launchpad](#exercise-13-integrate-the-sap-task-center-service-into-sap-btp-launchpad) It's possible to setup SAP Task Center using a Booster, but this requires admin access to the Global Account.  This access is not available to the participants in the TechEd systems so the steps below are for your reference only and can only executed in your own system environment where you might have SAP BTP Global Account Admin privileges.

1. To run the BTP Booster for SAP Task Center , choose from the left hand navigation (ensure that you are on the BTP Glob Account level and not inside the BTP subaccount) the **Booster** entry:

    <br>![](/exercises/ex1/images/booster01.png)

2. Search now by typing **"Task Center"** for the BTP Booster an press the **Start** button on the tile:

    <br>![](/exercises/ex1/images/booster02.png)

    In the upcoming window you should now get the result from the prerequisite check, this must be passed (if not please inform the TechEd session team):

    <br>![](/exercises/ex1/images/booster03.png)

3. Press now the **Next** button from bottom right corner to move to the next phase of the BTP Booster.
  In this step validate yourself with the used and entitled services (Launchpad and Task center), select the BTP subaccount and press the **Next** button.
  The SAP Task Center setup will be executed in this subaccount! 
  
  **Important: Pleas use here only the subaccount which you have access to, otherwise other participants get an error to run this SAP TechEd Hands-on which should be avoided**
  <br>![](/exercises/ex1/images/booster04.png)

4. In the last step check again the subaccount and start the execution by finally press **Finish**.

    <br>![](/exercises/ex1/images/booster05.png)

    In the upcoming screen you should now see the execution of the different actions and the status:

    <br>![](/exercises/ex1/images/booster06.png)

After the successful execution you get a popup with the option to configure the destinations or to jump in the SAP Help documentation.

<br>![](/exercises/ex1/images/booster07.png)

Pleas click on the first link to enter your subaccount. 

<br>![](/exercises/ex1/images/destinations_overview.png)

**Congratulations** with the successful execution of this exercise we can now go further with the SAP Tas Center by setting up the Launchpad service to access the SAP Task Center application.

## Exercise 1.3 Integrate the SAP Task Center service into SAP BTP Launchpad

In the upcoming exercise we will add the SAP Task Center apps to your BTP Launchpad, you can find [here](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/3a499676e7ae4282af84092f778e3737.html#procedure) also the official SAP Help documentation for more details. 

1. To get started select from the BTP cockpit again the **Instances and Subscriptions** entry from the BTP navigation, by clicking the icon you will enter the site manager to configure the launchpad service:

<br>![](/exercises/ex1/images/lp_site_manager_access.png)

2. In the next step click on the **Channel Manager** icon and refresh the "HTML5 Apps" channel by clicking the refresh icon:

    <br>![](/exercises/ex1/images/lp_site_manager_channel_manager_refresh.png)

   The status should be changed to "updating":

    <br>![](/exercises/ex1/images/lp_site_manager_channel_manager_updating.png)

    To validate that the SAP Task Center apps are now available we'll check the "Content Manager":

    <br>![](/exercises/ex1/images/lp_site_manager_main_page.png)

4. In the upcoming screen select the second tab (Content Explorer) and click on the **HTML5 Apps** tile:

    <br>![](/exercises/ex1/images/lp_site_manager_content_manager.png)

    <br>![](/exercises/ex1/images/lp_site_manager_html5_apps.png)

    As result you should now see to entries/apps:

    1. Task Center
    2. Task Center Administration

    <br>![](/exercises/ex1/images/lp_site_manager_content_manager_stc-apps.png)

5. Select now all entries an press the **Add to My Content** button. 
   If you now select the the first tab to validate the result, you should now identify the Task Center apps are added to the items list:

    <br>![](/exercises/ex1/images/lp_site_manager_my_content.png)

6. The last step is now to create a group and the apps to the pre-defined "Everyone" role ([SAP Help documentation](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/baeaf6ee364e48ac95dc09470281f174.html)).

7. To enable the visibility of the SAP Task Center apps in the BTP Launchpad we need to create in the "Content Manager an new "Group".
   You can add new content by clicking the **+ New** button afterwards select **Group**:

    <br>![](/exercises/ex1/images/lp_site_manager_create_group.png)

   Provide a name and a description and click (**Important**) in input field in the upper right corner, you will otherwise not see the apps. Finally press for each app the **+** button and save your changes:

    <br>![](/exercises/ex1/images/lp_site_manager_group_add_apps.png)

8. Assign now the SAP Task Center apps to "everyone" role, if u want to create a own "custom" role have a look in the [official SAP Help documentation](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/baeaf6ee364e48ac95dc09470281f174.html) to follow the required steps.

    <br>![](/exercises/ex1/images/lp_site_manager_role_add_apps.png)

9. The almost last step is now to create launchpad site by creating an new "site" in the "Site Manager".
    Please navigate for this in the "Site Directory": 

    <br>![](/exercises/ex1/images/lp_site_manager_site_directory.png)

10. create a "new" site:

    <br>![](/exercises/ex1/images/lp_site_manager_site_directory_new_site.png)

11. Afterwards you are able to see all settings for your newly created launchpad site. In order to access the "SAP Task Center" as business user (task approver), please open the URL in "Incognito"-mode browser session or logout all your sessions for the platform user (BTP Admin):

    <br>![](/exercises/ex1/images/lp_site_manager_site_edit.png)

> ℹ You can also bookmark the URL for your Launchpad site for later reference.

12. After providing the credentials from the "**business user**" you should now identify the "Task Center tiles":

    <br>![](/exercises/ex1/images/lp_site_launch.png)

13. By entering the first (Task Center) tile you should now see the (empty) SAP Tas Center application:

    <br>![](/exercises/ex1/images/tc_final.png)

14. (optional) by changing the theme of your BTP launchpad site you can also adapt the site to the new "**SAP Horizon Theme**". 

    Select the settings from your profile (upper right corner) and select "**Settings**":

    <br>![](/exercises/ex1/images/theme_01.png)

    Choose now one of the available "Horizon" themes: 

    <br>![](/exercises/ex1/images/theme_02.png)

    And check the result (example: SAP Evening Theme):

    <br>![](/exercises/ex1/images/theme_03.png)

**Congratulations** with this you can now access the SAP Task Center applications via the BTP Launchpad service !!!
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

Afterwards a download of the "new" certificate will start, please store the file on a known place in the file system and open (double click) the file.
In the upcoming wizard step trough all steps w/o changing the defaults:

<br>![](/exercises/ex1/images/user_profile_cert_import1.png)

Provide here also the password which u have defined before and import the certificate:

<br>![](/exercises/ex1/images/user_profile_cert_import2.png)

By entering now the BTP Launchpad site url you should now able to select a certificate:

<br>![](/exercises/ex1/images/cert_based_logon.png)

And afterwards you are successfully logged on at the BTP Launchpad site with the SAP Task Center applications:

<br>![](/exercises/ex1/images/cert_based_logon_lp.png)

**Congratulations** you have now finished the entire "[Exercise 1](README.md)" after completing this last step.
You can now switch back to main page of the hands-on or directly start with "[Exercise 2](../ex2/README.md)"

## Summary

You've now ...

- enabled SAP Task Center in your TechEd subaccount successfully <img src="/exercises/ex1/images/Checkmark_R_green.png" height="40" width="40" >

- configured the BTP Launchpad service & integrated the SAP Task Center applications <img src="/exercises/ex1/images/Checkmark_R_orange.png" height="40" width="40" >

- setting up SSO to use the certificate based logon for the BTP Launchpad service to access the SAP Task Center applications <img src="/exercises/ex1/images/Checkmark_R_purple.png" height="40" width="40" >

<br><img src="/exercises/ex1/images/hero.png" height="100" width="100" >


Continue to - [Exercise 2 - Integrate SAP S/4HANA as task provider](../ex2/README.md)

