<!-- loio4b89a8b4d0f54797aca4a9e951be7d90 -->

# Manage Content

As a content administrator, you can create products that include API, Events, and AI artifacts from different business systems, and manage the content that application developers can view on the catalog.

To illustrate the benefits of this feature, let's consider an example. Imagine you work for XYZ company and you are tasked with building an application. To accomplish this, you need to utilize APIs such as the sales order or CRM APIs from S4HANA, payroll APIs from SuccessFactors, and marketing solution APIs from SAP Marketing Cloud. Using this feature, you can enhance the extensibility of these APIs and leverage them to build your application and address any challenges you encounter.

![Architecture diagram showing the process of adding and registering business systems in the System Landscape within SAP Business Technology Platform.](images/ABHE_DEV_Edition_3b25f9f.png)

The block diagram illustrates the process of adding and registering business systems in the System Landscape within SAP Business Technology Platform. Once a business system is added and registered, it can be found in Developer Hub. To discover the APIs within these systems, the content admin creates and publishes products, making them visible in the catalog. They can incorporate pertinent API documentation and ensure that this catalog is readily available to developers. Once they appear in the catalog, developers can explore and utilize these APIs to develop applications.

To achieve these objectives, your *Global Account Administrator* needs to register these systems in your system landscape. This action establishes a connection between the SAP system and SAP BTP. Following system registration, these systems appear on the *Manage Content* page in Developer Hub. For more information, see [Discover and Publish APIs from Business Systems](discover-and-publish-apis-from-business-systems-0cea56f.md).

> ### Note:  
> At present, you can only register and add S/4 HANA Cloud business systems.



## Artifacts

Developer Hub supports the following artifact types, which you can publish and manage to make them discoverable and consumable by API consumers in the catalog.


<table>
<tr>
<th valign="top">

Artifacts

</th>
<th valign="top">

Types

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

API

</td>
<td valign="top">

 

</td>
<td valign="top">

API artifacts are the core building blocks used to design, configure, publish, and manage APIs in SAP Integration Suite, API Management. These artifacts define how APIs behave, how they interact with backend systems, and how they are exposed to consumers. See [API Artifact](api-artifact-a4f87b1.md)

</td>
</tr>
<tr>
<td valign="top">

Events

</td>
<td valign="top">

 

</td>
<td valign="top">

Also known as an asynchronous or event-driven API, that enables applications to exchange data in real time by listening for and reacting to specific events, rather than relying on repeated polling or manual requests.

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

AI

</td>
<td valign="top">

MCP Server

</td>
<td valign="top">

An MCP Server is an artifact you create in SAP Integration Suite to expose your enterprise APIs and data to AI agents in a structured, governed way. See [MCP Server](mcp-server-9eb9239.md)

</td>
</tr>
<tr>
<td valign="top">

LLM-Proxy

</td>
<td valign="top">

An API artifact in SAP Integration Suite that exposes LLM services as an OpenAI-compatible interface, enabling governed access to AI models for applications and agents. See  <?sap-ot O2O class="- topic/xref " href="92a895edc6904e6e90b3b8c05bc8f423.xml" text="" desc="" xtrc="xref:4" xtrf="file:/home/builder/src/dita-all/slu1713332208086/loiod8a6092f89b24b5e8531d35c034be3aa_en-US/src/content/localization/en-us/4b89a8b4d0f54797aca4a9e951be7d90.xml" output-class="" outputTopicFile="file:/home/builder/tp.net.sf.dita-ot/2.3/plugins/com.elovirta.dita.markdown_1.3.0/xsl/dita2markdownImpl.xsl" ?> .

</td>
</tr>
</table>

