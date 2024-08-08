---
copyright:
  years: 2024
lastupdated: "2024-07-12"

subcollection: sap-ase-managed
---

{{site.data.keyword.attribute-definition-list}}

# Securely Connecting to the SAP ASE Self Service Portal
{: #connect}

VPN access and initial credentials must be retrieved in order to connect to the SAP ASE Self Service Portal.

Be sure to accept the invitation to the IBM Cloud account.

## Connect to the Self Service Portal
{: #connect-to-the-self-service-portal}

The Self Service Portal is deployed on a private network. To access the portal, VPN access must be configured. As part of the Base Environment, a Client to Site VPN is created for the Self Service Portal.

1. Login to IBM Cloud
2. Go to the Resource List and launch the Secrets Manager instance.
3. Select "View Secret" for the "vpc-client-profile" under the "sap-ase-ssp-portal" secret group.
4. Download the Client Profile.
5. Unzip the downloaded Client Profile and locate the OVPN file.
6. Install and open [OpenVPN](https://openvpn.net/) connect.
7. Add a Profile and upload the OVPN file.
8. Use the toggle to connect to the OpenVPN Profile for the Self Service Portal.
9. Verify connection to the private network by navigating to the Self Service Portal in the desired internet browser.

## Login to the Self Service Portal
{: #login-to-the-self-service-portal}

1. Login to IBM Cloud.
2. Go to the Resource List and launch the Secrets Manager instance.
3. Select "View Secret" for the "initial-login" secret under the "sap-ase-ssp-portal" secret group.
4. Confirm you are in a safe environment and copy the secret value.
5. Launch [OpenVPN](https://openvpn.net/) and select the Profile previously created.
6. Navigate to the Self Service Portal.
7. Login with the invited email and initial password from Secets Manager.

It is strongly recommended that the initial password be updated. To update, click "Forgot Password" on the portal's Login page.
{: tip}

## Manage Self Service Portal Users
{: #manage-users}

The Self Service Portal is integrated with [IBM Cloud App ID](https://www.ibm.com/products/app-id). With Cloud Directory, you can manage your users in a scalable registry by using pre-built functionality that enhances security and self-service. See the IBM Cloud App ID documentation for [Managing users](https://cloud.ibm.com/docs/appid?topic=appid-cd-users) in Cloud Directory.
