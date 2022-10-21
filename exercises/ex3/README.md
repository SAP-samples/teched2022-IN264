# Exercise 3 - Integrate SAP SAP Process Automation as task provider

In this exercise, we will integrate SAP Process Automation as additional task provider to provide you also the idea to implement a "central inbox accross SAP solutions.

## Exercise 3.1 create the destination to the SAP Process Automation instance from a remote subaccount

### (Option a) Manual createion
1. Navigate in your BTP subaccount to **Destinations**

2. Creat a new one by choosing **New Destination**

![](/exercises/ex3/images/new_dest.png)

3. Enter the following details:
    * __Name__: SPA_rem
    * __Type__: HTTP
    * __URL__: https://spa-api-gateway-bpi-eu-prod.cfapps.eu10.hana.ondemand.com/internal/workflow/rest/v1
    * __Proxy Type__: Internet
    * __Authentication__: OAuth2SAMLBearerAssertion
    * __Audience__: https://teched-spa-tc-eu10-mthzww43.authentication.eu10.hana.ondemand.com
    * __AuthnContextClassRef__: urn:oasis:names:tc:SAML:2.0:ac:classes:PreviousSession
    * __Client Key:__: Dedsb-9be2997d-a9b2-4a73-83d9-b1ac80a3528f!b152845|xsuaa!b120249icated
    * __Token Service URL Type:__: Dedicated
    * __Token Service URL:__: https://teched-spa-tc-eu10-mthzww43.authentication.eu10.hana.ondemand.com/oauth/token/alias/teched-spa-tc-eu10-mthzww43.aws-live-eu10
    * __Token Service User:__: sb-9be2997d-a9b2-4a73-83d9-b1ac80a3528f!b152845|xsuaa!b120249
    * __Token Service Password:__: Welcome123
   
 4. Under Additional Properties, click **New Property** and add the following properties one at a time:
    * __nameIdFormat__: urn:oasis:names:tc:SAML:1.1:nameid-format:emailAddress
    * __tc.enabled__: true
    * __tc.provider_type__: SPA
    * __tc.ui.group__: SAP Process Automation
    * __tc.ui.label__: SAP Process Automation Task
    * __URL.queries.sap-client__: 400
    * __userIdSource__: user_uuid

### (Option a) Using the provided archive/destination createion
Navigate in your BTP subaccount to **Destinations** and create a new one by choosing the **Import Destination** button:

![](/exercises/ex3/images/destination.png)

Extract now the [archive](/exercises/ex3/SPA_remote_Destination.zip) and import the destination.

## Exercise 3.2 - Check SAP Process Automation connectivity via Task Center Admin app

After completing these steps you will confirm that SAP Process Automation connectivity is working from SAP Task Center.

1.	In your subaccount, click **Instances and Subscriptions >> Launchpad Service**.
<br>![](/exercises/ex3/images/lp_subscr.png)

2. If prompted, select **tdteched3.accounts.ondemand.com** as the Identity Provider.
<br>![](/exercises/ex3/images/auth_custom_ias.png)

3. Enter the following credentials and click **Logon**:
   * __Email or User Name__: &lt;IN264-## where ## is your assigned student number&gt;
   * __Password__: Welcome123
 <br>![](/exercises/ex3/images/logon.png)
 
4. Click **Go to site** icon on the site you created earlier.
<br>![](/exercises/ex3/images/execute_lp_site.png)

5. Click **Task Center Administrator**.
<br>![](/exercises/ex3/images/admin_app.png)

6. Click S4HANA and confirm the status is **OK**.
<br>![](/exercises/ex3/images/spa_admin_app_success.png)

## Exercise 3.2 - SAP Process Automation start process

To validate that we can also hace SAP Process Automation tasks availble for SAP Task Center please execut the follwing API via Postman:

https://github.com/SAP-samples/teched2022-IN264/blob/main/exercises/ex2/README.md#exercise-23-update-user-uuid-in-sap-s4hana

2. Search and Select the API request **IN264 start prc**:
<br>![](/exercises/ex3/images/postman.png)

3. **IMPORTANT** update the **global_user_id** value with **UUID** for your SAP Task Center user.

4. Execute the API request by pressing the **Send** button and check afterwards that you get an **201** status response:
<br>![](/exercises/ex3/images/201.png)

## Summary

