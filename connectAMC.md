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
{: #retrieve-secrets}

1. Login to IBM Cloud.
2. Go to the Resource List and launch the Secrets Manager instance.
3. Filter by secret group: `<% base environment prefix %>-ase-user-secrets`
4. Locate the ASE user login credentials (`<% base environment prefix %>-<% ase instance prefix %>-user-login`). Select "View secret", confirm you are in a safe environment, and copy the username and password to a secure location.   
5. Locate and download the AMC private certificate (`<% ase instance prefix %>-amc-private-cert`).

## Add the private certificate to your keychain
{: #add-private-cert-to-keychain}

1. Open and unzip the AMC private certificate file from Secrets Manager.
2. Click on your certificate's .pem file.
3. When prompted, enter your Macbook password to allow for Keychain access.
4. On success, the certificate will be added to your keychain.
5. Once added, find the `*.inrernal.com` certificate in your keychain and click on it to open the details.
6. Expand the "Trust" section, and in the dropdown next to "When using this certificate", select "Always trust".
7. If prompted, enter your Macbook password to update the settings for the certificate.

## Connect to AMC
{: #connect-amc-lb}

1. Login to IBM Cloud.
2. Expand the hamburger icon in the top left corner.
3. Select Infrastructure > Network > Load Balancers.
4. Select the region.
5. Copy the hostname for either the primary or the companion load balancer: `<% base environment prefix %>-<% primary | companion %>-amc-lb-b`.
6. Launch OpenVPN connect and connect to the VPN.
7. When prompted to "Enter password", retrieve [a temporary one time passcode from IBM Cloud](https://iam.cloud.ibm.com/identity/passcode). If prompted to login, enter your IBM Cloud email and password.
8. Open a new internet browser window or tab.
9. Paste the AMC load balancer hostname into the address bar, following the format `https://<% amc load balancer hostname %>:8443`.
10. On the AMC login page, enter the ASE user login credentials.
