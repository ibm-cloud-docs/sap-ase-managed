---
copyright:
  years: 2024
lastupdated: "2024-07-12"

subcollection: sap-ase-managed
---

{{site.data.keyword.attribute-definition-list}}

# Overview

{: #overview}

SAP Adaptive Server Enterprise, Cloud Edition by IBM is the SAP ASE data server hosted and managed by IBM Cloud.

IBM Cloud for SAP provides your enterprise with full cloud capabilities. Running SAP ASE on IBM Cloud enables you to quickly move your workloads from an on-premises server to the cloud, taking advantage of its lower cost of ownership and enterprise-level services, and faster deployment time. Once you are running on IBM Cloud, you pay only for the server time used, reducing the amount of hardware that remains idle because it is unnecessary. The start-up costs of running on IBM Cloud are also much lower than purchasing and maintaining your own hardware.

With a few exceptions, an SAP ASE running on IBM Cloud has the same functionality as an on-premises version, and you perform the same administrative tasks. Clients connect to the SAP ASE running on IBM Cloud in the same way as they connect to an on-premises SAP ASE.

## Key Features

### Network Architecture

The SAP ASE service utilizes a three-tiered network architecture.

- **Customer Edge VPC** – VPC in customer’s cloud environment that groups IBM Cloud resources needed for on-premise integration, bastion hosts (jump servers), VPN servers, gateways, and public gateways. All inbound and outbound traffic to and from IBM Cloud passes through this VPC.
- **Customer Management VPC** – VPC in customer’s cloud environment that groups IBM Cloud resources needed to manage SAP ASE, included tools such as Administration & Management Console (AMC), and potentially any other customer-specific tools for managing their SAP ASE instances (optional).
- **Customer Workload VPC** – VPC in customer’s cloud environment that groups IBM Cloud resources for SAP ASE instances. This is where customer databases are hosted.

### Security

All access to SAP ASE cloud edition instances is via secure connections on SQL ports and the data is always stored encrypted using SAP ASE full database encryption. All storage and network communication in the environment is encrypted.

In order to provide a clean separation of duties, the SAP ASE security model has been modified in order to allow the managed service provider (MSP) to operate the SAP ASE server and perform regular activities like backups and patching whilst protecting customer data. The MSP team has no access to customer schemas and customer data. The SAP ASE cloud edition prevents DBA users from having SU control over any ASE instance.

### Backup and Restore

The SAP ASE cloud edition provides automatic backups to your databases for the integrity of your database system. In production environments, daily full database backups are created and stored for 30 days. You can also request adhoc backups and adhoc restores through the self-service. Unless a custom backup strategy is defined, transaction logs are backed up every 30 minutes and stored for 30 days by default.s

### Self Service Portal

The SAP ASE Customer Self Service Portal provides customers with the ability to

- upload and manage database encryption keys
- restart ASE database servers
- execute ad-hoc back-ups and restores
- drop databases
