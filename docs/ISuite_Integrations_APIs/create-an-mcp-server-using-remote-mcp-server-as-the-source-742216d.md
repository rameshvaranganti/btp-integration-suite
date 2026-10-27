<!-- loio742216d01dfd4c58ab22090068216638 -->

# Create an MCP Server Using Remote MCP Server as the Source

Create an MCP server that uses a remote MCP server as its source, allowing SAP Integration Suite MCP server to act as a managed proxy and governance layer for AI agents.



## Prerequisites

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

-   Create a content package. See, [Creating an Integration Package](https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-integration-package?version=CLOUD).

-   Activate API Management capability. See, [Activate and Configure the API Management Capability](activate-and-configure-the-api-management-capability-f6eb433.md).

-   Activate Integration Cell runtime. See, [Activate Integration Cell](activate-integration-cell-1a627da.md).

-   Assign the *PI\_Integration\_Developer* role collection to yourself.

-   Set up a destination in SAP BTP cockpit to connect an MCP server to the remote MCP server. See, [Configure a Destination to Connect an MCP Server to a Remote MCP Server](configure-a-destination-to-connect-an-mcp-server-to-a-remote-mcp-server-1c8b388.md).

    > ### Note:  
    > Only destinations with the *Proxy Type* set to `Internet` are currently supported.
    > 
    > The following authentication mechanisms are supported:
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
    > </table>

    > ### Note:  
    > The MCP remote server must support the Streamable HTTP transport. Only MCP servers exposed through Streamable HTTP can be proxified.




## Context

A remote MCP server is an externally hosted server that provides tools, resources, and prompts through the Model Context Protocol \(MCP\).

SAP Integration Suite lets you connect to a remote MCP server and expose its capabilities through a single, managed endpoint. Integration developers can configure, discover, and synchronize the primitives of a remote MCP server, and selectively expose the tools, resources, and prompts needed by AI agents. Security and traffic policies can also be applied at the proxy layer, while the underlying remote MCP server remains unchanged.



## Procedure

1.  Log on to SAP Integration Suite.

2.  From the left navigation pane, choose *Design* \> *Integrations and APIs* to view the list of integration packages.

3.  Select the *<integration package\>* where you want to add an API artifact and choose *Edit*.

4.  On the *<integration package\>* details page, choose *Artifacts* and under the *Add* option, select *MCP Server*.

    The *Create MCP Server* dialog opens.

5.  Select *Remote MCP Servers* as the source type and choose *Next*.

    This option will enable you to create an MCP server from a remote or a third-party MCP server.

6.  Select a destination pointing to a remote MCP server. See, [Configure a Destination to Connect an MCP Server to a Remote MCP Server](configure-a-destination-to-connect-an-mcp-server-to-a-remote-mcp-server-1c8b388.md).

    Verify the *Name*, *URL*, and *Authentication* and choose *Next*

7.  In the *Provide MCP Details* step, fill in all the required details as follows:


    <table>
    <tr>
    <th valign="top">

    MCP Server Details
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Name
    
    </td>
    <td valign="top">
    
    Enter an intuitive name. Use only alphanumeric characters and special character such as underscore "\_".
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ID
    
    </td>
    <td valign="top">
    
    APIs are identified by their IDs on the home screen. You can use space and special characters such as underscore\(\_\), period\(.\), hyphen\(-\) in an ID.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Destination
    
    </td>
    <td valign="top">
    
    Displays the destination selected in the previous step. This destination is used to connect to the remote MCP server.

    > ### Note:  
    > By default, the destination you select here is also used for runtime execution. If your remote MCP server requires different authentication mechanisms for tool, resource, or prompt execution, you can configure a different runtime destination in the **Source** tab when editing the MCP server. See, [Configure a Destination to Connect an MCP Server to a Remote MCP Server](configure-a-destination-to-connect-an-mcp-server-to-a-remote-mcp-server-1c8b388.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Relative Path
    
    </td>
    <td valign="top">
    
    Specifies the relative path of the remote MCP server discovery/runtime endpoint. The runtime endpoint is constructed by combining the destination URL with this relative path. This field is optional.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    MCP Path
    
    </td>
    <td valign="top">
    
    Enter the path prefix for the MCP server. For example, `/BusinessPartner or BusinessPartner`. This defines the proxified endpoint under which the MCP server is exposed.

    > ### Note:  
    > The base path shouldn't be left empty or set to only "/".


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Version
    
    </td>
    <td valign="top">
    
    Add a version if you want to improve, upgrade, or customize the functional behavior of an existing MCP server. Versioning allows the creation and management of multiple concurrent versions of an MCP server.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Runtime Profile
    
    </td>
    <td valign="top">
    
    The runtime node on which the MCP server will be deployed.

    > ### Note:  
    > The MCP server can be only deployed and managed over Integration Cell runtime profile.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Virtual Host
    
    </td>
    <td valign="top">
    
    You can view the *Virtual Host URL* for the selected runtime profile. The virtual host defines the public-facing hostname, which is combined with the base path to expose your MCP server.

    For example, even if your backend service is hosted at `https://internal.services.local/orders`, you can expose it externally as `https://mcpserver.yourdomain.com/v1/orders` using a virtual host.

    This helps in the proxification of the internal URL, improving security and allowing for more flexible deployment configurations.
    
    </td>
    </tr>
    </table>
    
8.  In the *Create Tools* step, select the checkboxes next to the tools you want to expose from the remote MCP server.

    > ### Note:  
    > Each MCP server supports up to 50 tools.

9.  Choose *Add* to finalize and create the MCP server.

    Choose *Edit* to update the configuration \(all fields except ID\). Use the *MCP Configuration* tab to modify *Source*, *Tools*, *Resources*, and *Prompts*, and the *Policies* tab to configure traffic management and security policies. For detailed information, see [Configure an MCP Server Created by Connecting to a Remote MCP Server](configure-an-mcp-server-created-by-connecting-to-a-remote-mcp-server-edb5d69.md).


