<!-- loio5e143a5b3e664284a4415e760a192eda -->

# GoTo Webinar Receiver Adapter

The GoTo Webinar receiver adapter connects SAP Integration Suite to GoTo Webinar allowing data exchange between the two systems. GoTo Webinar is a video-conferencing platform designed for hosting webinars, virtual events, and video meetings.

> ### Note:  
> This adapter is available on SAP Business Accelerator Hub.
> 
> For more information, see [Consuming Integration Adapters from SAP Business Accelerator Hub](consuming-integration-adapters-from-sap-business-accelerator-hub-b9250fb.md).
> 
> The availability of the adapter is dependent on your SAP Integration Suite service plan. For more information about different service plans and their supported feature set, see SAP Notes [2903776](https://launchpad.support.sap.com/#/notes/2903776) and [3188446](https://launchpad.support.sap.com/#/notes/3188446).

> ### Note:  
> This adapter exchanges data with a remote component that might be outside the scope of SAP. Make sure that the data exchange complies with your company’s policies.



<a name="loio5e143a5b3e664284a4415e760a192eda__ashweq30223"/>

## How the GoTo Webinar Receiver Adapter Works

If you have configured the GoTo Webinar receiver adapter, data exchange is performed as follows at runtime: SAP Integration Suite tenant sends the operation request to GoTo Webinar \(this is a receiver system\), GoTo Webinar works on the request and sends the data back to the SAP Integration Suite tenant.



## Configure the GoTo Webinar Receiver Adapter

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

*Address*

</td>
<td valign="top">

Specify the GoTo Webinar Address.

Example: `https://api.getgo.com`

</td>
</tr>
<tr>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

Select the method to connect to GoTo Webinar:

-   *OAuth2 Authorization Code* 
-   *Personal Access Token*



</td>
</tr>
<tr>
<td valign="top">

*Credentials Name*

\(Only available when the *OAuth2 Authorization Code* is selected\)

</td>
<td valign="top">

Specify the OAuth2 Authorization Code artifact that stores the Client ID and Client Secret.

</td>
</tr>
<tr>
<td valign="top">

*Client ID Alias*

\(Only available when the *Personal Access Token* is selected\)

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the Client ID.

</td>
</tr>
<tr>
<td valign="top">

*Client Secrets Alias*

\(Only available when the *Personal Access Token* is selected\)

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the Client Secret.

</td>
</tr>
<tr>
<td valign="top">

*Personal Access Token Alias*

\(Only available when the *Personal Access Token* is selected\)

</td>
<td valign="top">

Specify the Secure Parameter alias that stores the Personal Access Token.

</td>
</tr>
<tr>
<td valign="top">

*Reuse Connection*

</td>
<td valign="top">

Enable this property to reuse the connection.

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

Specify the maximum waiting time \(in milliseconds\) for a response to be received from the GoTo Webinar service.

Example: `60000`

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

*API Version*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the required version.

</td>
</tr>
<tr>
<td valign="top">

*Entity*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the entity based on which the operation will be performed.



</td>
</tr>
<tr>
<td valign="top">

*Operation*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Select the desired operation from the dropdown.

</td>
</tr>
<tr>
<td valign="top">

*Operation Parameters*

\(Only available when the *Configuration Type* is *Basic*\)

</td>
<td valign="top">

Specify the operation parameters as a key-value pair.

</td>
</tr>
<tr>
<td valign="top">

*Query*

</td>
<td valign="top">

Specify the expression containing the query parameter and value.

Example: `fromTime=2026-03-13T10%3A00%3A00Z&toTime=2026-04-15T22%3A00%3A00Z`

</td>
</tr>
<tr>
<td valign="top">

*HTTP Method*

\(Only available when the *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Select the required method from the available dropdown:

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

Specify the relative endpoint, excluding the Host.

Example: `organizers/:organizerKey/webinars`

</td>
</tr>
<tr>
<td valign="top">

*Send Body*

\(Only available when the *Configuration Type* is *Advanced*\)

</td>
<td valign="top">

Select to pass the payload as the request body.

> ### Note:  
> In Content Modifier, set header as content-type = application/json



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

