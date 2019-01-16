---
title: Magento
seo-title: Magento
description: null
seo-description: Learn how to use AEM with Magento.
uuid: 5b40c980-e117-4940-86a0-1ea22f230709
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: d8d054e4-d9d0-45de-ac53-0dfaf8a00a6d
disttype: dist5
gnavtheme: light
groupsectionnavitems: no
hidemerchandisingbar: inherit
hidepromocomponent: inherit
isreadyforlocalization: false
modalsize: 426x240
pagetitle: Administering Magento
index: y
internal: n
snippet: y
---

# Magento{#magento}

## Registration {#registration}

You can create a registration form using the [foundation form component](../../authoring/using/default-components-foundation.md#form) and add the necessary fields.  
Make sure you select **Magento Registration** as the action type. [](../../authoring/using/default-components-foundation.md#form)

## Product/Catalog Import {#product-catalog-import}

You can re-import catalog blueprint and products from your Magento server by using the [standard blueprint import procedure](../../administering/using/generic.md#importingproducts).  
You just need to select the **Magento2** importer.

![](assets/chlimage_1-43.jpeg) 

## Order-Service {#order-service}

You can add a new mapping to the Apache Sling Service User Mapper Service Amendment. To do that:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Click **Apache Sling Service User Mapper Service Amendment**.

   ![](assets/chlimage_1-44.jpeg)

1. Enter the following information:

    * **Ranking**: 0
    * **Service Mapping**: com.infield.aem.magento2.core:orders=commerce-orders-service

1. Click **Save**.

