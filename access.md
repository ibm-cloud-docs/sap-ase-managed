---
copyright:
  years: 2024
lastupdated: "2024-07-12"

subcollection: sap-ase-managed
---

{{site.data.keyword.attribute-definition-list}}

# Managing Users, Roles, and Privileges
{: #access}

Access to SAP ASE Cloud Edition on IBM Cloud instances for users is controlled by the Cloud Identity and Access Management (IAM).
{: shortdesc}

Every user that accesses the `SAP ASE Cloud Edition on IBM Cloud` service in your account must be assigned an access policy with an IAM role. Review the following roles, actions, and more to help determine the best way to assign access to `SAP ASE Cloud Edition on IBM Cloud`.

The access policy that you assign users in your account determines what actions a user can perform within the context of the service or specific instance that you select. The allowable actions are customized and defined by the `SAP ASE Cloud Edition on IBM Cloud` service as operations that you are allowed to perform on the service. Each action is mapped to an IAM platform or service role that you can assign to a user.

If a specific role and its actions don't fit the use case that you're looking to address, you can [create a custom role](/docs/account?topic=account-custom-roles&interface=ui#custom-access-roles) and pick the actions to include.
{: tip}

IAM access policies enable access to grant at different levels. The following are some options that are included:

- Access across all instances of the service in your account
- Access to an individual service instance in your account
- Access to a specific resource within an instance

Review the following tables that outline what types of tasks each role allows when you're working with `SAP ASE Cloud Edition on IBM Cloud`. Platform management roles enable users to perform tasks on service resources at the platform level. For example, assign user access to the service and create or delete instances. Service access roles enable user access to `SAP ASE Cloud Edition on IBM Cloud`.

| Platform role | Description of actions                                                                                                                |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Viewer        | You can view service instances, but you can't modify them.                                                                            |
| Operator      | You can perform platform actions that are required to configure and operate service instances, such as viewing a service dashboard.   |
| Editor        | You can perform all platform actions except for managing the account and assigning access policies.                                   |
| Administrator | You can perform all platform actions based on the resource this role is assigned, including assigning access policies to other users. |
{: row-headers}
{: class="simple-tab-table"}
{: caption="Table 2. IAM SAP ASE Cloud Edition on IBM Cloud Platform Roles" caption-side="bottom"}
{: #iamrolesplatformsapaseceonibmcloud}
{: tab-title="SAP ASE Cloud Edition on IBM Cloud Platform roles"}
{: tab-group="IAMSAPASECE"}

| Service role | Description of actions                                                                                                                                                                  |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Reader       | You can perform read-only actions within a service, such as viewing service-specific resources.                                                                                         |
| Writer       | You have permissions beyond the reader role, including creating and editing service-specific resources.                                                                                 |
| Manager      | You have permissions beyond the writer role that allows you to complete privileged actions, as defined by the service. In addition, you can create and edit service-specific resources. |
{: row-headers}
{: class="simple-tab-table"}
{: caption="Table 2. SAP ASE Cloud Edition on IBM Cloud Service Access Roles" caption-side="bottom"}
{: #iamrolesplatformsapaseceonibmcloud}
{: tab-title="SAP ASE Cloud Edition on IBM Cloud Service roles"}
{: tab-group="IAMSAPASECE"}
