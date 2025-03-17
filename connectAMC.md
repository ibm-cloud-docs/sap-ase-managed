---
copyright:
  years: 2024
lastupdated: "2024-07-12"

subcollection: sap-ase-managed
---

{{site.data.keyword.attribute-definition-list}}

# Connecting to AMC
{: #connect-amc}

The Administration and Management Console (AMC) for SAP ASE is a web based tool for managing and administering your SAP ASE servers.

These instructions assume that you are using a Mac-based system.
{: tip}

## Retrieve values from Secrets Manager

1. Login to IBM Cloud.
2. Go to the Resource List and launch the Secrets Manager instance.
3. Filter by secret group: `<% base environment prefix %>-ase-user-secrets`
4. Retrieve the ASE password. Select "View Secret" for the `<% base environment prefix %>-<% ase instance prefix %>-user-login`
5. Retrieve the AMC private certificate. Select "View Secret" for the `<% ase instance prefix %>-amc-private-cert`

## Add the private certificate to your keychain

1. Open the AMC private certificate file from Secrets Manager.
2. Click on your certificate's .pem file.
3. Enter the ASE password retrieved from Secrets Manager when prompted.
4. On success, the certificate will be added to your keychain.
5. Once added, find your certificate in your keychain and click on it to open the details.
6. Expand the "Trust" section, and in the dropdown next to "When using this certificate", select "Always trust".

## Connect to AMC

1. Login to IBM Cloud.
2. Expand the hamburger icon in the top left corner.
3. Select Infrastructure > Network > Load Balancers.
4. Select the region.
5. Copy the hostname for either the primary or the companion load balancer: `<% base environment prefix %>-<% primary | companion %>-amc-lb-b`.
6. Launch OpenVPN connect and connect to the VPN.
7. When prompted to "Enter password", retrieve [a temporary one time passcode from IBM Cloud](https://iam.cloud.ibm.com/identity/passcode). If prompted to login, enter your IBM Cloud email and password.
8. Open a new internet browser window or tab.
9. Paste the AMC load balancer hostname into the address bar and append the AMC port (:8443) to the end.
