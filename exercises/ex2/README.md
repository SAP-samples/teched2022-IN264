# Exercise 2 - Integrate SAP S/4HANA on-premise as a task provider

In this exercise, we will go through the steps to integrate Task Center with SAP S/4HANA on-premise.  You will create a destination in SAP Business Technology Platform (BTP) to the SAP S/4HANA system, validate the connectivity from SAP Task Center to S/4HANA, and update the UUID field for your SAP S/4HANA user.

## Exercise 2.1 Create SAP S/4HANA Destination

The SAP Task Center communicates with the task provider applications via predefined destinations in a customer subaccount.  After completing this exercise you will setup the destination required for SAP Task Center to pull tasks from SAP S/4HANA on-premise system.  For this exercise you have the option to create the destination manually or import a pre-created destination.  

Option 1: Create destination manually

1. In your subaccount, expand Connectivity and click **Destinations**.
<br>![](/exercises/ex2/images/S4Destination1.png)

2.	Click **New Destination**.
<br>![](/exercises/ex2/images/S4Destination2.png)

3. Enter the following details:
    * __Name__: S4HANA
    * __Type__: HTTP
    * __URL__: http://s4hana1.tdc.sap.com:50081
    * __Proxy Type__: OnPremise
    * __Authentication__: BasicAuthentication
    * __Location ID__: &lt;add IN264-## where ## is your assigned student number&gt;
    * __User__: TC_SRV_USR
    * __Password__: Welcome123
   
 4. Under Additional Properties, click **New Property** and add the following properties one at a time:
    * __tc.enabled__: true
    * __tc.provider_type__: S/4HANA
    * __tc.ui.group__: SAP S/4HANA
    * __tc.ui.label__: SAP S/4HANA Task
    * __URL.queries.sap-client__: 400
    
**HINT**: When typing properties names directly in the interface, the first character of the property will be added in uppercase. Type the properties names in Notepad and paste into the user interface instead.
<br>![](/exercises/ex2/images/S4Destination3.png)

 5. Click **Save**.
 6. Click **Check Connection** and confirm connection is successful.
 <br>![](/exercises/ex2/images/S4Destination5.png)
 
 
Option 2: Import a pre-created destination (only complete if you skipped the option to create the destination manually)

1. In your subaccount, expand Connectivity and click **Destinations**.
<br>![](/exercises/ex2/images/S4Destination1.png)

2.	Click **Import Destination**.
<br>![](/exercises/ex2/images/S4Destination4-1.png)

3. Navigate to IN264-Resources folder you downloaded earlier.  Select **S4HANA_Destination** file and click **Open**.
<br>![](/exercises/ex2/images/SelectDestforImport.png)

5. Update the following properties for the imported destination:
   * __Location ID__: &lt;add IN264-## where ## is your assigned student number&gt;
   * __Password__: Welcome123
<br>![](/exercises/ex2/images/S4Destination4.png)
5. Click **Save**.
6. Click **Check Connection** and confirm connection is successful.
 <br>![](/exercises/ex2/images/S4Destination5.png)
 

## Exercise 2.2 Check SAP S/4HANA connectivity via Task Center Admin app

After completing these steps you will confirm that S/4 HANA on-premise connectivity is working from SAP Task Center.

1.	In your subaccount, click **Instances and Subscriptions >> Launchpad Service**.
<br>![](/exercises/ex2/images/EX2.2-1.png)

2. If prompted, select **tdteched3.accounts.ondemand.com** as the Identity Provider.
<br>![](/exercises/ex2/images/EX2.2-2.png)

3. Enter the following credentials and click **Logon**:
   * __Email or User Name__: &lt;IN264-## where ## is your assigned student number&gt;
   * __Password__: Welcome123
 <br>![](/exercises/ex2/images/EX2.2-3.png)
 
4. Click **Go to site** icon on the site you created earlier.
<br>![](/exercises/ex2/images/EX2.2-4.png)

5. Click **Task Center Administrator**.
<br>![](/exercises/ex2/images/EX2.2-5.png)

6. Click S/4HANA and confirm the status is **OK**.
<br>![](/exercises/ex2/images/EX2.2-6.png)

## Exercise 2.3 Update user UUID in SAP S/4HANA
For the integration scenario of SAP Task Center, you must use the user universal unique identifier (user UUID) of SAP Cloud Identity Services - Identity Authentication as the federation identifier.

User UUID stands for universal unique identifier. It specifies an identifier for a user that is unique across technology layers such as user interface, APIs, and security tokens, as well as across products and lines of businesses contributing to a business process in the Intelligent Enterprise.

This attribute is automatically generated by Identity Authentication at user creation, and can be provisioned to various SAP cloud solutions by Identity Provisioning.

User UUID addresses the challenge of integrating user-related data across system boundaries. SAP Task Center is an example of a service which requires the use of the user UUID as a common user identifier. SAP Task Center provides a single entry point for business users to access their tasks. This scenario needs an enterprise-wide mapping of users to relate tasks to each other in different systems.

In this exercise we will use SAP Cloud Identity Provisioning proxy system to update the UUID in the backend S/4 system.  The SAP Cloud Identity Provisioning proxy system is pre-configured for this hands-on exercise.  We will use CURL to call the proxy system and update the UUID in S/4, but you can also use other rest clients like Postman to make a similar call.

1. Navigate to IN264-Resources folder you downloaded earlier.  Open **CURL Commands** folder.
<br>![](/exercises/ex2/images/EX2.3-2.png)

2. Open **IN264-##.txt** where **##** is your assigned user number and copy the entire CURL command.
<br>![](/exercises/ex2/images/EX2.3-3.png)

3. In Windows search, type **Powershell** and open the Windows PowerShell app.
<br>![](/exercises/ex2/images/EX2.3-1.png)

6. Paste the copied curl command into the Powershell app and hit **Enter** key on your keyboard.

NOTE: CURL command in the text file is unique to each participant so confirm that you are executing the command for your own user.  The UUID shown in the CURL command is User UUID that comes from the user profile in SAP Cloud Identity Authentication Service(IAS).
<br>![](/exercises/ex2/images/EX2.3-4.png)

7. Confirm the CURL command is executed successfully.  The output at the end should look similar to the screenshot.
<br>![](/exercises/ex2/images/EX2.3-5.png)

## Summary

You've now setup the destination configuration that needs to be done for SAP Task Center in order to work with on-premise tasks from SAP S/4HANA on SAP BTP, Cloud Foundry environment.  In addition, you've updated the S/4HANA user properties with the universal unique identifier (user UUID) of SAP Cloud Identity Services - Identity Authentication.

Continue to - [Exercise 3 - Integrate SAP Process Automation as task provider  ](../ex3/README.md)
