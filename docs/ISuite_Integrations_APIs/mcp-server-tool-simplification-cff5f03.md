<!-- loiocff5f03498384ef1a07de75ff97bf8cf -->

# MCP Server Tool Simplification

MCP server tool simplification lets developers refine the tool definitions exposed by an MCP server without modifying the underlying source artifact.

Working directly in the MCP server editor, developers can hide optional input and output parameters, simplify enum values, and update tool names, titles, and descriptions. The result is an agent-facing schema that contains only the information relevant to the intended use case.



## Why Agent-Facing Schemas Matter

MCP servers generated from API artifacts expose the full backend schema, which is designed for system-to-system integration rather than AI agent consumption. When agents use these schemas directly, three types of noise affect reliability and inference cost.

First, backend schemas can contain many fields, most of which are irrelevant to any single use case. The system passes all these fields to the agent in context on every tool call, consuming tokens regardless of their relevance to the task.

Second, parameters that use enum types can surface large sets of raw values that carry no inherent meaning for a large language model. Without a way to restrict the visible options, agents must process the full list, increasing the chance of incorrect selection.

Third, many backend fields lack descriptions because they were not designed for natural language interpretation. Without guidance, an agent doesn't know when or how to use these fields, which increases the risk of incorrect parameter usage.

In multi-tool agentic workflows, these issues multiply.

-   Every tool schema in the workflow is held in context simultaneously.
-   Token overhead and inference cost multiply across each step.

When you trim the agent-facing schema to include only what's relevant, you create more focused, cost-efficient, and reliable agent interactions.



## Non-Destructive Changes

Hiding a parameter is a non-destructive operation. The parameter is suppressed from the agent-facing schema at design-time, but the source artifact remains unchanged. You can make a hidden parameter visible again at any time without requiring a synchronization step. The same principle applies to enum values. You can hide individual enum values within a parameter's data type to restrict the options visible to the agent. You can restore them later if needed. For example, in a `get_SalesOrder` tool, you can hide the `orderby` parameter and remove the `_Partner` and `_PricingElement` expansion options. This produces a leaner schema that is less likely to confuse the agent and less costly to run.



## Synchronization with Source Artifacts

If you synchronize an MCP server with its source artifact after making tool simplification changes, refinements such as hidden parameters and enum values are preserved wherever possible. However, if an attribute that was previously hidden becomes a required field in the updated source, the hidden setting is automatically removed, and the attribute is displayed. This ensures that the agent always receives a valid, complete schema for mandatory inputs.

**Related Information**  


[MCP Server](mcp-server-9eb9239.md "An MCP Server is an artifact you create in SAP Integration Suite to expose your enterprise APIs and data to AI agents in a structured, governed way. It is built on the Model Context Protocol (MCP) which is an open-source protocol designed to bridge the gap between AI applications or agents and enterprise tools and data. Just as REST APIs connect web applications to data and services, MCP enables AI-native integrations by exposing tools, APIs, and data sources to AI Agents.")

[Refine and Streamline MCP Server Tool Definitions](refine-and-streamline-mcp-server-tool-definitions-3b90a0c.md "Refine the tool definitions in your MCP Server by adding or deleting tools, hiding parameters, simplifying enum values, and updating tool names and descriptions.")

