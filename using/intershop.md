---
title: Intershop
seo-title: Intershop
description: null
seo-description: Learn how to deploy eCommerce with Intershop.
uuid: 5ec7ebfa-f8fa-4768-865e-835ca788d4fb
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/intershop
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 22.359-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 43 47.848-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 217e65a4-9575-4ede-912a-30204b496f27
disttype: dist5
firstPublishExternalDate: 2017-10-31T16:17:55.972-0400
gnavtheme: light
isreadyforlocalization: false
jcr-created: 2017-12-01T19 02 32.627-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:43:46.935-0400
lochandoffdate: 2018-04-30T03 27 22.358-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Intershop
pagetitle: Deploying eCommerce with Intershop
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 43 46.935-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/intershop.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/ecommerce/intershop
sha1: 2ab857ed4f15a3b095c10ba7c48718b675bbc41c
topicBrowsingSortDate: 2018-04-03T08:43:46.935-0400
index: y
internal: n
snippet: y
translate: y
---

# Intershop

>[!NOTE]
>
><p>This page contains links to the&nbsp;<a href="http://www.intershop.com/">Intershop website</a>. Certain areas need an account for full access.</p>

---

## Deploying eCommerce with Intershop

Deploying the necessary eCommerce packages provides the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with Intershop implementation (including a demonstration catalog).

This catalog is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site.

### Technical Requirements

This document applies to both Intershop 7.4 and Intershop 7.4 CI (Continuous Integration).

### Setup Geometrixx in Intershop 7

This procedure will initialize the Intershop system with a Geometrixx organization to work with the AEM reference implementation.

>[!CAUTION]
>
><p>The three following Intershop 7 cartridges must have been successfully deployed on the Intershop instance:</p> <ul> <li><span class="code">adobe_app_sf_rest</span></li> <li><span class="code">adobe_app_bo_ch_sales</span></li> <li><span class="code">adobe_init</span></li> </ul>

A database initialization needs to be performed on `adobe_init`. To do that:

1. Add the cartridge to the `dbinit` section of the `cartridgelist.properties`.

1. Open an ANT build shell.

1. Type:

   ```shell
   dbinit -t=adobe_init -!
   ```

1. Login to the new Geometrixx organization:

    * **Login**: `admin`    
    * **Password**: `intershop7`    
    * **Organization**: `Geometrixx`

>[!NOTE]
>
><p>See the <a href="https://support.intershop.com/kb/index.php">Intershop Knowledge Base</a> for more information.</p>

### Installation of eCommerce with Intershop

To install AEM with an Intershop integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](deploy.md).

1. Install the demonstration content packages using the [Package Manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager).

   >[!NOTE]
   >
   ><p>Packages are available on demand. To be able to find and download them, please&nbsp;<a href="http://www.intershop.com/contact">contact Intershop</a>.</p> 

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

Configure the Intershop REST Client:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Open `Intershop REST Client`.

1. Update the properties to point to the Intershop instance.
   ![](assets/chlimage_1.png)

>[!CAUTION]
>
><p>Use of the Intershop server requires a separate Intershop license.</p> 
