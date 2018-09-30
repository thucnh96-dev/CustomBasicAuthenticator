# CustomBasicAuthenticator
This custom authenticator will add new claims to the authenticated user. 

1) Stop the server if it is already running
2) Build the project using following command ```mvn clean install```
3) Copy the jar file org.wso2.custom.authenticator.local-1.0-SNAPSHOT.jar from the target directory to <IS_HOME>/repository/components/dropins folder
4) Start the server
5) Create custom local claim called ```http://test.wso2.org/claims/customname``` and mapped to an attribute which is available in your user store.
6) Then mapped this claims to an oidc claim.
7) Don’t forget to add the oidc claims to the registry.
8) Add a service provider by selecting the requested claim as "http://test.wso2.org/claims/customname"
9) select Local & Outbound Authentication Configuration and choose ```BasicCustom``` as the authenticator.
10) Get an id token for this service provider by authenicating through BasicCustom
11) Parse the id token using \[1], now you could able to see the claim keplerNumber as a json attribute.

Refer \[2] understand the implementations details.

\[1] https://jwt.io/

\[2] https://medium.com/@nilasini/sso-within-two-sps-while-using-a-custom-authenticator-and-a-custom-claim-handler-wso2is-5-3-0-bd473361ddf6
