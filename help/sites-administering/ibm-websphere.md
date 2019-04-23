---
title: IBM Websphere Commerce
seo-title: IBM Websphere Commerce
description: Learn how to use AEM with IBM Websphere Commerce.
seo-description: Learn how to use AEM with IBM Websphere Commerce.
uuid: ec36ccf1-a132-4657-b1a1-2b2b919261b9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: fdd84ff0-a7e5-4e3f-910e-e15db0ba50a8
pagetitle: Administering IBM Websphere Commerce
---

# IBM Websphere Commerce{#ibm-websphere-commerce}

>[!NOTE]
>
>This document applies to Websphere Commerce version 7 Feature Pack 8.  
>To run the Geometrixx Outdoors store with WebSphere Commerce, the Geometrixx Outdoors products and catalog data must be loaded into WebSphere Commerce.

The product data is maintained in Websphere Commerce software and made available through AEM.

The actual product information imported is held in the CRX repository under:

`/etc/commerce/products`

## Full Product Import {#full-product-import}

The provided product data is for reference only. It is required to import the product data from your WebSphere Commerce store.

>[!NOTE]
>
>The following steps use `geometrixx-outdoors-wc` as store name for the Geometrixx Outdoors store. You might use a different store name, but that requires updating product base path of the catalogue blueprint before roll-out as an additional step.

Before the actual import, delete all existing product data using CRXDE Lite:

1. In CRXDE Lite, navigate to the sub-tree holding the product data:  
   `/etc/commerce/products`
1. Delete the node that holds your product data; for example, `geometrixx-outdoors-wc`.
1. Click **Save All** to persist the change.

To do the full import:

1. Navigate to the **Products** console, via **Commerce**.
1. Click **Import Products**.
1. Configure the parameters as follows:

    * WebSphere Commerce store ID: set to the STORE_ID from the WC STORE table
    * WebSphere Commerce store name: geometrixx-outdoors-wc
    * WebSphere Commerce master catalog id: set to the CATALOG_ID from the WC CATALOG table

1. Select **Next** to import the products, a log of the actions taken will be shown.
1. Select **Done** to close the wizard.

   When complete, you can verify the data imported at:

    * [http://localhost:4502/crx/de/index.jsp#/etc/commerce/products](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)

   A geometrixx-outdoors-wc should have been added.

To do roll-out the catalog:

1. Navigate to the **Catalogs** console, via **Commerce**.
1. Navigate to the **Base Catalog** in the **Geometrixx Outdoors WC** catalog blueprint folder.
1. Using either:

    * [quick actions](/help/sites-authoring/basic-handling.md#quick-actions)
    * [selection mode](/help/sites-authoring/basic-handling.md)

   Select the **Rollout Changes** icon.

1. In the wizard, set the rollout as needed and then tap/click **Rollout Changes**.
1. A dialog opens. Tap/click **Done **when the process is finished.

## Customize Product Import Attributes {#customize-product-import-attributes}

To change the current configuration:

1. Navigate to:

    * `http://localhost:4502/system/console/configMgr`.

1. Click **Adobe CQ Commerce - IBM WebSphere Commerce product & product variant data parser**.
1. Change the configuration as required.
1. Click **Save**.
1. Do a [full import](#full-product-import).

## Change Product Price {#change-product-price}

Highly volatile attributes (for example price or temporary discount) will not be imported but fetched directly from the eCommerce engine side for every page requested.

To change the price of a product:

1. Check the current price in AEM for the relevant product(s), for example:

    * [http://localhost:4502/content/geometrixx-outdoors/en_US/men/shirts/ashanti-nomad.html](http://localhost:4502/content/geometrixx-outdoors/en_US/men/shirts/ashanti-nomad.html)

1. Log in to IBM Management Center for WebSphere Commerce.
1. Click this symbol to work on approved content:

   ![](do-not-localize/chlimage_1.jpeg)

   The approved content should be displayed in the header.

1. Select **Catalogs** in the **Management Center Tools** menu.
1. Select **GeometrixxOutdoorsESites** as catalog in the left drop down in the menu bar.
1. Expand the left menu tree of the **Geometrixx Outdoors** catalog to find the required product, for example **Mens** and then **Mens Apparel**.
1. Select the required product, for example Ashanti Nomad shirt, open the context menu and select **Show SKUs List**.

   ![](assets/chlimage_1-306.png)

1. Double click the first entry to open the **S** size variant of the shirt.
1. Go to **Manage SKU** tab and scroll down to **Pricing**.
1. Change the offer price.
1. Click **Save and Preview**.

   >[!NOTE]
   >
   >It is important to trigger reindexing which does not happen on save.

1. Check the new price in AEM. In our example, the price for the S size should have changed and the other sizes should have the old price.

## Use Scale Prices for a Product {#use-scale-prices-for-a-product}

To use scale prices for a product, first start by adding a product to the cart:

1. Check the current price in AEM for the relevant product(s), for example:

    * [http://localhost:4502/content/geometrixx-outdoors/en_US/equipment/hiking/longirod-trek.html](http://localhost:4502/content/geometrixx-outdoors/en_US/equipment/hiking/longirod-trek.html)

1. Enter `1` for quantity.
1. Click **ADD TO CART**.

A product is now in your cart. To setup scale prices in WebSphere Commerce:

1. Log in to IBM Management Center for WebSphere Commerce.
1. Click this symbol to work on approved content:

   ![](do-not-localize/chlimage_1-1.jpeg)

   The approved content should be displayed in the header.

1. Select **Catalogs** in the **Management Center Tools** menu.
1. Select **GeometrixxOutdoorsESites** as catalog in the left drop down in the menu bar.
1. Expand the left menu tree of the **Geometrixx Outdoors** catalog to find the required product, for example **Equipment** and then **Equipment Summer**.
1. Select the required product, for example Longirod Trek, open the context menu and select **Show SKUs List**.
1. Double click the first entry to open the product SKU variant.
1. Go to **Manage SKU** tab and scroll down to **Pricing**.
1. Add two more price ranges.

   ![](assets/chlimage_1-46.jpeg)

1. Click **Save and Preview**.

   >[!NOTE]
   >
   >It is important to trigger reindexing which does not happen on save.

1. Navigate to the cart page in AEM, it shows one entry with one pair of Longirod Trek for $89.00.
1. Change the quantity to two and click **Set**. The cart item price is updated to $158.00 which is $79.00 for one.

