<!-- loioefebd504386846389e0c60cd2fcb4edf -->

# Set Default Runtime Profile

The tenant administrator can view and configure a runtime profile, to mark one of them as default for the tenant.



## Prerequisites

-   For Cloud Integration runtime, the Cloud Integration capability should be active. See [Activating and Managing Capabilities](https://help.sap.com/docs/integration-suite/sap-integration-suite/activating-and-managing-capabilities?version=CLOUD&ai=true)
-   For Integration Cell and Edge Integration Cell runtimes, the runtimes should be explicitly activated See [Activate Integration Cell](https://help.sap.com/docs/integration-suite/isuite-integrations-and-apis/activate-integration-cell?version=CLOUD&ai=true) and [Activate Edge Integration Cell](https://help.sap.com/docs/integration-suite/isuite-edge-integration-cell/activate-edge-integration-cell?version=CLOUD&ai=true)



## Context

Runtime profile is a collection of capabilities such as success factor adapter, splitter or datastore elements, available for a particular product. You can consume these capabilities at the time of designing integration flows.

The tool enables you to design for multiple runtimes at the same time. You should select specific runtime profile to develop content for the respective runtime. You can execute the following steps to configure a runtime profile for a tenant.



## Procedure

1.  Choose *Settings* \> *Integration*.

    > ### Note:  
    > You can click on the runtime profile name under *Name* field to see the available capabilities for the relevant profile.

2.  Choose *Edit* in the *Runtime Profiles* tab page.

3.  Select the radio button for the runtime profile you want to mark as default.

4.  Choose *Save* or *Cancel* as appropriate.

    > ### Note:  
    > You can also configure runtime profile at integration flow level. For more details please refer to [Configure Runtime Profile for an Integration Flow](configure-runtime-profile-for-an-integration-flow-65cc0bc.md).


**Related Information**  


[Runtime Profiles](runtime-profiles-8007daa.md "Integration Suite allows you to design integration content for different target integration platforms. Accordingly, different runtime profiles are available to adapt the user interface of the integration content designer to the specifications and capabilities of the target integration platform.")

