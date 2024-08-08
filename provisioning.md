---
copyright:
  years: 2024
lastupdated: "2024-07-12"

subcollection: sap-ase-managed
---

{{site.data.keyword.attribute-definition-list}}

# Provisioning
{: #provisioning}

Provision SAP Adaptive Server Enterprise Cloud Edition by IBM Cloud through the [catalog](https://test.cloud.ibm.com/catalog/services/sap-adaptive-server-enterprise-cloud-edition-by-ibm-cloud).
{: shortdesc}

## Provisoning through the IBM Cloud Catalog
{: #provisioning-through-ibm-cloud-catalog}

Provision from the console by specifying the following parameters:

### Plan selection
{: #plan-selection}

SAP Adaptive Server Enterprise Cloud Edition by IBM Cloud offers two plans:

- **Multi-zone (HA)**: The instance includes one Business Critical Base Environment deployed across two zones in a single region for High Availability, as well as the default backup service configured to take 7 daily full backups, 5 weekly full backups, and 3 month retention.
- **Single zone (Non-HA)**: The instance includes one Business Non-Critical Base Environment deployed in a single zone. No backup service is configured and cannot be added.

While not included in the initial deployment, at least one SAP ASE instance is need to utilize this service. Post creation, SAP ASE instances can be added to the service.
{: tip}

### Resource configuration
{: #resource-configuration}

- **Service name**: The name can be any string and is the name that is used to identify the new deployment.
- **Resource group**: If you are organizing your services into [resource groups](https://cloud.ibm.com/docs/account?topic=account-account_setup), specify the resource group in this field. Otherwise, you can leave it as Default. For more information, see [Managing resource groups](https://cloud.ibm.com/docs/account?topic=account-rgs).
- **Lead Client Name**: The full name of the lead client.
- **Lead Client Email**: The email address of the lead client where they can be contacted.
- **SAP Customer ID**: The ID of the SAP Customer.
- **SAP Tenant ID**: The ID of the SAP Tenant.
- **Primary Contact Notification List**: A comma or semicolon separated list of emails addresses that should be notified first of events.
- **Additional Comments**: Provide any additional details or comments you would like shared with the provisioning team.
- **Add-ons**: Services that can be provided upon request along with the deployment. These services include: Management VPC with Bastion Host, and Direct Link including Management.

After you select the appropriate settings, click **Create** to start the provisoning process.

## Configuring the instance post-provisioning
{: #configuring-the-instance-post-provisioning}

Depending on the plan selected, further options can be applied to the instance created.

| Options                                        | Multi-zone (HA)                     | Single zone (Non-HA) |
| ---------------------------------------------- | ----------------------------------- | -------------------- |
| Additional Base Environments                   | Critical and Non-Critical           | Only Non-Critical    |
| XS-XXL SAP ASE Instances                       | Critical and Non-Critical           | Only Non-Critical    |
| Application Patching (at least 2 times a year) | Yes                                 | Yes                  |
| Management VPC with Bastion                    | Yes                                 | Yes                  |
| Direct Link including Management               | Yes                                 | Yes                  |
| Ad-hoc Work (half day)                         | Yes                                 | Yes                  |
| Additional 3 IOPs Storage (in 100GB intervals) | Yes, with or without COS for backup | Yes                  |
{: caption="Table 1. Post-Provisioning Options" caption-side="bottom"}

### SAP ASE Instance Size Options
{: #sap-ase-instance-sizing-options}

SAP ASE Instances come in a range of sizes. Refer to the table to determine the best size for your instance.

| Size      | Compute (vCPU) | Memory (GB RAM) | Storage | Total Block Storage (3 IOPs GB) | Total COS |
| --------- | -------------- | --------------- | ------- | ------------------------------- | --------- |
| X-Small   | 2              | 8               | 256     | 512                             | 2150      |
| Small     | 4              | 32              | 512     | 1024                            | 4301      |
| Medium    | 8              | 64              | 1024    | 2048                            | 8602      |
| Large     | 16             | 128             | 1536    | 3072                            | 12902     |
| X-Large   | 32             | 256             | 2048    | 4096                            | 17203     |
| XX-Large  | 64             | 512             | 3072    | 6144                            | 25805     |
| XXX-Large | 128            | 1024            | 5120    | 10240                           | 43008     |
{: caption="Table 2. SAP ASE Instance Size Options" caption-side="bottom"}

### Advanced Configuration
{: #advanced-configuration}

#### Backups
{: #backups}

The default backup service includes

| Backup                                         | Default Retention |
| ---------------------------------------------- | ----------------- |
| Daily full backup (database, transaction logs) | Last 7 days       |
| Weekly full backup                             | Last 5 weeks      |
| Monthly full backup                            | Last 3 months     |
{: caption="Table 3. Default Backup Service" caption-side="bottom"}

Additional retention periods can be requested for each backup at an additional cost.
