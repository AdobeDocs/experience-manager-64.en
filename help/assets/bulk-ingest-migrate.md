---
title: Installing Feature Pack 18912 for bulk asset migration
seo-title: Installing Feature Pack 18912 for bulk asset migration
description: Feature pack 18912 lets you either bulk ingest assets by way of FTP, or migrate assets from Dynamic Media Classic to Dynamic Media in AEM. This optional feature pack is available from Adobe support.
seo-description: Feature pack 18912 lets you either bulk ingest assets by way of FTP, or migrate assets from Dynamic Media Classic to Dynamic Media in AEM. This optional feature pack is available from Adobe support.
uuid: 316d77e3-3d61-4cf0-8955-726ee54e268c
contentOwner: rbrough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 6198e613-a867-49a8-b9a5-a05e7889821c
---

# Installing feature pack 18912 for bulk asset migration{#installing-feature-pack}

The installation of feature pack 18912 is _optional_. Feature Pack 18912 lets you either bulk ingest assets by way of FTP, or migrate assets from Dynamic Media Classic to Dynamic Media on AEM. The optional feature pack is available from Adobe support.

>[!NOTE]
>
>Migration feature packs, such as this one, are only supported as part of a migration project through Adobe Pro Services.

When installing this feature pack, you must also create a service user and provide that information to Adobe support.

See also [Configuring Dynamic Media - Scene7 mode](https://helpx.adobe.com/experience-manager/6-4/assets/using/config-dms7.html).

**To install feature pack 18912 for bulk asset migration**,

1. In your AEM instance, navigate to **Tools** &gt; **Security** &gt; **Users** and select **Create User**. This service user must have **read/write** permissions to /**content/dam**.
1. In the **ID** and **Password** fields, enter a user name and password; for example, **FTP User**. This name appears in the timeline as the user who created the asset. When an asset is uploaded from FTP, an asset is considered created when it is uploaded to the FTP server and is pushed to AEM.
1. Contact Adobe support by filing a customer support ticket to access feature pack 18912 for downloading. In the customer support ticket, provide the following information:

    * Server IP address for the author instance, including the port number (by default, the port number is 4502.) 
    * AEM service user username/password from the previous step

1. When you receive feature pack 18912 from Adobe support, install it.

   See [How to Work with Packages](/help/sites-administering/package-manager.md) for more information on using Package Share and packages in AEM.

