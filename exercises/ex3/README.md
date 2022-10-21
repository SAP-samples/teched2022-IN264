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
