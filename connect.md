---
copyright:
  years: 2024
lastupdated: "2024-07-12"

subcollection: sap-ase-managed
---

{{site.data.keyword.attribute-definition-list}}

# Connecting to the Cloud ASE Portal
{: #connect}

The Cloud ASE Portal provides customers with the ability to

- upload and manage database encryption keys
- restart ASE database servers
- execute ad-hoc back-ups and restores
- drop databases

VPN access and initial credentials must be retrieved in order to connect to the Cloud ASE Portal.

Be sure to accept the invitation to the IBM Cloud account. An IBMid is required to succesfully connect.

## Securely Connect to the Cloud ASE Portal
{: #securely-connect-to-the-cloud-ase-portal}

The Cloud ASE Portal is deployed on a private network. To access the portal, VPN access must be configured.

1. Login to IBM Cloud
2. Go to the Resource List and launch the Secrets Manager instance.
3. Select "View Secret" for the `$PREFIX-vpc-client-profile` under the 
`$PREFIX-cloud-ase-portal-logins` secret group.
4. Download the Client Profile.
5. Unzip the downloaded Client Profile and locate the OVPN file.
6. Install and open [OpenVPN](https://openvpn.net/) connect.
7. Add a Profile and upload the OVPN file.
8. Specify your IBM Cloud username in the username field.
9. Click "Connect"
10. When prompted to "Enter password", retrieve [a one time password from IBM Cloud](https://iam.cloud.ibm.com/identity/passcode). If prompted to login, enter your IBM Cloud email and password. 
11. Upon successful login, the toggle will be enabled next to the configured profile.
12. Verify connection to the private network by navigating to the Cloud ASE Portal in the desired internet browser.

## Login to the Cloud ASE Portal 
{: #login-to-the-cloud-ase-portal}

1. Login to IBM Cloud.
2. Go to the Resource List and launch the Secrets Manager instance.
3. Select "View Secret" for the `$PREFIX-dba-initial-login` secret under the `$PREFIX-cloud-ase-portal-logins` secret group.
4. Confirm you are in a safe environment and copy the secret value.
5. Launch [OpenVPN](https://openvpn.net/) and connect to the Profile previously configured by enabling the toggle.
6. Navigate to the Cloud ASE Portal.
7. Login with the invited email and initial password from Secets Manager.

It is strongly recommended that the initial password be updated. To update, click "Forgot Password" on the portal's Login page.
{: tip}

## Manage Cloud ASE Portal Users
{: #manage-users}

The Self Service Portal is integrated with [IBM Cloud App ID](https://www.ibm.com/products/app-id). With Cloud Directory, you can manage your users in a scalable registry by using pre-built functionality that enhances security and self-service. See the IBM Cloud App ID documentation for [Managing users](https://cloud.ibm.com/docs/appid?topic=appid-cd-users) in Cloud Directory.
