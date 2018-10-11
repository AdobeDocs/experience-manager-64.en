---
title: Intershop
seo-title: Intershop
description: null
seo-description: Learn how to deploy eCommerce with Intershop.
uuid: 42fb86c6-8ff9-4b5f-98a4-f74ebad2a1c1
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
discoiquuid: 7fb4bd55-c89c-4884-83c9-fafa69bd8ad6
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
publishexternaldate: 2018-04-03T08 43 46.935-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/intershop.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/ecommerce/intershop
sha1: a5a15e648494c04f01b71b03c042ac60dabd0205
topicBrowsingSortDate: 2018-04-03T08:43:46.935-0400
index: y
internal: n
snippet: y
translate: y
---

# Intershop

>[!NOTE]
>
>This page contains links to the [Intershop website](http://www.intershop.com/). Certain areas need an account for full access.

## Deploying eCommerce with Intershop
Deploying the necessary eCommerce packages provides the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with Intershop implementation (including a demonstration catalog).

This catalog is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site.

### Technical Requirements
This document applies to both Intershop 7.4 and Intershop 7.4 CI (Continuous Integration).

### Setup Geometrixx in Intershop 7
This procedure will initialize the Intershop system with a Geometrixx organization to work with the AEM reference implementation.

>[!CAUTION]
>
>The three following Intershop 7 cartridges must have been successfully deployed on the Intershop instance:
>
>* `adobe_app_sf_rest`
>* `adobe_app_bo_ch_sales`
>* `adobe_init`
>

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
>See the [Intershop Knowledge Base](https://support.intershop.com/kb/index.php) for more information.

### Installation of eCommerce with Intershop
To install AEM with an Intershop integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](deploy.md).
1. Install the demonstration content packages using the [Package Manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager).

   >[!NOTE]
   >
   >Packages are available on demand. To be able to find and download them, please [contact Intershop](http://www.intershop.com/contact).

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

Configure the Intershop REST Client:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Open `Intershop REST Client`.
1. Update the properties to point to the Intershop instance.

   ![](assets/intershop/chlimage_1.png)

>[!CAUTION]
>
>Use of the Intershop server requires a separate Intershop license.

