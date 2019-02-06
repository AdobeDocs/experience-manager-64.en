---
title: IBM Websphere Setup
seo-title: Geometrixx Outdoors Data Loading
description: Setup the Geometrixx Store and load the Geometrixx Outdoors product data into WebSphere Commerce.
seo-description: Setup the Geometrixx Store and load the Geometrixx Outdoors product data into WebSphere Commerce.
uuid: 035e7fe3-9ee4-498d-be8c-41058738094d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: 19c369ef-e4dd-4a2d-b9f3-b44bdba07b82
index: y
internal: n
snippet: y
---

# IBM Websphere Setup{#ibm-websphere-setup}

The procedures on this page need to be performed in order to setup the Geometrixx Store and load the Geometrixx Outdoors product data into WebSphere Commerce.

>[!NOTE]
>
>The following instructions are intended for use with IBM WebSphere Commerce developer toolkit profile only. Based on your WebSphere Commerce setup, they might be different.

The Geometrixx Outdoors product data .csv file was used as base data. It contains products and variants in english and gaelic . The IDs used in that description might change.

>[!NOTE]
>
>Names and identifiers used on this page (for example **GeometrixxCAS) **should not be changed, otherwise it will require further changes in the configuration files.

### Open Administration Console {#open-administration-console}

1. Select Store Archives &gt; Publish.
1. Filter by Extended sites.
1. Select `ExtendedSitesCatalogAssetStore-FEP.sar`.
1. Update directory to **GeometrixxCAS** and store identifier to **GeometrixxCAS**.
1. Select **Extended Sites Organization**.
1. Set inventory to Non-ATP.
1. Set sample data to **None**.
1. Click **Next**.
1. Click** Finish**.

To complete the setup of the administration console:

1. Select Store Archives &gt; Publish.
1. Select `Aurora.sar`.
1. Select **Publish an asset store...** as the business model.
1. Set store type to **Consumer Direct (MPS)**.
1. Update **directory** and **store identifier**.
1. Select **Extended Sites Organization**.
1. Select new catalog asset store created before (**GeometrixxCAS**).
1. Set inventory to Non-ATP.
1. Click **Next**.
1. Click **Finish**.

### Open Accelerator {#open-accelerator}

1. Select Extended Sites Hub as the store.
1. Select Extended Sites -&gt; New Store
1. Provide name, default currency and email  
   - Store Unique Identifier: Geometrixx  
   - Store Display Name: Geometrixx  
   - Store Short Description: Geometrixx
1. Select **Extended Sites Seller Organization** for Store Organization.
1. Select **Next**.
1. Select new storefront asset store store created above and click **Next**.
1. Select new catalog asset store **GeometrixxCAS** and click **Next**.
1. Select payment methods and click **Next**.
1. Click **Finish**.

You need to do these two last steps for the accelerator:

1. Select Extended Sites &gt; View Stores.
1. Select new extended site and click **Open**.

### Open Management Center {#open-management-center}

1. Open Store Management tool.
1. Select Stores folder.
1. Open the new catalog asset store.
1. Add French as a supported language.
1. Open the new storefront asset store.
1. Add French as a supported language.
1. Select Stores folder.
1. Open new extended site store.
1. Add French as a supported language.

   >[!NOTE]
   >
   >French is used for Gaelic which is currently not supported by Websphere Commerce.

### Refresh Server {#refresh-server}

1. Open Websphere Commerce Toolkit.
1. Stop Websphere Commerce Server.
1. Start Websphere Commerce Server.
1. Publish Websphere Commerce Server.

### Open Management Center {#open-management-center-1}

1. Open Catalogs tool.
1. Select new catalog asset store.
1. Select new Catalog Upload.
1. Select catalog.zip and Save. You can download it form here:

   [Get File](assets/catalog.zip)

1. Wait for load to complete.

### Create Search Index {#create-search-index}

1. Open Database access JSP.
1. Run the following command:

   ```
   select * from catalog;
   ```

1. Note the new master catalog ID.
1. Open the command prompt.
1. Run the following commands:

   ```shell
   cd c:\ibm\wcde_ent70\components\foundation\subcomponents\search\bin
   
   setupSearchIndex.bat -masterCatalogId <master catalog ID> -dbuser <username> -dbuserpwd <password> -dbauser <username> -dbauserpwd 
   ```

   >[!NOTE]
   >
   >Replace `<master catalog ID>` with your own master catalog ID and replace `<username>` and `<password>` with your database username and password.

1. Stop and restart Search server.
1. Run the following commands:

   ```shell
   cd c:\ibm\wcde_ent70\bin
   
   di-preprocess.bat C:\IBM\WCDE_ENT70\search\pre-processConfig\MC_10101\DB2
   
   di-buildindex.bat -masterCatalogId <master catalog ID>
   ```

   >[!NOTE]
   >
   >Replace `<master catalog ID>` with your own master catalog ID.

### Load Inventory {#load-inventory}

1. Extract contents of the inventory zip. You can download it:

   [Get File](assets/inventory.zip)

1. Unzip to `<WCinstallDirectory>\samples\DataLoad\Inventory\Non-ATP`.
1. In the `<WCinstallDirectory>\samples\DataLoad\Inventory directory, configure the wc-dataload-env.xml` to connect to your database.

For example, set the `storeIdentifier` and `fulfillmentCenterName` to the new eSite created and catalog identifier to the new catalog asset store.

```shell
<_config:BusinessContext storeIdentifier=" Geometrixx " catalogIdentifier=" GeometrixxCAS" languageId="-1" currency="USD">
   <_config:ContextData name="fulfillmentCenterName">Geometrixx</_config:ContextData>
</_config:BusinessContext>
```

1. Configure the appropriate `<_config:Database` section to the database for your environment. It should point to DB2, Oracle or local database for connection.
1. Open the `<WCinstallDirectory>\samples\DataLoad\Inventory\Non-ATP\non_ATP_inventory_for_esite.csv` file and update the `CurrentStoreIdentifier`, `CatEntryStoreIdentifier` and `FulfillmentCenterName` with the same values as above.
1. Open command prompt.

   ```shell
   cd c:\ibm\wcde_ent70\bin
   
   dataload <WCinstallDirectory>\samples\DataLoad\Inventory\Non-ATP\wc-dataload-for-esite.xml
   ```

### Open Administration Console {#open-administration-console-1}

1. Go to configuration.
1. Refresh registry.

