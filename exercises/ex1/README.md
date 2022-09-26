# Exercise 1 - Enable SAP Task Center

In this exercise, we will execute the BTP Booster to setup SAP Task Center service for your subaccount

## Exercise 1.1 execute the SAP Task Center Booster

After completing these steps you will have created/enabled SAP Task Center service in your BTP subaccount

1. Click here.
<br>![](/exercises/ex1/images/01_01_0010.png)


## Exercise 1.2 validate the the "Booster" setup of SAP Task Center

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

