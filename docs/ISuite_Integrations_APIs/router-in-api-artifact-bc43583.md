<!-- loiobc43583819a0456aa15a3057a488ca41 -->

# Router in API Artifact

The Router in API artifacts enables you to control message flow by routing messages based on conditions, splitting composite messages, aggregating multiple messages, or sending copies to multiple routes.

You use the Router in an API artifact to:

-   Route messages to specific receivers or interfaces based on conditions.
-   Split composite messages into individual messages for separate processing.
-   Combine or aggregate multiple messages into a single message.
-   Send copies of the same message to multiple routes in parallel or sequential order.



## Routing Capabilities and Restrictions

The capabilities and restrictions of the Router depend on where it is placed in the flow:

-   When a router is added after the security and traffic management policies, the Router supports the following routing condition types:

    -   Header-based conditions using `header.<name>` as the expression root
    -   Exchange property conditions using `property.<name>` as the expression root
    -   XML and non-XML payload conditions

-   You can place a Router before any security policy \(except authentication policies\) and before any traffic management policy. In this position, the following restrictions apply:

    -   Only non-XML conditions are supported. XML-based conditions are not allowed in this position. The UI enforces this through field-level validation.
    -   Conditions must use `header.<name>` as the expression root. Header-based conditions are fully supported end-to-end.
    -   The Exception Subprocess does not handle errors generated during policy execution when the Router step is placed before security policies \(except authentication policies\) or traffic management policies.




## Configuring the Router Step

To add and configure a Router step in your API artifact, including defining routing conditions, expression types, and the default route, see [Define Router](define-router-d7fddbd.md).

