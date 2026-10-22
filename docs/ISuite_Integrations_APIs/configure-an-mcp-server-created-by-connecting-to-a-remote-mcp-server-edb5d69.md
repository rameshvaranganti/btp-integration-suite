<!-- loioedb5d6996911409280e269f123927112 -->

# Configure an MCP Server Created by Connecting to a Remote MCP Server

After creating an MCP server from a remote MCP server, you can customize its behavior, control the exposed tools, resources, and prompts, and define how agents interact with the remote MCP server.

An MCP server created from a remote MCP server is a versioned entity that you can manage independently within SAP Integration Suite. After creation, you can further customize and manage it by:

-   Selecting and refining the tools, resources, and prompts exposed to agents.
-   Configuring policies to enforce security, traffic control, and governance.
-   Synchronizing updates from the remote MCP server to keep the MCP server definition aligned with the latest changes. If the remote MCP server definition changes \(for example, new tools or resources are added, or existing ones are modified\), you can use the **Synchronize** option to align the MCP server with the latest changes without recreating it.



## MCP Configuration

In the *MCP Configuration* tab, you can configure the core capabilities exposed by the MCP server. You can view the source and add or manage tools, resources, and prompts available to agents.



### Source

The **Source** tab displays the configuration used to connect to the remote MCP server.

> ### Note:  
> When configuring the remote MCP server source, you can use different destinations for discovering the server and for runtime invocation. By default, the same destination is used for both..


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

**Source Type**

</td>
<td valign="top">

Displays the source type used to create the MCP server. For this source, the value is **MCP Server**.

</td>
</tr>
<tr>
<td valign="top">

**Discovery Destination**

</td>
<td valign="top">

Specifies the destination used to discover the remote MCP server and retrieve its tools, resources, and prompts.

</td>
</tr>
<tr>
<td valign="top">

**Runtime Destination**

</td>
<td valign="top">

Specifies the destination used when agents invoke the remote MCP server through the MCP server in Integration Suite. By default, this is the same as the discovery destination, but you can configure a different destination if required.

> ### Note:  
> If your remote MCP server requires different authentication mechanisms for tool, resource, or prompt execution, you can configure a different runtime destination in the **Source** tab.



</td>
</tr>
<tr>
<td valign="top">

**Relative Path**

</td>
<td valign="top">

Specifies the relative path of the remote MCP server endpoint. The runtime endpoint is constructed by combining the destination URL with this relative path.

</td>
</tr>
</table>



### Tools

The **Tools** tab displays the tools exposed by the remote MCP server that are available for agent consumption. You can control which tools are exposed through the MCP server in Integration Suite.

To add and expose tools:

1.  Go to the *MCP Configuration* \> *Tools* tab and choose *Add*.
2.  Select the tools that you want to expose from the list of tools discovered from the remote MCP server, and choose *Add*.

    > ### Note:  
    > Each MCP server supports up to 50 tools.


The selected tools are added to the MCP server. For each tool, you can:

-   Review the **Name**, **Title**, and **Description**.
-   View the tool definition provided by the remote MCP server.
-   Remove tools that you no longer want to expose by selecting the tool and choosing *Delete*.



### Resources

You can expose specific resources discovered from the remote MCP server for AI agent consumption. These resources provide agents with read-only access to structured data and contextual information exposed by the remote MCP server.

1.  Go to *MCP Configuration* and choose the *Resources* tab. Choose *Add* to open the resource selection dialog.

2.  Select the resources that you want to expose and choose *Add* to include them in your MCP server.

    > ### Note:  
    > -   Only the resources with GET method will be listed for MCP resources.
    > -   Each MCP server supports up to 30 MCP resources.


The selected resources are added to the MCP server. For each resource, you can:

-   Review or modify the **Name**, **Title**, and **Description**.

-   Compare the resource details with those of the source remote MCP server.

-   Review the **resource schema** provided by the remote MCP server. The resource schema defines the URI template used to access the resource and the MIME type of the content returned.

-   Use **API Reference** to review the corresponding source API operation and its parameters.




### Prompts

Prompts define reusable interaction patterns that agents can use to interact with an MCP server in a consistent and structured way. You can either create a new prompt by choosing *New Prompts* or import prompts discovered from the remote MCP server by choosing *Remote Server Prompts*.

You can add prompts to the MCP server in the following ways:

-   Add a new prompt
    1.  Go to *MCP Configuration* and choose the *Prompts* tab, and choose *Add* \> *New Prompts*.
    2.  In *Define Prompt*, provide a **Name**, **Title**, and **Description**, and choose *Next*.
    3.  In *Define Arguments*, define the following input arguments for the prompt and choose *Next*:
        -   Specify a **Name** for the argument.

        -   Optionally, provide a **Title** and **Description**.

        -   Select **Required** if the argument is mandatory.

        -   Add additional arguments if needed.


    4.  In **Define Messages** dialog, select a role and enter the corresponding message content:
        -   **User**: Represents input or a request from the user.

        -   **Assistant**: Represents a response, instruction, or context provided by the assistant.

        -   Add additional messages as needed to define the interaction flow.


    5.  Choose *Add* to save the prompt.

        > ### Note:  
        > To define a prompt, you must define the prompt and messages. Defining arguments is optional.


-   Add remote server prompts
    1.  In the ***Prompts*** step, choose *Add* \> *Remote Server Prompts*.

        If prompts are available on the remote MCP server, they are automatically discovered and listed in the *Add Prompts* dialog.

    2.  Select one or more prompts and choose *Add* to create copies of them in the MCP server you are configuring. After adding the prompts, you can modify the copied prompts as needed.




## MCP Policy Configuration

Policies govern how tools are accessed and executed.

1.  Navigate to the *Policies* tab.
2.  Add and configure policies as needed. See, [Add Policies to Artifacts](add-policies-to-artifacts-c2b3e56.md) 

    > ### Note:  
    > -   By default, **Authentication** and **Authorization** policies are applied to an MCP server. These policies are mandatory and cannot be deleted.
    > 
    > -   The **Authentication** policy must always be the first policy in the request flow. Only **OAuth-based authentication** is supported for an MCP server.
    > 
    > -   If the MCP server is created from an API artifact, the **Authentication** policy configuration is inherited from the source API artifact.
    > 
    > 
    > The following policies are supported for MCP servers and can be configured under the *Policies* section:
    > 
    > -   Traffic Management: [Quota](quota-2aecf15.md), [Surge Protection](surge-protection-3d14745.md), and [IP Filter](ip-filter-3a8b424.md) 
    > 
    > -   Security Policies: [Authentication](authentication-fa6eec4.md) and [Authorization](authorization-6658409.md)
    > 
    > 
    > By default, all MCP tools are protected with an Authentication and Authorization policy. This ensures that only authenticated and authorized agents—typically with proper credentials and identity assertions—can invoke the tool. To maintain system performance and prevent overload during traffic spikes, you can configure a Surge Protection Policy—for example, limit each agent to 4 calls every 10 seconds. Any calls beyond this threshold will be temporarily blocked or throttled to protect backend systems.

    > ### Note:  
    > Only destinations with the *Proxy Type* set to `Internet` or `OnPremise` are currently supported.
    > 
    > The following authentication mechanisms are supported:
    > 
    > **Supported Authentication Mechanisms**
    > 
    > 
    > <table>
    > <tr>
    > <th valign="top">
    > 
    > Proxy Type
    > 
    > </th>
    > <th valign="top">
    > 
    > Authentication Mechanism
    > 
    > </th>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > Internet
    > 
    > </td>
    > <td valign="top">
    > 
    > -   ClientCertificateAuthentication
    > 
    > -   OAuth2ClientCredentials
    > 
    > -   NoAuthentication
    > 
    > -   BasicAuthentication
    > 
    > -   OAuth2Password
    > 
    > -   OAuth2JWTBearer
    > 
    > -   SAMLAssertion
    > 
    > -   OAuth2SAMLBearerAssertion
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > <tr>
    > <td valign="top">
    > 
    > OnPremise
    > 
    > </td>
    > <td valign="top">
    > 
    > -   OAuth2ClientCredentials
    > 
    > -   NoAuthentication
    > 
    > -   BasicAuthentication
    > 
    > -   PrincipalPropagation
    > 
    > -   OAuth2Password
    > 
    > -   OAuth2JWTBearer
    > 
    > -   SAMLAssertion
    > 
    > -   OAuth2SAMLBearerAssertion
    > 
    > 
    > 
    > 
    > </td>
    > </tr>
    > </table>
    > 
    > To set up a HTTP destination from scratch, navigate to SAP BTP Cockpit, select *Destination* from the side navigation pane, and follow the step-by-step instructions in [Create HTTP Destinations](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/create-http-destinations?version=Cloud).

    > ### Note:  
    > The Authentication and Authorization policies are added by default when an MCP server is created from an API artifact. The Authentication policy is read-only because its configuration is inherited from the source API artifact. The Authorization policy remains editable and can be configured independently for the MCP server.

    > ### Note:  
    > For MCP servers created from API artifacts, if the source API includes an **Authorization** policy, enable **Trust Upstream MCP Authorization** in the API artifact's Authorization policy. This allows the API artifact to trust the authorization performed by the MCP server and prevents duplicate authorization checks.




## MCP Adapter Configuration

Adapters define how an MCP server receives requests from agents and communicates with the target backend service.

Every MCP server contains two adapters:

-   **MCP Sender Adapter** – Receives incoming requests from agents and exposes the MCP endpoint. This adapter is created automatically and cannot be modified.

    **Configuration Properties**


    <table>
    <tr>
    <th valign="top">

    Section
    
    </th>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Value/Options
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    General
    
    </td>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Specifies the name of the sender adapter. By default, the value is **MCP**.
    
    </td>
    <td valign="top">
    
    MCP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Specifies an optional description for the sender adapter. Use this field to provide additional information about the adapter configuration.
    
    </td>
    <td valign="top">
    
    User-defined
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter Type
    
    </td>
    <td valign="top">
    
    Displays the type of the sender adapter. The value is **MCP** and is read-only. The MCP sender adapter receives incoming Model Context Protocol \(MCP\) requests from agents and exposes the MCP server endpoint.
    
    </td>
    <td valign="top">
    
    MCP
    
    </td>
    </tr>
    </table>
    
-   **MCP Receiver Adapter** – Connects the MCP server to the selected source API artifact. It forwards requests received by the MCP sender adapter to the API artifact for processing.

    When an MCP server is created with an **API** as the source, the HTTP receiver adapter displays the following properties:

    **Configuration Properties**


    <table>
    <tr>
    <th valign="top">

    Section
    
    </th>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Value/Options
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="3">
    
    General
    
    </td>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Name of the receiver adapter channel.
    
    </td>
    <td valign="top">
    
    MCP
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    Optional description for the adapter.
    
    </td>
    <td valign="top">
    
    User-defined
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Adapter Type
    
    </td>
    <td valign="top">
    
    Type of adapter used for backend communication.
    
    </td>
    <td valign="top">
    
    MCP
    
    </td>
    </tr>
    <tr>
    <td valign="top" rowspan="6">
    
    Connection
    
    </td>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Displays the type of backend connection. When the MCP server is created from a remote or a third-party MCP server, the value is **MCP Provider** and is read-only.
    
    </td>
    <td valign="top">
    
    MCP Provider
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Destination
    
    </td>
    <td valign="top">
    
    The pre-configured API Provider destination used to reach the backend system.
    
    </td>
    <td valign="top">
    
    Destination name
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Proxy Type
    
    </td>
    <td valign="top">
    
    Defines how the backend is reached.
    
    </td>
    <td valign="top">
    
    The type of proxy that you are using to connect to the target system:

    -   Select **Internet** if you are connecting to a cloud system.

    -   Select **On-Premise** if you are connecting to an on-premise system.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication
    
    </td>
    <td valign="top">
    
    Authentication mechanism used to invoke the backend service.
    
    </td>
    <td valign="top">
    
    Defines how the tenant \(as the HTTP client\) authenticates itself against the receiver.

    The following authentication mechanisms are supported:

    -   Internet
        -   ClientCertificateAuthentication

        -   OAuth2ClientCredentials

        -   NoAuthentication

        -   BasicAuthentication

        -   OAuth2Password

        -   OAuth2JWTBearer

        -   SAMLAssertion

        -   OAuth2SAMLBearerAssertion


    -   OnPremise
        -   OAuth2ClientCredentials

        -   NoAuthentication

        -   BasicAuthentication

        -   PrincipalPropagation

        -   OAuth2Password

        -   OAuth2JWTBearer

        -   SAMLAssertion

        -   OAuth2SAMLBearerAssertion




    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    URL
    
    </td>
    <td valign="top">
    
    The endpoint URL resolved from the selected API Provider destination.
    
    </td>
    <td valign="top">
    
    Auto-populated from destination
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Timeout \(in ms\)
    
    </td>
    <td valign="top">
    
    Specifies the time \(in milliseconds\) that the client waits for a response before the connection is interrupted.

    The default value is 60000 milliseconds \(1 minute\).
    
    </td>
    <td valign="top">
    
    60000
    
    </td>
    </tr>
    </table>
    

