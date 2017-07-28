# SOASTA-API-PHP
Query the infamous SOASTA API using a PHP code base.
I wrote this to make things easy for those less enclined to read alot.
for support on the API, please visit: https://docs.soasta.com/query-api/#authentication

<b>Authentication<b/>

For information about Tokens API, see Tokens_API.

To use the REST APIs, callers will issue a request using the mPulse URL shown below to get a security token. Note that the mPulse API URL is case sensitive. For example, to get a token from a mPulse instance via its RepositoryService:

Specify a username and account to get the security token used in later queries.

Where $user, is your username, and $pass, is your password.

"https://mpulse.soasta.com/concerto/services/rest/RepositoryService/v1/Tokens"

Note: Users who belong to multiple tenants and wish to obtain a security token for a tenant that is not their default, can add the "tenant” key to the JSON body; for example, “tenant”: “My Tenant”.

Will get the response like this: {"token":"da7be4d72030656559f3e41a98924a6b2a544730"}

<b>REST API URLs<b/>

Once a security token is acquired, it is used in all subsequent queries within the validity period. The URLs for accessing the REST API use the token, the mPulse instance, the domain, the query type(s), and any optional parameters that go with the query type, and take the following format:

/concerto/api/v2/<api-key>/<query-type>?<optional parameters>

If curl is used, the command line looks like this:

curl -H "Authentication: <security token>" "https://mpulse.soasta.com/mpulse/api/v2/<api-key>/<query type>?<optional parameters>"
