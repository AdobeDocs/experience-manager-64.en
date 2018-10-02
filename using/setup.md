---
uuid: ae73e0ed-3cdb-489d-9010-1751bdc82afb
index: y
internal: n
snippet: y
translate: y
---

# IBM Websphere Setup

The procedures on this page need to be performed in order to setup the Geometrixx Store and load the Geometrixx Outdoors product data into WebSphere Commerce.

>[!NOTE]
>
><p>The following instructions are intended for use with IBM WebSphere Commerce developer toolkit profile only. Based on your WebSphere Commerce setup, they might be different.</p>

The Geometrixx Outdoors product data .csv file was used as base data. It contains products and variants in english and gaelic . The IDs used in that description might change.

>[!NOTE]
>
><p>Names and identifiers used on this page (for example&nbsp;<b>GeometrixxCAS)&nbsp;</b>should not be changed, otherwise it will&nbsp;require&nbsp;further changes in the configuration files.</p>

### Open Administration Console

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

### Open Accelerator

1. Select Extended Sites Hub as the store.

1. Select Extended Sites -&gt; New Store

1. Provide name, default currency and email - Store Unique Identifier: Geometrixx - Store Display Name: Geometrixx - Store Short Description: Geometrixx

1. Select **Extended Sites Seller Organization** for Store Organization.

1. Select **Next**.

1. Select new storefront asset store store created above and click **Next**.

1. Select new catalog asset store **GeometrixxCAS** and click **Next**.

1. Select payment methods and click **Next**.

1. Click **Finish**.

You need to do these two last steps for the accelerator:

1. Select Extended Sites &gt; View Stores.

1. Select new extended site and click **Open**.

### Open Management Center

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
   ><p>French is used for Gaelic which is currently not supported by Websphere Commerce.</p>

### Refresh Server

1. Open Websphere Commerce Toolkit.

1. Stop Websphere Commerce Server.

1. Start Websphere Commerce Server.

1. Publish Websphere Commerce Server.

### Open Management Center

1. Open Catalogs tool.

1. Select new catalog asset store.

1. Select new Catalog Upload.

1. Select catalog.zip and Save. You can download it form here:

1. Wait for load to complete.

### Create Search Index

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
   ><p>Replace <span class="code">&lt;master catalog ID&gt;</span> with your own master catalog ID and replace <span class="code">&lt;username&gt;</span> and <span class="code">&lt;password&gt;</span> with your database username and password.</p> 

1. Stop and restart Search server.

1. Run the following commands:

   ```shell
   cd c:\ibm\wcde_ent70\bin
   
   di-preprocess.bat C:\IBM\WCDE_ENT70\search\pre-processConfig\MC_10101\DB2
   
   di-buildindex.bat -masterCatalogId <master catalog ID>
   ```

   >[!NOTE]
   >
   ><p>Replace <span class="code">&lt;master catalog ID&gt;</span> with your own master catalog ID.</p>

### Load Inventory

1. Extract contents of the inventory zip. You can download it:

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

### Open Administration Console

1. Go to configuration.

1. Refresh registry.

