---
title: Installing Feature Pack 18912
seo-title: Installing Feature Pack 18912
description: Feature Pack 18912 lets you bulk ingest assets by way of FTP, or migrate assets from Dynamic Media Classic (Scene7), or both. This optional feature pack is available from Adobe support.
seo-description: Feature Pack 18912 lets you bulk ingest assets by way of FTP, or migrate assets from Dynamic Media Classic (Scene7), or both. This optional feature pack is available from Adobe support.
uuid: b9be43c9-f6ae-4d9b-90e1-9f698ff80e88
contentOwner: rbrough
discoiquuid: 327587b3-4e56-4cca-909e-3878092021ea
index: y
internal: n
snippet: y
---

# Installing Feature Pack 18912{#installing-feature-pack}

The installation of Feature Pack 18912 is optional. Feature Pack 18912 lets you bulk ingest assets by way of FTP, or migrate assets from Dynamic Media Classic (Scene7), or both. The optional feature pack is available from Adobe support.

When installing this feature pack, you must also create a service user and provide that information to Adobe support.

See also [Configuring Dynamic Media - Scene7 mode](/assets/using/config-dynamic-fp-14410).

**To install feature pack 18912**,

1. In your AEM instance, navigate to **Tools** &gt; **Security** &gt; **Users** and select **Create User**. This service user must have **read/write** permissions to /**content/dam**.
1. In the **ID** and **Password** fields, enter a user name and password; for example, **FTP User**. This name appears in the timeline as the user who created the asset. When an asset is uploaded from FTP, an asset is considered created when it is uploaded to the FTP server and is pushed to AEM.
1. Contact Adobe support by filing a customer support ticket to access Feature Pack 18912 for downloading. In the customer support ticket, provide the following information:

    * Server IP address for the author instance, including the port number (by default, the port number is 4502.) 
    * AEM service user username/password from the previous step

1. When you receive Feature Pack 18912 from Adobe support, install it.

   See [How to Work with Packages](../../sites/administering/using/package-manager.md) for more information on using Package Share and packages in AEM.

