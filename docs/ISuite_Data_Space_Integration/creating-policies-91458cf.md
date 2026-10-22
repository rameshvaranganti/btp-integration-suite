<!-- loio91458cfbeba44478bce2e5aaec7b5801 -->

# Creating Policies

Create a policy in Data Space Integration.



<a name="loio91458cfbeba44478bce2e5aaec7b5801__context_whl_lbf_2yb"/>

## Context

You want to define policies that regulate how other members of the data space can use your assets.

In a contract definition, policies can function either as **access policy** or **usage policy**, which means they either define who can use an asset \(access\) or for how long and in what manner \(usage\). You must have defined at least two policies to use them in a contract definition: one to be used as access policy, and one as usage policy.

Rules are collected in the following categories:

-   **Permission** \(access and usage policies\): Specifies what a consumer is allowed to do, often under certain conditions.

-   **Prohibition** \(usage policies only\): Defines what a consumer is not allowed to do, for example, use data within a specific region.

-   **Obligation** \(usage policies only\): Defines what a consumer must do, for example, provide data by a certain end date.




<a name="loio91458cfbeba44478bce2e5aaec7b5801__steps_vzx_3bf_2yb"/>

## Procedure

1.  Go to *Design* \> *Data Spaces* \> *Policies* and choose *Create*.

2.  In the *Overview* section, enter the following details:

    -   *Name*
    -   *ID* \(optional\)
    -   *Type*: `Access` or `Usage`
    -   *Description* \(optional\)

3.  In the *Rules* section, choose *Add* to create a new rule. Rules define the policy.

    If you're creating an **access policy**, add the following parameters to define your rules. You can only define rules as **permissions**.

    **Rule Parameters for Access Policies**


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
    
    *Attribute*
    
    </td>
    <td valign="top">
    
    Select one of the following attributes to define your permission:

    -   *Business Partner Number*
    -   *Business Partner Group*
    -   *Membership*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Operator*
    
    </td>
    <td valign="top">
    
    Define an operator that specifies the relationship between attribute and value.

    Select one of the following operators:

    -   *is*: Include a specific value \(applicable for all attributes\)

        If you choose this option, your value cannot be a list. Choose this option to create a 1:1 relationship between *Attribute* and *Value*.

        > ### Example:  
        > `Business Partner Number is BPN0000123`

    -   *is any of*: Include one or more values of a list \(applicable for *Business Partner Number* and *Business Partner Group*\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Value*
    
    </td>
    <td valign="top">
    
    Define the value that your attribute should correspond to.

    For some attributes, the value is already entered and cannot be changed. For example, the value for *Membership* is always `active`.
    
    </td>
    </tr>
    </table>
    
    If you're creating a **usage policy**, add the following parameters to define your rules. You can define rules as **permissions**, **prohibitions**, or **obligations**.

    **Rule Parameters for Usage Policies**


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
    
    *Attribute*
    
    </td>
    <td valign="top">
    
    For **Permissions**, select one of the following attributes to define your rule:

    -   *Affiliates BPNL*
    -   *Affiliates Region*
    -   *Contract Reference*
    -   *Data Frequency*
    -   *Data Usage End Date*
    -   *Data Usage End Definition*
    -   *Data Usage End Duration Days*
    -   *Exclusive Usage*
    -   *Framework Agreement*
    -   *Jurisdiction Location*
    -   *Jurisdiction Location Reference*
    -   *Liability*
    -   *Membership*
    -   *Precedence*
    -   *Usage Purpose*
    -   *Version Changes*
    -   *Warranty*
    -   *Warranty Definition*
    -   *Warranty Duration Months*

    For **Prohibitions**, select one of the following attributes to define your rule:

    -   *Affiliates BPNL*
    -   *Affiliates Region*
    -   *Usage Restriction*

    For **Obligations**, select one of the following attributes to define your rule:

    -   *Data Provisioning End Date*
    -   *Data Provisioning End Duration Days*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Operator*
    
    </td>
    <td valign="top">
    
    Define an operator that specifies the relationship between attribute and value.

    Select one of the following operators:

    -   *is*: Include a specific value \(applicable for all attributes\)

        If you choose this option, your value cannot be a list. Choose this option to create a 1:1 relationship between *Attribute* and *Value*.

        > ### Example:  
        > `Business Partner Number is BPN0000123`

    -   *is all of*: Include all values of a list \(applicable for *Usage Purpose* and *Contract Reference*\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Value*
    
    </td>
    <td valign="top">
    
    Define the value that your attribute should correspond to.

    For some attributes, the value is already entered and cannot be changed. For example, the value for *Membership* is always `active`.
    
    </td>
    </tr>
    </table>
    
    Add as many rules as you need to define your policy.

4.  *Save* your changes. Your new policy appears in the list of policies.




<a name="loio91458cfbeba44478bce2e5aaec7b5801__postreq_h51_nd1_42c"/>

## Next Steps

Now that you've created policies, you can assign them to a contract definition to define the conditions under which business partners can use one of your assets. See [Working with Contract Definitions](working-with-contract-definitions-f136d72.md).

