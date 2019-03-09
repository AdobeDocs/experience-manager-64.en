---
title: Magento
seo-title: Magento
description: Learn how to use AEM with Magento.
seo-description: Learn how to use AEM with Magento.
uuid: f3377316-7292-4c14-8ed0-ac181b3d4f4c
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: 03d5c142-9caf-4e78-938b-7c94dff6c9b1
pagetitle: Administering Magento
---

# Magento{#magento}

## Registration {#registration}

You can create a registration form using the [foundation form component](../../../sites/authoring/using/default-components-foundation.md#form) and add the necessary fields.  
Make sure you select **Magento Registration** as the action type. [](../../../sites/authoring/using/default-components-foundation.md#form)

## Product/Catalog Import {#product-catalog-import}

You can re-import catalog blueprint and products from your Magento server by using the [standard blueprint import procedure](../../../sites/administering/using/generic.md#importing-products).  
You just need to select the **Magento2** importer.

![](assets/chlimage_1-42.jpeg) 

## Order-Service {#order-service}

You can add a new mapping to the Apache Sling Service User Mapper Service Amendment. To do that:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Click **Apache Sling Service User Mapper Service Amendment**.

   ![](assets/chlimage_1-43.jpeg)

1. Enter the following information:

    * **Ranking**: 0
    * **Service Mapping**: com.infield.aem.magento2.core:orders=commerce-orders-service

1. Click **Save**.

