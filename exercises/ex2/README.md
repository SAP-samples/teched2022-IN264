# Exercise 2 - Exercise 2 Description

In this exercise, we will create...

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
 
 
Option 2: Import a pre-created destination (only completed if you skipped the option to create the destination manually)

<a href="myFile.js" download>Click to Download</a>
1. In your subaccount, expand Connectivity and click **Destinations**.
<br>![](/exercises/ex2/images/S4Destination1.png)

2.	Click **Import Destination**.
<br>![](/exercises/ex2/images/S4Destination4-1.png)

3. Select the provided destination file and click **Open**.
4. Update the following properties for the imported destination:
   * __Location ID__: &lt;add IN264-## where ## is your assigned student number&gt;
   * __Password__: Welcome123
<br>![](/exercises/ex2/images/S4Destination4.png)
5. Click **Save**.
6. Click **Check Connection** and confirm connection is successful.
 <br>![](/exercises/ex2/images/S4Destination5.png)
 
 
## Exercise 2.2 Sub Exercise 2 Description

After completing these steps you will have...


1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex2/images/02_02_0010.png)

## Summary

You've now ...

Continue to - [Exercise 3 - Excercise 3 ](../ex3/README.md)
