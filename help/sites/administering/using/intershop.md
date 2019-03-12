---
title: Intershop
seo-title: Intershop
description: Learn how to use AEM with Intershop.
seo-description: Learn how to use AEM with Intershop.
uuid: a06520ce-e758-4ca4-adb8-30513118a041
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: 66d0d4bd-4e56-4cea-a155-1fc41c748af8
pagetitle: Administering Intershop
index: y
internal: n
snippet: y
---

# Intershop{#intershop}

>[!NOTE]
>
>This document applies to both Intershop 7.4 and Intershop 7.4 CI (Continuous Integration).

## Catalog Importer {#catalog-importer}

There are a variety of ways to import product and catalog data. The product and catalog data can be imported when initially setting up the environment, or after changes have been made in the Intershop data.

The importer supports the following modes:

* [Full Import](#full-import)
* [Incremental Import](#incremental-import)
* [Express Update](#express-update)

The product data is maintained in Intershop 7 software and made available through AEM.

The actual product information imported from Intershop or any other source is held in the CRX repository under:

`/etc/commerce/products`

The following properties indicate that the products are linked with Intershop:

* `commerceProvider`
* `cq:intershopCatalogId`
* `cq:intershopId`

>[!NOTE]
>
>The Intershop implementation (for example `geometrixx-outdoors/en_US`) only stores product IDs and other basic information under `/etc/commerce`.
>
>The Intershop server is referenced every time information about a product is requested.

### Full Import {#full-import}

If required, before the actual import, delete all existing product data using CRXDE Lite:

1. In CRXDE Lite, navigate to the sub-tree holding the product data:  
   `/etc/commerce/products`
1. Delete the node that holds your product data; for example, `outdoors`.
1. Click **Save All** to persist the change.

To do the full import:

1. Open the Intershop importer in AEM:

   `/etc/importers/intershop.html`

1. Configure the parameters as required; for example:

   ![](assets/chlimage_1-30.jpeg)

1. Click **Import Catalog** to start the import.

   When complete, you can verify the data imported at:  
   [http://localhost:4502/crx/de/index.jsp#/etc/commerce/products](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)

### Incremental Import {#incremental-import}

1. Check the information held in AEM for the relevant product(s), in the appropriate sub-tree under:

   `/etc/commerce/products`

1. In Intershop, update the information held on the relevant product(s).
1. Open the Intershop importer in AEM:

   `/etc/importers/intershop.html`

1. Select the checkbox **Incremental Import**.
1. Click **Import Catalog** to start the import.

   When complete, you can verify the data imported at:  
   [http://localhost:4502/crx/de/index.jsp#/etc/commerce/products](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)

### Express Update {#express-update}

The import process can take a long time so you can select specific areas of the catalog for an express update that is triggered manually. This uses the export feed together with the standard attributes configuration:

1. Check the information held in AEM for the relevant product(s), in the appropriate sub-tree under:

   `/etc/commerce/products`

1. Log on to the Intershop 7 Commerce Management application.
1. Navigate to to the desired product.
1. Click the lock icon on top of the page to lock the product for editing.
1. On the **General** tab mark the checkbox **Express Update**.
1. Click **Apply** and click the lock icon on top of the page again to unlock the product.

   ![](assets/chlimage_1-104.png)

1. Open the Intershop importer in AEM:

   `/etc/importers/intershop.html`

1. Select the checkbox **Express Update**.
1. Click **Import Catalog** to start the import.

   When complete, you can verify the data imported at:  
   [http://localhost:4502/crx/de/index.jsp#/etc/commerce/products](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)

## Configure the Catalog Importer {#configure-the-catalog-importer}

The Intershop catalog can be imported into AEM, using the batch importer for Intershop catalogs, categories and products.

The parameters used by the importer can be configured for:

**Intershop Product and Catalog Importer** 
( `com.adobe.cq.commerce.intershop.impl.importer.IntershopImporter`)

![](assets/chlimage_1-105.png)

>[!NOTE]
>
>When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../../sites/deploying/using/configuring-osgi.md) for full details. Also see the console for a full list of configurable parameters and their defaults.

## Configure the Product Attributes to Load {#configure-the-product-attributes-to-load}

The response parser can be configured to define the properties and attributes to be loaded for (variant) products.

The parameters used by the parser can be configured for:

**Intershop JSON Parser** 
( `com.adobe.cq.commerce.intershop.impl.importer.IntershopJSONParser`)

![](assets/chlimage_1-106.png)

>[!NOTE]
>
>When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../../sites/deploying/using/configuring-osgi.md) for full details. Also see the console for a full list of configurable parameters and their defaults.

