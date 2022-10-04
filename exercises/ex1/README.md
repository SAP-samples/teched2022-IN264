# Exercise 1 - Enable SAP Task Center

In this exercise, we will execute the BTP Booster (Excercise 1.1.)to setup SAP Task Center service on your subaccount

## Exercise 1.1 execute the SAP Task Center Booster

To run the BTP Booster for SAP Task Center, choose from the left hand navigation (ensure that you are on the BTP Glob Account level and not inside the BTP subaccount) the **Booster** entry:

<br>![](/exercises/ex1/images/booster01.png)

Search now by typing "Task Center" for the BTP Booster an presse the **Start** button on the tile:

<br>![](/exercises/ex1/images/booster02.png)

In the upcomming windo you should now get the resut from the prerequsite check, this must be passed (if not pls.inform the TechEd session team):

<br>![](/exercises/ex1/images/booster03.png)

Press now the **Next** button from bottom right corner to move to the next phase of the BTP Booster.
In this step validate yourself with the used and entitled services (Lauchpad and Task center), select the BTP subaccount and press the **Next** button.
The SAP Task Center setup will be executed in this subaccount! 
**Important: Pleas use here only the subaccount which you have access to, otherwise other participants get an error to run this SAP TechEd Hands-on which should be avoided**

<br>![](/exercises/ex1/images/booster04.png)

In the last step check again the subaccount and start the execution by finally press **Finish**.

<br>![](/exercises/ex1/images/booster05.png)

In the upcoming screen you should now see the execution of the diffent actions and the status:

<br>![](/exercises/ex1/images/booster06.png)

After the execution was successfully you should now see this summary with the option to configure the destinations or to jump in the SAP Help documentation.

<br>![](/exercises/ex1/images/booster07.png)

Pleas click on the first link to jump directly in your subaccount and the created destinations which we need to configure in our scenario in [excercise](exercises/ex2#exercise-21-sub-exercise-1-description). 

<br>![](/exercises/ex1/images/destinations_overview.png)

**Congratulations** with the successful execution of this excercise we can now go further with the SAP Tas Center by setting up the Launchpad service to access the SAP Task Center application.


## Exercise 1.2 integrate the SAP Task Center service into SAP BTP Launchpad

In the upcoming excercise we will add the SAP Task Center apps to your BTP Launchpad, you can find [here also the official SAP Help doumentation](https://help.sap.com/docs/TASK_CENTER/08cbda59b4954e93abb2ec85f1db399d/3a499676e7ae4282af84092f778e3737.html#procedure). 

To get started select from the BTP cockpit again the **Instances and Subscriptions** entry from the BTP navigation, by clicking the icon you will enter the site manager to configure the launchpad service:

<br>![](/exercises/ex1/images/lp_site_manager_access.png)

In the next step click on the **Channel Manager** icon and refresh the "HTML5 Apps" channel by clicking the refresh icon:

<br>![](/exercises/ex1/images/lp_site_manager_channel_manager_refresh.png)

The status should be changed to "updating":

<br>![](/exercises/ex1/images/lp_site_manager_channel_manager_updating.png)

To validate that the SAP Task Center apps are now available we'll check the "Content Manager":

<br>![](/exercises/ex1/images/lp_site_manager_main_page.png)

In the upcoming screen select the second tab (Content Explorer) and click on the **HTML5 Apps** tile:

<br>![](/exercises/ex1/images/lp_site_manager_content_manager.png)

<br>![](/exercises/ex1/images/lp_site_manager_html5_apps.png)

As result you should now see to entries/apps:

1. Task Center
2. Task Center Administration

<br>![](/exercises/ex1/images/lp_site_manager_content_manager_stc-apps.png)

Pleae select all entries an press the **Add to My Content** button. 
If you now select the the first tab to validate the result, you should now identify the Task Center apps are now added to the items list:

<br>![](/exercises/ex1/images/lp_site_manager_my_content.png)

The last step is now to assign the apps to the pre-defined "Everyone" role ([SAP Help documentation](https://help.sap.com/docs/Launchpad_Service/8c8e1958338140699bd4811b37b82ece/baeaf6ee364e48ac95dc09470281f174.html)):

## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

