---
title: Digital River
seo-title: Digital River
description: Learn about Digital River integration with AEM.
seo-description: Learn about Digital River integration with AEM.
uuid: 9604d780-5b60-492f-ae80-5ca7b02f5c10
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: b01891ea-0f72-4e6c-a216-ab6aca16da97
pagetitle: Administering Digital River
index: y
internal: n
snippet: y
---

# Digital River{#digital-river}

## Product Import {#product-import}

>[!NOTE]
>
>This section must be performed by someone with write access to `/etc/commerce/products` and `/etc/tags`.

To import products to a specific folder:

1. In the AEM Home Page, click **Commerce**.

   ![](assets/chlimage_1.jpeg)

1. Click **Products**.

   ![](assets/chlimage_1-1.jpeg)

1. Click **Create** and select **Create Folder**.

   ![](assets/chlimage_1-2.jpeg)

1. Enter the required values and click **Create**.

   ![](assets/chlimage_1-3.jpeg)

1. Enter the newly created folder by clicking it.

   ![](assets/chlimage_1-4.jpeg)

1. Click **Create** again and select **Import Products**.

   ![](assets/chlimage_1-5.jpeg)

1. Fill in the following information:

    * **Server**: Use the API endpoint provided by your Account or Project Manager.
    * **API Key**: Use the API Key provided by your Account or Project Manager.
    * **Secret**: Use the Secret provided by your Account or Project Manager.
    * **Locale**: Enter in the Locale of the products you want to import. If left blank, it will default to `en_us`.
    
    * For the first import leave **Is this an incremental import?** blank. For subsequent imports you can check this.
    * Leave all **Collection** fields blank.

   ![](assets/chlimage_1-6.jpeg)

1. Click **Import**. A pop-up opens during the import stating that it is importing. You have to wait.
1. After the import is done, the screen will display information about what was done. You can then click **Done** and it will take you back to the folder, now populated with products.

## Catalog Blueprint Import {#catalog-blueprint-import}

>[!NOTE]
>
>This section must be performed by someone with write access to `/content/catalogs`.

To import a catalog blueprint:

1. In the AEM Home Page, click **Commerce**.

   ![](assets/chlimage_1-7.jpeg)

1. Click **Catalogs**.

   ![](assets/chlimage_1-8.jpeg)

1. Click **Create** and select **Create Folder**.

   ![](assets/chlimage_1-9.jpeg)

1. Enter the required values and click **Create**.

   ![](assets/chlimage_1-10.jpeg)

1. Enter the newly created folder by clicking it.
1. Click **Create** again and select **Import Blueprints**.

   ![](assets/chlimage_1-11.jpeg)

1. Fill in the following information:

    * **Server**: Use the API endpoint provided by your Account or Project Manager.
    * **API Key**: Use the API Key provided by your Account or Project Manager.
    * **Secret**: Use the Secret provided by your Account or Project Manager.
    * **Locale**: Enter in the Locale of the products you want to import. If left blank, it will default to `en_us`.
    
    * **Catalag Name**: Type a name for the imported Catalog. If left blank, it will default to `Digital River`.

   ![](assets/chlimage_1-12.jpeg)

1. Click **Import**. A pop-up opens during the import stating that it is importing. You have to wait.
1. After the import is done, the screen will display information about what was done. You can then click **Done** and it will take you back to the folder, now populated with a Catalog Blueprint.

## Creating a Catalog {#creating-a-catalog}

>[!NOTE]
>
>This section must be performed by someone with write access to `/content/we-retail/us/en`.

To create a Catalog based on your blueprint:

1. In the AEM Home Page, click **Sites**.

   ![](assets/chlimage_1-13.jpeg)

1. Navigate to `/sites.html/content/we-retail/us/en and select Products.`

   ![](assets/chlimage_1-14.jpeg)

1. Click **Delete** and then **Force Delete**.

   ![](assets/chlimage_1-15.jpeg)

1. Click **Create** and **Catalog**.

   ![](assets/chlimage_1-16.jpeg)

1. Navigate and select the appropriate Catalog Blueprint.

   ![](assets/chlimage_1-17.jpeg)

1. Click **Next**.

   ![](assets/chlimage_1-18.jpeg)

1. Fill in the fields and click **Create**.
1. Once it's created, you have two options:

    1. Clicking **Done** brings you back to Sites.
    1. Clicking **Open Catalog** opens the new catalog page.

   ![](assets/chlimage_1-19.jpeg)

