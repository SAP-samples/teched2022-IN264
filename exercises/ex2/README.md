# Exercise 2 - Integrate SAP S/4HANA on-premise as a task provider

In this exercise, we will go thorugh the steps to integrate Task Center with SAP S/4HANA on-premise.  You will create a destination in SAP Business Technology Platform (BTP) to the S/4 system and validate the connectivity from SAP Task Center to SAP S/4HANA.

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

6. Click S4HANA and confirm the status is **OK**.
<br>![](/exercises/ex2/images/EX2.2-6.png)

## Exercise 2.3 Update user UUID in SAP S/4HANA


## Summary

You've now setup the destination configuration that needs to be donefor SAP Task Center in order to work with on-premise tasks from SAP S/4HANA on SAP BTP, Cloud Foundry environment.

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
