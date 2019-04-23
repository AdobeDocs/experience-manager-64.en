---
title: Intershop
seo-title: Intershop
description: Learn how to deploy eCommerce with Intershop.
seo-description: Learn how to deploy eCommerce with Intershop.
uuid: 6c1b0707-1928-48b8-8be6-03979b3c1ae9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: aea57da5-92d0-4c3f-a56b-0e853a403f23
pagetitle: Deploying eCommerce with Intershop
---

# Intershop{#intershop}

>[!NOTE]
>
>This page contains links to the [Intershop website](https://www.intershop.com/). Certain areas need an account for full access.

## Deploying eCommerce with Intershop {#deploying-ecommerce-with-intershop}

Deploying the necessary eCommerce packages provides the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with Intershop implementation (including a demonstration catalog).

This catalog is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site.

### Technical Requirements {#technical-requirements}

This document applies to both Intershop 7.4 and Intershop 7.4 CI (Continuous Integration).

### Setup Geometrixx in Intershop 7 {#setup-geometrixx-in-intershop}

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

### Installation of eCommerce with Intershop {#installation-of-ecommerce-with-intershop}

To install AEM with an Intershop integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](/help/sites-deploying/deploy.md).
1. Install the demonstration content packages using the [Package Manager](/help/sites-administering/package-manager.md).

   >[!NOTE]
   >
   >Packages are available on demand. To be able to find and download them, please [contact Intershop](https://www.intershop.com/contact).

1. [Author](/help/sites-authoring/page-authoring.md) any supplementary pages that you need in AEM.

Configure the Intershop REST Client:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Open `Intershop REST Client`.
1. Update the properties to point to the Intershop instance.

   ![](assets/chlimage_1-143.png)

>[!CAUTION]
>
>Use of the Intershop server requires a separate Intershop license.

