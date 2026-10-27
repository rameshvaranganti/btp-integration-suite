<!-- loio256409f190b44a8fa8afd4834f89db65 -->

# Creating an MCP Server

You can create an MCP server by exposing different types of back-end systems or services as AI-accessible tools. Depending on your use case and the source you want to integrate, SAP Integration Suite provides multiple methods for creating an MCP server.

> ### Note:  
> Availability of this feature depends upon the SAP Integration Suite service plan that you use. For more information about different service plans and their supported feature set, see SAP Note [2903776](https://launchpad.support.sap.com/#/notes/2903776).

Choose the creation method that best suits your integration scenario:

<table>
<tr>
<th valign="top">

Source

</th>
<th valign="top">

Use When

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

API artifact

</td>
<td valign="top">

You already have an API artifact deployed on Integration Cell and want to expose its operations as tools that AI agents can discover and invoke.

</td>
<td valign="top">

[Create an MCP Server from an API Artifact](create-an-mcp-server-from-an-api-artifact-9f18140.md)

</td>
</tr>
<tr>
<td valign="top">

HTTP endpoint

</td>
<td valign="top">

You want to expose a REST-based service directly by providing its endpoint URL and OpenAPI specification, without first creating an API artifact.

</td>
<td valign="top">

[Create an MCP Server from an HTTP Endpoint](create-an-mcp-server-from-an-http-endpoint-b59f141.md)

</td>
</tr>
<tr>
<td valign="top">

RFC-based backend

</td>
<td valign="top">

You want to expose selected RFC operations of an RFC-based backend system, such as SAP S/4HANA or SAP ECC, as MCP tools.

</td>
<td valign="top">

[Create an MCP Server by Referring to an RFC-Based Backend](create-an-mcp-server-by-referring-to-an-rfc-based-backend-cbb8b78.md)

</td>
</tr>
<tr>
<td valign="top">

Remote MCP server

</td>
<td valign="top">

An MCP server already exists outside SAP Integration Suite, and you want SAP Integration Suite to act as a managed proxy and governance layer for AI agents that consume it.

</td>
<td valign="top">

[Create an MCP Server Using Remote MCP Server as the Source](create-an-mcp-server-using-remote-mcp-server-as-the-source-742216d.md)

</td>
</tr>
</table>

After you create an MCP server, you can refine its tool definitions for AI agent consumption without changing the source. See [MCP Server Tool Simplification](mcp-server-tool-simplification-cff5f03.md). To make the MCP server available to AI agents, deploy it. See [Deploy an MCP Server](deploy-an-mcp-server-017ba42.md).
