<!-- loio2dc6e5a98bca436c98a6cd7602960e99 -->

# Salesforce Service Cloud Adapter

The Salesforce Service Cloud receiver adapter connects SAP Integration Suite to Salesforce Service Cloud. The Salesforce Service Cloud is a customer relationship management \(CRM\) platform designed to help businesses manage and resolve customer inquiries across multiple channels, including phone, email, chat, social media, and messaging.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio2dc6e5a98bca436c98a6cd7602960e99__ashweq30223"/>

## How the Salesforce Service Cloud Receiver Adapter Works

If you have configured the Salesforce Service Cloud receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to Salesforce Service Cloud \(this is a receiver system\), Salesforce Service Cloud works on the request and sends the data back to the SAP Integration Suite tenant.



## Configure the Salesforce Service Cloud Receiver Adapter

**Connection**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the authentication type to connect to Salesforce:

-   *OAuth 2.0 Client Credentials* 
-   *OAuth 2.0 JWT Bearer*
-   *OAuth 2.0 Username-Password*



</td>
</tr>
<tr>
<td valign="top">

*Address*

\(Only available when the *OAuth 2.0 Client Credentials* is selected\)

</td>
<td valign="top">

-   For *OAuth 2.0 Client Credentials*: Specify the instance URL endpoint to perform the data calls.

    Example: `https://{MyDomain}.my.salesforce.com` if MyDomain is enabled on the org.


-   For *OAuth 2.0 Username-Password*: Specify the login endpoint to your Salesforce instance URL.

    Example: `https://login.salesforce.com` for the Salesforce production environment, https://test.salesforce.com for the Salesforce Sandbox environment and `https://{MyDomain}.my.salesforce.com` in case MyDomain is enabled on the org.




</td>
</tr>
<tr>
<td valign="top">

*OAuth2 Credentials Name*

\(Only available when the *OAuth 2.0 Client Credentials* is selected\)

</td>
<td valign="top">

Specify the OAuth2 Client Credentials security artifact that stores the consumer key and consumer secret.

</td>
</tr>
<tr>
<td valign="top">

*Audience*

\(Only available when the *OAuth 2.0 JWT Bearer* is selected\)

</td>
<td valign="top">

Specify the login endpoint to your Salesforce instance url.

Example: `https://login.salesforce.com` for Salesforce production environment, `https://test.salesforce.com` for Salesforce Sandbox environment and `https://site.force.com/customers` if implementing for an Experience Cloud site.

</td>
</tr>
<tr>
<td valign="top">

*Subject Alias*

\(Only available when the *OAuth 2.0 JWT Bearer* is selected\)

</td>
<td valign="top">

Specify the security artifact secure parameter that stores the username.

</td>
</tr>
<tr>
<td valign="top">

*Issuer Alias*

\(Only available when the *OAuth 2.0 JWT Bearer* is selected\)

</td>
<td valign="top">

Specify the security artifact secure parameter that stores the OAuth client\_id of the connected app in Salesforce for which the certificate was registered.

</td>
</tr>
<tr>
<td valign="top">

*Keystore Alias*

\(Only available when the *OAuth 2.0 JWT Bearer* is selected\)

</td>
<td valign="top">

Specify the keystore alias for Client JWT token generation. It consists of the key and certificate to sign the JWT.

</td>
</tr>
<tr>
<td valign="top">

*Expiration \(in secs\)*

\(Only available when the *OAuth 2.0 JWT Bearer* is selected\)

</td>
<td valign="top">

Specifies the validity of the assertion in seconds.

</td>
</tr>
<tr>
<td valign="top">

*Basic Credential Name*

\(Only available when the *OAuth 2.0 Username-Password* is selected\)

</td>
<td valign="top">

Specify the security material that stores the basic credential name \(username-password pair\).

</td>
</tr>
<tr>
<td valign="top">

*Security Token Alias*

\(Only available when the *OAuth 2.0 Username-Password* is selected\)

</td>
<td valign="top">

Specify the security artifact secure parameter that stores the security token. It can be omitted if your IP has been whitelisted on Salesforce.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Credential Name*

\(Only available when the *OAuth 2.0 Username-Password* is selected\)

</td>
<td valign="top">

Specify the security artifact user credentials that stores the Consumer key and Client secret.

</td>
</tr>
<tr>
<td valign="top">

*Connection Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for the connection to be established with the GoTo Webinar service.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Response Timeout \(in ms\)*

</td>
<td valign="top">

Specify the maximum waiting time \(in milliseconds\) for a response to be received with the GoTo Webinar service.

Example: `60000`

</td>
</tr>
<tr>
<td valign="top">

*Lazy Authentication*

</td>
<td valign="top">

Enable to defer OAuth token retrieval or generation until the first API call.

</td>
</tr>
</table>

**Processing**


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Configuration Type*

</td>
<td valign="top">

Select the required configuration type:

-   *Basic* to use the dropdowns and parameter text fields.
-   *Advanced* to specify the relative URL.



</td>
</tr>
<tr>
<td valign="top">

*Type*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the type of API to be used:

-   *Apex Call*
-   *REST*
-   *REST Bulk 2.0*



</td>
</tr>
<tr>
<td valign="top">

*Operation*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*API Version*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the required version.

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Object*

</td>
<td valign="top">

Select the technical Salesforce object name for the data being processed without spaces.

Example: `AccountPartner, CustomObject__c`

</td>
</tr>
<tr>
<td valign="top">

*Salesforce Object ID*

</td>
<td valign="top">

Specify the Salesforce object ID which identifies a specific record in Salesforce.

</td>
</tr>
<tr>
<td valign="top">

*External ID Name*

</td>
<td valign="top">

Specify the name of the external field of a specific Salesforce object.

</td>
</tr>
<tr>
<td valign="top">

*External ID Value*

</td>
<td valign="top">

Specify the value of the external field of a specific Salesforce object.

</td>
</tr>
<tr>
<td valign="top">

*Filter Fields*

</td>
<td valign="top">

Enable to apply filters to the Salesforce Object.

</td>
</tr>
<tr>
<td valign="top">

*Name*

</td>
<td valign="top">

Specify the name of the field to be returned in the response.

</td>
</tr>
<tr>
<td valign="top">

*Method*

</td>
<td valign="top">

Select the type of operation to be performed.

</td>
</tr>
<tr>
<td valign="top">

*List of IDs*

</td>
<td valign="top">

Specify the list of up to 200 IDs of objects to be deleted.

> ### Note:  
> The IDs can belong to different object types, including custom objects.



</td>
</tr>
<tr>
<td valign="top">

*All or None*

</td>
<td valign="top">

Enable All or None \(technical name is allOrNone\) to roll back the entire request when the deletion of any object fails or disable it to continue with the independent deletion of other objects in the request.

</td>
</tr>
<tr>
<td valign="top">

*SOQL Query*

</td>
<td valign="top">

Specify the SOQL query to be executed.

</td>
</tr>
<tr>
<td valign="top">

*SOSL Search*

</td>
<td valign="top">

Specify the SOSL search to be executed.

</td>
</tr>
<tr>
<td valign="top">

*Next Records URL*

</td>
<td valign="top">

Specify the URL to retrieve the next batch of records.

Example:`/services/data/v64.0/sobjects/Account/0015Exxxx1pZixuQxx`

</td>
</tr>
<tr>
<td valign="top">

*Method Name*

</td>
<td valign="top">

Select the Apex REST method used to specify the Method annotation in the Apex Class.

</td>
</tr>
<tr>
<td valign="top">

*Resource Relative URL*

\(Only available when the *Type* is selected as *Apex Call*\)

</td>
<td valign="top">

Specify the relative URL of the Apex requestURI. The relative path is the part of the requestURI after the instance URL and needs to start with /.

Example: If the request URL is `https://instance.salesforce.com/services/apexrest/Account/123`, the relative URL will be "`/services/apexrest/Account/123`".

</td>
</tr>
<tr>
<td valign="top">

*Job ID*

</td>
<td valign="top">

Specify the ID of the job.

</td>
</tr>
<tr>
<td valign="top">

*Job Result Type*

</td>
<td valign="top">

Select the type of records to be retrieved for the selected job ID.

-   *Failed Results*
-   *None*
-   *Successful Results*
-   *Unprocessed Records*



</td>
</tr>
<tr>
<td valign="top">

*Advanced Job Properties*

</td>
<td valign="top">

Enable to specify all the advanced properties in the adapter instead of in the payload.

</td>
</tr>
<tr>
<td valign="top">

*Operation Name*

</td>
<td valign="top">

Select the required operation.

</td>
</tr>
<tr>
<td valign="top">

*Column Delimiter for Job*

</td>
<td valign="top">

Select the column delimiter used for CSV job data:

-   *Backquote Character \(\`\)*
-   *Caret Character \(^\)*
-   *Comma Character \(,\)*
-   *Pipe Character \(|\)*
-   *SemiColon Character \(;\)*
-   *Tab Character*



</td>
</tr>
<tr>
<td valign="top">

*Content Type*

</td>
<td valign="top">

Select the content type for the job:

-   *CSV*



</td>
</tr>
<tr>
<td valign="top">

*Line Ending*

</td>
<td valign="top">

Select the line ending used for CSV job data, marking the end of a data row:

-   *CRLF—carriage return character*
-   *LF—linedfeed character*



</td>
</tr>
<tr>
<td valign="top">

*Assignment Rule ID*

</td>
<td valign="top">

Specify the ID of an assignment rule to run for a Case or a Lead. The assignment rule can be active or inactive.

</td>
</tr>
<tr>
<td valign="top">

*External ID Field Name*

</td>
<td valign="top">

Specify the external ID field in the object being updated. Only needed for upsert operations. Field values must also exist in CSV job data.

</td>
</tr>
<tr>
<td valign="top">

*Job Type*

</td>
<td valign="top">

Select the type of records to be retrieved for the selected job ID:

-   *V2ingest*
-   *Classic*
-   *BigObjectIngest*



</td>
</tr>
<tr>
<td valign="top">

*Query Locator*

</td>
<td valign="top">

Specify a queryLocator with a locator value to get a specific set of job results.

</td>
</tr>
<tr>
<td valign="top">

*Query Job ID*

</td>
<td valign="top">

Specify the Job ID of the Query.

</td>
</tr>
<tr>
<td valign="top">

*Max Records*

</td>
<td valign="top">

Specify the maximum number of records the adapter is expected to receive from Salesforce per page to prevent a timeout.

Example: `2000`

> ### Note:  
> If working with a very large number of query results, then there is a possibility of a timeout before receiving all the data from Salesforce.



</td>
</tr>
<tr>
<td valign="top">

*Sforce-Locator*

</td>
<td valign="top">

Specify the Sforce-Locator to get the individual pages from the query results.

</td>
</tr>
<tr>
<td valign="top">

*Auto Pagination*

</td>
<td valign="top">

Enable to retrieve all records in case the query result has more than one page.

</td>
</tr>
<tr>
<td valign="top">

*Enable PkChunking*

</td>
<td valign="top">

Enable automatic primary key \(PK\) chunking. PK chunking splits bulk queries on large tables into chunks based on the record IDs, or primary keys, of the queried records.

</td>
</tr>
<tr>
<td valign="top">

*Upload Job Data from body*

</td>
<td valign="top">

Enable this property to create a job and upload all the data for a job using a multipart request.

</td>
</tr>
<tr>
<td valign="top">

*Include deleted records in query result*

</td>
<td valign="top">

Enable to include the records that have been deleted or merged as part of the results.

</td>
</tr>
<tr>
<td valign="top">

*Handle XML Null Values*

</td>
<td valign="top">

Enable to use null values in the payload to nullify properties in Salesforce.

</td>
</tr>
<tr>
<td valign="top">

*Treat all XML Payload Values as String*

</td>
<td valign="top">

Enable to treat all the values in the XML payload as string before sending it to Salesforce.

</td>
</tr>
<tr>
<td valign="top">

*Enable Multiple Batch Processing*

</td>
<td valign="top">

Enable to allow multiple round trips to Salesforce in case the number of records exceeds the allowed limit \(200 records\) for the SObject Collections.

> ### Note:  
> Note that this feature does not support allOrNone=true.



</td>
</tr>
<tr>
<td valign="top">

*Enable Lookup Query*

</td>
<td valign="top">

Enable this property to automatically resolve queries in the request body.

> ### Note:  
> Enable Query Lookup supports only XML Payload Format.



</td>
</tr>
<tr>
<td valign="top">

*Payload Format*

</td>
<td valign="top">

Select the payload format of the request and response body.

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

\(Only available when the *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Select the HTTP Method:

-   *DELETE*
-   *GET*
-   *PATCH*
-   *POST*
-   *PUT*



</td>
</tr>
<tr>
<td valign="top">

*Relative URL*

\(Only available when the *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Specify the endpoint path, excluding the Host.

Example: `/services/data/v48.0/sobjects/ContentVersion/000000000000000123/VersionData`

</td>
</tr>
<tr>
<td valign="top">

*Send Body*

\(Only available when the *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Enable this checkbox if you want to send the body of the message with the request. For methods *GET* and *DELETE*, the body isn't sent by default.

</td>
</tr>
<tr>
<td valign="top">

*Query Parameters*

</td>
<td valign="top">

Specify the query parameter. When using multiple parameters, ensure they are separated by "&".

Example: `param1=value1&param2=value2`

</td>
</tr>
<tr>
<td valign="top">

*Request Headers*

</td>
<td valign="top">

Enter a list of custom headers, separated by a pipe \(|\), to be sent to the target system. Use an asterisk \(\*\) to send all custom headers to the target system. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
<tr>
<td valign="top">

*Response Headers*

</td>
<td valign="top">

Enter a list of headers, separated by a pipe \(|\), coming from the target system's response to be received in the message. Use an asterisk \(\*\) to receive all the headers from the target system, which is also the default value. All Camel-specific headers and HTTP protocol headers except "date" are excluded by default even if you specify them.

</td>
</tr>
</table>

