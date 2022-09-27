# Exercise 1 - Enable SAP Task Center

In this exercise, we will execute the BTP Booster (Excercise 1.1.)to setup SAP Task Center service on your subaccount

## Exercise 1.1 execute the SAP Task Center Booster

To run the BTP Booster for SAP Task Center, choose from the left hand navigation (ensure that you are on the BTP Glob Account level and not inside the BTP subaccount) the **Booster** entry:

<br>![](/exercises/ex1/images/booster01.png)

Search now by typing "Task Center" for the BTP Booster an presse the **Start** button on the tile:

<br>![](/exercises/ex1/images/booster02.png)

In the upcomming windo you should now get the resut from the prerequsite check, this must be passed (if not pls.inform the TechEd session team):

<br>![](/exercises/ex1/images/booster02.png)

Press now the **Next** button from bottom right corner to move to the next phase of the BTP Booster.
In this step validate yourself with the used and entitled services (Lauchpad and Task center), select the BTP subaccount and press the **Next** button.
The SAP Task Center setup will be executed in this subaccount! 
**Important: Pleas use here only the subaccount which you have access to, otherwise other participants get an error to run this SAP TechEd Hands-on which should be avoided**

<br>![](/exercises/ex1/images/booster04.png)

In the last step check again the subaccount and start the execution by finally press **Finish**.

<br>![](/exercises/ex1/images/booster05.png)

In the upcoming screen you should now see the execution

After completing these steps you will have created/enabled SAP Task Center service in your BTP subaccount

1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)


## (optional) Exercise 1.2 validate the the "Booster" setup of SAP Task Center

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```
## Exercise 1.3 integrate the SAP Task Center service into SAP BTP Launchpad

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

