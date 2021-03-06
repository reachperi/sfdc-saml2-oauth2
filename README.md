### Notes on SFDC OAuth2 Flows

#### 6 flows ####

---------

1. [SAML Bearer Assertion Flow ](./SAML-Bearer-Assertion-Flow.md)

Token endpoint: POST: https://login|test.salesforce.com/services/oauth2/token

**grant_type**=urn:ietf:params:oauth:grant-type:saml2-bearer

assertion=The SAML Bearer Assertion, encoded using base64url.

response: access_token

-----

2. [JWT Bearer Token Flow ](./JWT-Bearer-Token-Flow.md)

Token endpoint: POST: https://login|test.salesforce.com/services/oauth2/token

**POST**: JWT

response: access_token

-------

3. [Web Server Flow ](./Web-server-flow.md)

Verification endpoint: GET :https://login|test.salesforce.com/services/oauth2/authorize

**response_type**=code (Validation Code)

Exchange Validation Code for access_token:

Token endpoint: POST: https://login|test.salesforce.com/services/oauth2/token

**grant_type**=authorization_code

response: access_token

--------


4. [User-Agent OAuth Authentication Flow](https://developer.salesforce.com/docs/atlas.en-us.api_rest.meta/api_rest/intro_understanding_user_agent_oauth_flow.htm)

Authorize endpoint: https://login|test.salesforce.com/services/oauth2/authorize

response_type=token



-----


5. [Web SSO SAML Assertion](https://developer.salesforce.com/page/Digging_Deeper_into_OAuth_2.0_on_Force.com#Obtaining_an_Access_Token_using_a_Web_SSO_SAML_Assertion)

Do not have to create a connected app to use this assertion flow

Token endpoint: https://login|test.salesforce.com/services/oauth2/token

**grant_type**=assertion

assertion_type=urn:oasis:names:tc:SAML:2.0:profiles:SSO:browser

assertion=The SAML Assertion, encoded using base64

[Reference](https://help.salesforce.com/articleView?id=remoteaccess_oauth_web_sso_flow.htm&type=0)

-------


6. [Username and Password Flow](https://developer.salesforce.com/page/Digging_Deeper_into_OAuth_2.0_on_Force.com#Obtaining_a_Token_in_an_Autonomous_Client_.28Username_and_Password_Flow.29)

Token endpoint: https://login|test.salesforce.com/services/oauth2/token

**grant_type**=password

username=username

password=user_password

-------
Reference:

- [Digging Deeper into OAuth 2.0 on Force.com](https://developer.salesforce.com/page/Digging_Deeper_into_OAuth_2.0_on_Force.com)
