<!-- loio8dbb4acd4f854d369314469fe4b7c9a9 -->

# Configure the RNIF Sender Adapter

Configure the RNIF sender adapter for SAP Cloud Integration to receive RosettaNet messages from a trading partner over HTTPS.

After you create a sender channel and select the RNIF sender adapter, configure the following attributes:

> ### Note:  
> If a parameter is not set, the corresponding feature is disabled or default values are used.



## Connections Tab

Select the *Connections* tab and provide values in the following fields:


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Address*

</td>
<td valign="top">

Endpoint Configuration

</td>
<td valign="top">

Configure the URL path for the endpoint. The address must start with `/` and must be unique per tenant. The full path is: `/RNIF20/RNIF20/{url}`

</td>
</tr>
<tr>
<td valign="top">

*Authorization*

</td>
<td valign="top">

Endpoint Configuration

</td>
<td valign="top">

Select the authorization type for incoming requests:

-   *User Role*: Authorization is performed against a configured user role.
-   *Client Certificate*: Authorization is performed using the client certificate presented by the sender.

> ### Note:  
> *Client Certificate* authorization for the sender channel is supported for Cloud runtime only. Select *User Role* authorization for Edge Integration Cell.



</td>
</tr>
<tr>
<td valign="top">

*User Role* 

> ### Note:  
> Only visible when *User Role* is selected.



</td>
<td valign="top">

Endpoint Configuration

</td>
<td valign="top">

Enter the user role required to access this endpoint. The default is: `ESBMessaging.send`

</td>
</tr>
<tr>
<td valign="top">

*Subject DN* 

> ### Note:  
> Only visible when *Client Certificate* is selected.



</td>
<td valign="top">

Client Certificate Authorization

</td>
<td valign="top">

Enter the allowed client certificate Subject DN entries, separated by commas. The system only accepts certificates with a matching Subject DN.

</td>
</tr>
<tr>
<td valign="top">

*Issuer DN* 

> ### Note:  
> Only visible when *Client Certificate* is selected.



</td>
<td valign="top">

Client Certificate Authorization

</td>
<td valign="top">

Enter the allowed client certificate Issuer DN entries, separated by commas. The system accepts only certificates issued by these certificate authorities.

</td>
</tr>
<tr>
<td valign="top">

*Maximum Request Body Size \(in MB\)*

</td>
<td valign="top">

Request Limits

</td>
<td valign="top">

Enter the maximum size allowed for incoming request bodies, in MB. The accepted range is 1–500 MB. The default is 40 MB.

</td>
</tr>
</table>



## Processing Tab

Select the *Processing* tab and provide values in the following fields:


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Configuration Source*

</td>
<td valign="top">

Partner Interface Process \(PIP\) Details

</td>
<td valign="top">

Choose the source for the processing configuration:

-   *Dynamic*: The incoming message. The system reads all PIP and security parameters from the Partner Directory at runtime. For more details, see [Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md).
-   *Static from Channel*: The channel configuration.



</td>
</tr>
</table>

These fields are visible only when *Configuration Source* is set to *Static*:


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Action Type*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Select the PIP action type:

-   **Single-Action Request**
-   **Two-Action Request**



</td>
</tr>
<tr>
<td valign="top">

*PIP Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the PIP standard code \(for example, `3A4`\).

</td>
</tr>
<tr>
<td valign="top">

*PIP Version*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the PIP version \(for example, `V02.02`\).

</td>
</tr>
<tr>
<td valign="top">

*Business Transaction Activity*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the business transaction activity name.

</td>
</tr>
<tr>
<td valign="top">

*Requesting Action*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the requesting action of the PIP.

</td>
</tr>
<tr>
<td valign="top">

*Responding Action* 

> ### Note:  
> Only visible when *Action Type* is set to *Two-Action Request*.



</td>
<td valign="top">

Partner Interface Process \(PIP\) Configuration

</td>
<td valign="top">

Specifies the business action used for the response side of a two-action PIP.

</td>
</tr>
<tr>
<td valign="top">

*Current Role*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the current role in the PIP exchange \(for example, `Buyer`\).

</td>
</tr>
<tr>
<td valign="top">

*Partner Role*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the partner role in the PIP exchange \(for example, `Seller`\).

</td>
</tr>
<tr>
<td valign="top">

*Current Business Service Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the current business service code.

</td>
</tr>
<tr>
<td valign="top">

*Partner Business Service Code*

</td>
<td valign="top">

Partner Interface Process Configuration

</td>
<td valign="top">

Enter the partner business service code.

</td>
</tr>
</table>



## Exchange Pattern


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Exchange Type*

</td>
<td valign="top">

Exchange Pattern

</td>
<td valign="top">

Selects the exchange pattern for the RNIF action and signal messages in the configured PIP.

-   *Asynchronous*. Use when the RNIF conversation requires asynchronous action and signal message handling.
-   *Synchronous*. Use when the RNIF conversation is handled in a synchronous exchange pattern.
-   *Dynamic*. Resolves the exchange type at runtime from an exchange property or message header.



</td>
</tr>
<tr>
<td valign="top">

*Callback URL*

</td>
<td valign="top">

Exchange Pattern

</td>
<td valign="top">

Enter the URL to which the trading partner delivers the asynchronous response message.

</td>
</tr>
<tr>
<td valign="top">

*Callback URL Credential Name*

> ### Note:  
> Only visible when *Exchange Type* is set to *Asynchronous*.



</td>
<td valign="top">

Exchange Pattern

</td>
<td valign="top">

Enter the name of the security credential used to authenticate inbound requests received at the callback URL.</p\>

</td>
</tr>
<tr>
<td valign="top">

*Time to Acknowledge \(in ms\)*

> ### Note:  
> Only visible when *Exchange Type* is set to *Asynchronous*.



</td>
<td valign="top">

Exchange Pattern

</td>
<td valign="top">

Enter the maximum time in milliseconds within which the trading partner must send an acknowledgment after receiving the message.

</td>
</tr>
<tr>
<td valign="top">

*Time to Perform \(in ms\)*

> ### Note:  
> Only visible when *Exchange Type* is set to *Asynchronous*.



</td>
<td valign="top">

Exchange Pattern

</td>
<td valign="top">

Enter the maximum time in milliseconds within which the trading partner must complete the business transaction.

</td>
</tr>
<tr>
<td valign="top">

*Asynchronous Retry Count*

> ### Note:  
> Only visible when *Exchange Type* is set to *Asynchronous*.



</td>
<td valign="top">

Exchange Pattern

</td>
<td valign="top">

Enter the number of times the adapter retries sending the message if no acknowledgment is received within the acknowledgment timeout period.

</td>
</tr>
<tr>
<td valign="top">

*Asynchronous Retry Interval \(in ms\)*

> ### Note:  
> Only visible when *Exchange Type* is set to *Asynchronous*.



</td>
<td valign="top">

Exchange Pattern

</td>
<td valign="top">

Enter the time in milliseconds to wait between retry attempts.

</td>
</tr>
</table>



## Security Tab

Select the *Security* tab and provide values in the following fields.

> ### Remember:  
> When *Configuration Source* is set to *Dynamic*, the system reads the security parameters directly from the Partner Directory, and you cannot edit the fields below. For more information, see [Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md).


<table>
<tr>
<th valign="top">

**Parameter**

</th>
<th valign="top">

**Section**

</th>
<th valign="top">

**Description**

</th>
</tr>
<tr>
<td valign="top">

*Validate Signature of Request Message*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Choose this option to validate the digital signature on the incoming request message.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias \(Signature Validation\)* 

> ### Note:  
> Only visible when *Validate Signature* is enabled.



</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Enter the private key alias used for signature validation.

</td>
</tr>
<tr>
<td valign="top">

*Decrypt Request Message*

</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Choose this option to decrypt inbound request messages.

</td>
</tr>
<tr>
<td valign="top">

*Private Key Alias \(Decryption\)* 

> ### Note:  
> Only visible when *Decrypt Request Message* is enabled.



</td>
<td valign="top">

Request Security

</td>
<td valign="top">

Enter the private key alias used for decryption.

</td>
</tr>
<tr>
<td valign="top">

*Encrypt Response Message*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Choose this option to encrypt the outgoing response message.

</td>
</tr>
<tr>
<td valign="top">

*Encryption Scope*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Select which part of the response is encrypted:

-   **Payload**
-   **Payload Container**



</td>
</tr>
<tr>
<td valign="top">

*Encryption Algorithm*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Select the encryption algorithm:

-   *RC2*
-   *3DES*
-   *AES128*
-   *AES256*



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias \(Encryption\)*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Enter the public key alias used to encrypt the response.

</td>
</tr>
<tr>
<td valign="top">

*Sign Response Message*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Choose this option to digitally sign the outgoing response message.

</td>
</tr>
<tr>
<td valign="top">

*Signing Algorithm*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Select the signing algorithm:

-   *SHA-1*
-   *SHA-256*
-   *SHA-384*
-   *SHA-512*



</td>
</tr>
<tr>
<td valign="top">

*Public Key Alias \(Signing\)*

</td>
<td valign="top">

Response Security

</td>
<td valign="top">

Enter the public key alias used for signing.

</td>
</tr>
</table>

**Related Information**  


[Configure the RNIF Receiver Adapter](configure-the-rnif-receiver-adapter-556d7e3.md "Configure the RNIF receiver adapter for SAP Cloud Integration to send RosettaNet messages to a trading partner over HTTPS.")

[Dynamic Configuration via Partner Directory](dynamic-configuration-via-partner-directory-a9cc79d.md "Configure the RNIF adapter to resolve Partner Interface Process (PIP) and security settings at runtime by looking up entries in the Partner Directory.")

