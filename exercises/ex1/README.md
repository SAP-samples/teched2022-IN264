# Exercise 1 - Enable SAP Task Center

In this exercise, we will execute the BTP Booster (Excercise 1.1.)to setup SAP Task Center service on your subaccount to enable SAP Task Center.
Alternative you can also following the steps for the manual setup.
After SAP Task Center is enabled in your BTP subaccount we will no configure the BTP Launchpad service to integrate the SAP Task Center apps.
Finally we will configure "Single-Sign-On" (SSO) for the "Enduser" to get acces to SAP Task Center web application without using basic authentication.

## Exercise 1.1 execute the SAP Task Center Booster

1. To run the BTP Booster for SAP Task Center , choose from the left hand navigation (ensure that you are on the BTP Glob Account level and not inside the BTP subaccount) the **Booster** entry:

    <br>![](/exercises/ex1/images/booster01.png)

2. Search now by typing **"Task Center"** for the BTP Booster an presse the **Start** button on the tile:

    <br>![](/exercises/ex1/images/booster02.png)

    In the upcomming windo you should now get the resut from the prerequsite check, this must be passed (if not pls.inform the TechEd session team):

    <br>![](/exercises/ex1/images/booster03.png)

3. Press now the **Next** button from bottom right corner to move to the next phase of the BTP Booster.
  In this step validate yourself with the used and entitled services (Lauchpad and Task center), select the BTP subaccount and press the **Next** button.
  The SAP Task Center setup will be executed in this subaccount! 

**Important: Pleas use here only the subaccount which you have access to, otherwise other participants get an error to run this SAP TechEd Hands-on which should be avoided**

    <br>![](/exercises/ex1/images/booster04.png)

4. In the last step check again the subaccount and start the execution by finally press **Finish**.

    <br>![](/exercises/ex1/images/booster05.png)

    In the upcoming screen you should now see the execution of the diffent actions and the status:

    <br>![](/exercises/ex1/images/booster06.png)

After the execution was successfully you should now see this summary with the option to configure the destinations or to jump in the SAP Help documentation.

<br>![](/exercises/ex1/images/booster07.png)

Pleas click on the first link to jump directly in your subaccount and the created destinations which we need to configure in our scenario in [excercise](exercises/ex2#exercise-21-sub-exercise-1-description). 

<br>![](/exercises/ex1/images/destinations_overview.png)

**Congratulations** with the successful execution of this excercise we can now go further with the SAP Tas Center by setting up the Launchpad service to access the SAP Task Center application.

## Exercise 1.2 Enable SAP Task Center manually

## Exercise 1.3 integrate the SAP Task Center service into SAP BTP Launchpad

In the upcoming excercise we will add the SAP Task Center apps to your BTP Launchpad, you can find [here also the official SAP Help doumentation](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/3a499676e7ae4282af84092f778e3737.html#procedure). 

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

7. To enable the visibility of the SAP Task Center apps in the BTP Laucnhpad we need to create in the "Content Manager an new "Group".
   You cann add new content by clicking the **+ New** button afterwards select **Group**:

    <br>![](/exercises/ex1/images/lp_site_manager_create_group.png)

   Provide a name and a description and click (**Important**) in input field in the upper right corner, you will otherwise not see the apps. Finally press for each app the **+** button and save your changes:

    <br>![](/exercises/ex1/images/lp_site_manager_group_add_apps.png)

8. Assing now the SAP Task Center apps to "everyone" role, if u want to create a own "custom" role have a look in the [official SAP Help documentation](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/baeaf6ee364e48ac95dc09470281f174.html) to follow the required steps.

    <br>![](/exercises/ex1/images/lp_site_manager_role_add_apps.png)

9. The alsmost last step is now to create launchpad site by creating an new "site" in the "Site Manager".
    Please navigate for this in the "Site Directory": 

    <br>![](/exercises/ex1/images/lp_site_manager_site_directory.png)

10. create a "new" site:

    <br>![](/exercises/ex1/images/lp_site_manager_site_directory_new_site.png)

11. Afterwards you are able to see all settings for your newly created launchpad site, to enter it via the "Task Center business user" open the URL via the "Incognito" mode:

    <br>![](/exercises/ex1/images/lp_site_manager_site_edit.png)

12. After providing the credentials from the "**business user**" you should now identify the "Task Center tiles":

    <br>![](/exercises/ex1/images/lp_site_launch.png)

13. By entering the first (Task Center) tile you should now see the (empty) SAP Tas Center application:

    <br>![](/exercises/ex1/images/tc_final.png)

14. (optional) by changing the theme of your BTP launchpad site you can also adapt the site to the new "**SAP Horizon Theme**". 

    Select the settings from your profile (upper right corner) and select "**Settings**":

    <br>![](/exercises/ex1/images/theme_01.png)

    Choose now one of the booth "Horozon" themes: 

    <br>![](/exercises/ex1/images/theme_02.png)

    And check the result (example: SAP Evening Theme):

    <br>![](/exercises/ex1/images/theme_03.png)

**Congratulations** with this you can now access the SAP Task Center applications via the BTP Launchpad service !!!
In the next excercise we will configure "Single-Sign-On" (SSO) with SAP Cloud Identity Services.

    



## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

