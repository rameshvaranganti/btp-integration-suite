<!-- loio3846eef6b00f40858ff56761098f2eac -->

# Routing

Use the Routing flow step \(Router\) to direct messages along different processing paths based on configurable conditions. At runtime, the Router evaluates conditions in the order in which they are defined and forwards the message to the first matching route.

> ### Note:  
> The *Throw Exception* option is selected to set the behavior of the router to respond to error occurrence.

**Routing Steps**


<table>
<tr>
<th valign="top">

Policy

</th>
<th valign="top">

Sub Category

</th>
<th valign="top">

Policy Definition

</th>
<th valign="top">

Runtime Support

</th>
<th valign="top">

Important Notes/Links

</th>
</tr>
<tr>
<td valign="top">

Aggregator

</td>
<td valign="top">



</td>
<td valign="top">

Combines related individual messages so that they can be processed in bulk. By using an Aggregator pattern, you can collect and store individual messages until a complete set of related messages has been received.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Aggregator](define-aggregator-aa23816.md).

</td>
</tr>
<tr>
<td valign="top">

Gather

</td>
<td valign="top">



</td>
<td valign="top">

Merges messages from different routes \(into a single message\) with the option to define certain strategies how to combine the initial messages.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Gather and Join](define-gather-and-join-94ef1f2.md).

</td>
</tr>
<tr>
<td valign="top">

Join

</td>
<td valign="top">



</td>
<td valign="top">

Used in combination with the Gather step. It brings together the messages from different routes, but it does not affect the content of the messages.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Gather and Join](define-gather-and-join-94ef1f2.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

Multicast

</td>
<td valign="top">

Parallel Multicast

</td>
<td valign="top" rowspan="2">

Sends copies of the same message to multiple routes. You can send copies to all routes at once using *Parallel Multicast* or in an order of your choice using *Sequential Multicast*. This allows you to perform multiple operations on the same message in a single integration process.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top" rowspan="2">

For more information, see [Define Multicast](define-multicast-17de3ea.md).

</td>
</tr>
<tr>
<td valign="top">

Sequential Multicast

</td>
<td valign="top">

-   Edge Integration Cell



</td>
</tr>
<tr>
<td valign="top">

Router

</td>
<td valign="top">



</td>
<td valign="top">

Specifies conditions based on which the messages are routed to a receiver or an interface during runtime.

</td>
<td valign="top">

-   Integration Cell
-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Router in API Artifact](router-in-api-artifact-bc43583.md) and [Define Router](define-router-d7fddbd.md).

</td>
</tr>
<tr>
<td valign="top" rowspan="7">

Splitter

</td>
<td valign="top">

EDI Splitter

</td>
<td valign="top">

Splits inbound bulk EDI messages, configure the splitter to validate and acknowledge the inbound messages.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define EDI Splitter](define-edi-splitter-584a3be.md).

</td>
</tr>
<tr>
<td valign="top">

General Splitter

</td>
<td valign="top">

Splits a composite message comprising N messages into N individual messages, each containing 1 message with the enveloping elements of the composite message.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define General Splitter](define-general-splitter-a6c1916.md).

</td>
</tr>
<tr>
<td valign="top">

IDoc Splitter

</td>
<td valign="top">

Splits a composite IDoc message into a series of individual IDoc messages. Each individual message contains the enveloping elements of the composite IDoc message.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define IDoc Splitter](define-idoc-splitter-4f250e4.md).

</td>
</tr>
<tr>
<td valign="top">

Iterating Splitter

</td>
<td valign="top">

Splits a composite message into a series of smaller messages without copying the enveloping elements of the composite message

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Iterating Splitter](define-iterating-splitter-d61d6ec.md).

</td>
</tr>
<tr>
<td valign="top">

PKCS\#7/CMS Splitter

</td>
<td valign="top">

Separates a PKCS7 Signed Data message into two files: one containing the signature and the other containing the original content.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define PKCS\#7/CMS Splitter](define-pkcs-7-cms-splitter-6c1649b.md).

</td>
</tr>
<tr>
<td valign="top">

Tar Splitter

</td>
<td valign="top">

Splits an archive \(.tar\) file into individual files.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Tar Splitter](define-tar-splitter-0f49759.md).

</td>
</tr>
<tr>
<td valign="top">

Zip Splitter

</td>
<td valign="top">

Splits an archive \(.zip\) file into individual files.

</td>
<td valign="top">

-   Edge Integration Cell



</td>
<td valign="top">

For more information, see [Define Zip Splitter](define-zip-splitter-4c0e3b8.md).

</td>
</tr>
</table>

