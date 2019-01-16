---
title: hybris
seo-title: hybris
description: null
seo-description: Learn how to use AEM with hybris.
uuid: a019f7a6-3c54-46be-a63b-90887ff9b70f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: e659b0dd-75be-4792-a8c7-a7b096fdaa60
disttype: dist5
gnavtheme: light
isreadyforlocalization: false
pagetitle: Administering hybris
index: y
internal: n
snippet: y
---

# hybris{#hybris}

After installation you can configure your instance:

1. [Configure the Facetted Search for Geometrixx Outdoors](#configurethefacettedsearchforgeometrixxoutdoors).
1. [Configure the Catalog Version](#configurethecatalogversion).
1. [Configure the Import Structure](#configuretheimportstructure).
1. [Configure the Product Attributes to Load](#configuretheproductattributestoload).
1. [Importing the Product Data](#importingtheproductdata).
1. [Configure the Catalog Importer](#configurethecatalogimporter).
1. Use the [importer to import the catalog](#catalogimporter) into a specific location in AEM.

## Configure the Facetted Search for Geometrixx Outdoors {#configure-the-facetted-search-for-geometrixx-outdoors}

>[!NOTE]
>
>This is not needed for hybris 5.3.0.1 and later.

1. In your browser, navigate to the **hybris management console** at:

   [http://localhost:9001/hmc/hybris](http://localhost:9001/hmc/hybris)

1. From the sidebar, select **System**, then **Facet search**, then **Facet Search Config**.
1. **Open Editor** for the **Sample Solr Configuration for clothescatalog**.  

1. Under **Catalog versions** use **Add Catalog version** to add `outdoors-Staged` and `outdoors-Online` to the list.
1. **Save** the configuration.
1. Open **SOLR Item types** to add **SOLR Sorts** to `ClothesVariantProduct`:

    * relevance ("Relevance", score)
    * name-asc ("Name (ascending)", name)
    * name-desc ("Name (descending)", name)
    * price-asc ("Price (ascending)", priceValue)
    * price-desc ("Price (descending)", priceValue)

   >[!NOTE]
   >
   >Use the context menu (usually right-button click) to select `Create Solr sort`.
   >
   >
   >For Hybris 5.0.0 open the `Indexed Types` tab, double-click on `ClothesVariantProduct`, then the tab `SOLR Sort`.

   ![](assets/chlimage_1-42.png)

1. In the **Indexed Types** tab set the **Composed Type** to:

   `Product - Product`

1. In the **Indexed Types** tab adjust the **Indexer queries** for `full`:

   ```shell
   SELECT {pk} FROM {Product} WHERE {pk} NOT IN ({{SELECT {baseProductpk} FROM {variantproduct}}})
   ```

1. In the **Indexed Types** tab adjust the **Indexer queries** for `incremental`:

   ```shell
   SELECT {pk} FROM {Product} WHERE {pk} NOT IN ({{SELECT {baseProductpk} FROM {variantproduct}}}) AND {modifiedtime} <= ?lastIndexTime
   ```

1. In the **Indexed Types** tab adjust the `category` facet. Double-click on the last entry in the category list to open the **Indexed property** tab:

   >[!NOTE]
   >
   >For hybris 5.2 make sure that the `Facet` attribute in the Properties table is selected according to the screenshot below:

   ![](assets/chlimage_1-43.png) ![](assets/chlimage_1-44.png)

1. Open the **Facet Settings** tab and adjust the field values:

   ![](assets/chlimage_1-45.png)

1. **Save** the changes.
1. Again from **SOLR Item types**, adjust the `price` facet according to the following screenshots. As with `category`, double-click on `price` to open the **Indexed property** tab:

   ![](assets/chlimage_1-46.png)

1. Open the **Facet Settings** tab and adjust the field values:

   ![](assets/chlimage_1-47.png)

1. **Save** the changes.
1. Open **System**, **Facet search**, then **Indexer operation wizard**. Start a cronjob:

    * **Indexer operation**: `full`   
    
    * **Solr configuration**: `Sample Solr Config for Clothes`

## Configure the Catalog Version {#configure-the-catalog-version}

The **Catalog version** ( `hybris.catalog.version`) that is imported can be configured for the OSGi service:

**Day CQ Commerce Hybris Configuration** 
( `com.adobe.cq.commerce.hybris.common.DefaultHybrisConfigurationService`)

**Catalog version** is usually set to either `Online` or `Staged` (the default).

>[!NOTE]
>
>When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../deploying/using/configuring-osgi.md) for full details. Also see the console for a full list of configurable parameters and their defaults.

The log output provides feedback on the created pages and components and reports potential errors.

## Configure the Import Structure {#configure-the-import-structure}

The following listing shows a sample structure (of assets, pages and components) that is created by default:

```shell
+ /content/dam/path/to/images
  + 12345.jpg (dam:Asset)
    + ...
  + ...
+ /content/site/en
  - cq:commerceProvider = "hybris"
  - cq:hybrisBaseStore = "basestore"
  - cq:hybrisCatalogId = "catalog"
  + category1 (cq:Page)
    + jcr:content (cq:PageContent)
      - jcr:title = "Category 1"
    + category11 (cq:Page)
      + jcr:content (cq:PageContent)
        - jcr:title = "Category 1.1"
      + 12345 (cq:Page)
        + jcr:content (cq:PageContent)
          + par
            + product (nt:unstructured)
              - cq:hybrisProductId = "12345"
              - sling:resourceType = "commerce/components/product"
              + image (nt:unstructured)
                - sling:resourceType = "commerce/components/product/image"
                - fileReference = "/content/dam/path/to/images/12345.jpg"
              + 12345.1-S (nt:unstructured)
                - cq:hybrisProductId = "12345.1-S"
                - sling:resourceType = "commerce/components/product"
                + image (nt:unstructured)
                  - sling:resourceType = "commerce/components/product/image"
                  - fileReference = "/content/dam/path/to/images/12345.1-S.jpg"
              + ...
```

Such a structure is created by the OSGi service `DefaultImportHandler` that implements the `ImportHandler` interface. An import handler is called by the actual importer to create products, product variations, categories, asset, etc.

>[!NOTE]
>
>You can [customize this process by implementing your own import handler](#customizingtheimportprocess).

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:30.831-0500

<p>Where has the following gone?</p> 
<ul> 
 <li><strong>Day CQ Commerce Hybris Default Import Handler</strong></li> 
</ul> 
<p>Can only find:</p> 
<ul> 
 <li>Geometrixx-Outdoors Catalog Blueprint Importer<br /> </li> 
 <li>Geometrixx-Outdoors Product Importer</li> 
 <li>Adobe CQ Commerce Page Event Listener</li> 
 <li>Adobe CQ Commerce PIM Post Processor</li> 
 <li>Adobe CQ Commerce Product Catalog Generator</li> 
 <li>Adobe CQ Commerce Promotion Manager</li> 
</ul>

 -->

The structure to be generated when importing can be configured for:

``**Day CQ Commerce Hybris Default Import Handler** 
`(com.adobe.cq.commerce.hybris.importer.DefaultImportHandler`)

When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../deploying/using/configuring-osgi.md) for full details. Also see the console for a full list of configurable parameters and their defaults.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:30.859-0500

<p>a lot more parameters on geometrixx-outdoors/en_US - what needs documenting? what is configured manually?</p>

 -->

<!-- 

Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-48.png" />

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:30.895-0500

<p>cross-references to MSM?</p>

 -->

<!-- 

Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-49.png" />

 -->

## Configure the Product Attributes to Load {#configure-the-product-attributes-to-load}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:30.946-0500

<p>See <a href="https://issues.adobe.com/browse/DOC-3984">https://issues.adobe.com/browse/DOC-3984</a></p>

 -->

The response parser can be configured to define the properties and attributes to be loaded for (variant) products:

1. Configure the OSGi bundle:

   **Day CQ Commerce Hybris Default Response Parser** 
   ( `com.adobe.cq.commerce.hybris.impl.importer.DefaultResponseParser`)

   Here you can define various options and attributes needed for loading and mapping.

   >[!NOTE]
   >
   >When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../deploying/using/configuring-osgi.md) for full details. Also see the console for a full list of configurable parameters and their defaults.

## Importing the Product Data {#importing-the-product-data}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:31.063-0500

<p>The import procedures need checking.</p> 
<p>In L16 /etc/importers/hybris doesn't exist anymore, but http://localhost:4502/miscadmin#/etc/commerce/productimporter does</p> 
<p>And if there is just the one now then these procedures need to be moved to a generic location.</p> 
<p> </p> 
<p>see also http://ec2author.day.com:8080/content/docs/en/cq/6-0/administer/ecommerce/native.html?#Importing%20Products<br /> </p>

 -->

There are a variety of ways to import the product data. The product data can be imported when initially setting up the environment, or after changes have been made in the hybris data:

* [Full Import](#fullimport)
* [Incremental Import](#incrementalimport)
* [Express Update](#expressupdate)

Actual product information imported from hybris is held in the repository under:

`/etc/commerce/products`

The following properties indicate the link with hybris:

* `commerceProvider`
* `cq:hybrisCatalogId`
* `cq:hybrisProductID`

>[!NOTE]
>
>The hybris implementation (i.e. `geometrixx-outdoors/en_US`) only stores product IDs and other basic information under `/etc/commerce`.
>
>The hybris server is referenced every time information about a product is requested.

#### Full Import {#full-import}

1. If required, delete all existing product data using CRXDE Lite.

    1. Navigate to the sub-tree holding the product data:  
       `/etc/commerce/products`  
       For example:  
       [ `http://localhost:4502/crx/de/index.jsp#/etc/commerce/products`](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)
    
    1. Delete the node that holds your product data; for example, `outdoors`.
    1. **Save All** to persist the change.

1. Open the hybris importer in AEM:

   `/etc/importers/hybris.html`

   For example:

   [http://localhost:4502/etc/importers/hybris.html](http://localhost:4502/etc/importers/hybris.html)

1. Configure the required parameters; for example:

   ![](assets/chlimage_1-50.png)

1. Click **Import Catalog** to start the import.

   When complete, you can verify the data imported at: `  
   /etc/commerce/products/outdoors`  
   You can open this in CRXDE Lite; for example:  
   ` [http://localhost:4502/crx/de/index.jsp#/etc/commerce/products](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)`

### Incremental Import {#incremental-import}

1. Check the information held in AEM for the relevant product(s), in the appropriate sub-tree under:

   `/etc/commerce/products`

   You can open this in CRXDE Lite; for example:  
   [http://localhost:4502/crx/de/index.jsp#/etc/commerce/products](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)

1. In hybris, update the information held on the revelant product(s).  

1. Open the hybris importer in AEM:

   `/etc/importers/hybris.html`

   For example:

   [http://localhost:4502/etc/importers/hybris.html](http://localhost:4502/etc/importers/hybris.html)

1. Select the clickbox **Incremental Import**.
1. Click **Import Catalog** to start the import.

   When complete, you can verify the data updated in AEM under: `  
   /etc/commerce/products`  
   ` [](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)`

### Express Update {#express-update}

The import process can take a long time, so as an extension to the [Product Synchronization](#productsynchronizationandpublishing) you can select specific areas of the catalog for an express update that is triggered manually. This uses the export feed together with the standard attributes configuration.

1. Check the information held in AEM for the relevant product(s), in the appropriate sub-tree under:

   `/etc/commerce/products`

   You can open this in CRXDE Lite; for example:  
   [http://localhost:4502/crx/de/index.jsp#/etc/commerce/products](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)

1. In hybris, update the information held on the revelant product(s).  

1. In hybris, add the product(s) to the Express Queue; for example:

   <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:31.741-0500

<p>Need new screenshot...</p>

 -->

   ![](assets/chlimage_1-51.png)

1. Open the hybris importer in AEM:

   `/etc/importers/hybris.html`

   For example:

   [http://localhost:4502/etc/importers/hybris.html](http://localhost:4502/etc/importers/hybris.html)

1. Select the clickbox **Express Update**.
1. Click **Import Catalog** to start the import.

   When complete, you can verify the data updated in AEM under: `  
   /etc/commerce/products`  
   ` [](http://localhost:4502/crx/de/index.jsp#/etc/commerce/products)`

## Configure the Catalog Importer {#configure-the-catalog-importer}

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (buergi@adobe.com)
Last Modified Date: 2017-11-30T05:00:31.914-0500

<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">We need a better wording. If I read it, I thin about polling, periodically updating the data. But this configuration defines parameters for one import.</p> 
<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">Let's add another section about polling:</p> 
<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">PollingCatalogUpdater will call the DefaultHybrisImporter in 'incrementalImport" mode. Polling importer is a more generic CQ feature that we are using for this and also for express update.</p> 
<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">Here's an example, please incorporate: http://experiencedelivers.adobe.com/cemblog/en/experiencedelivers/2013/03/example-of-cq-poll-config.html</p> 
<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">Levente Santha may provide more details</p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:31.929-0500

<p>have reworded, will incorporate other examples later.</p>

 -->

The hybris catalog can be imported into AEM, using the batch importer for hybris catalogs, categories and products.

The parameters used by the importer can be configured for:

**Day CQ Commerce Hybris Catalog Importer** 
( `com.adobe.cq.commerce.hybris.impl.importer.DefaultHybrisImporter`)

When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../deploying/using/configuring-osgi.md) for full details. Also see the console for a full list of configurable parameters and their defaults.

## Catalog Import {#catalog-import}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:31.986-0500

<p>We need a new screenshot, now we have</p> 
<ol> 
 <li>Full import</li> 
 <li>Incremental import</li> 
 <li>Express update (new feature for 5.6.200)</li> 
</ol>

 -->

The hybris package comes with a catalog importer for setting up the initial page structure.

This is available from:

`http://localhost:4502/etc/importers/hybris.html` 

![](assets/ecommerceimportconsole.png)

The following information has to be provided:

* **Base store** 
  The identifier of the base store configured in hybris.

* **Catalog** 
  The identifier of the catalog to import.

* **Root path** 
  The path where the catalog should be imported into.

## Removing a Product from the Catalog {#removing-a-product-from-the-catalog}

To remove one, or more, products from the catalog:

1. [Configure the for OSGi service](../../deploying/using/configuring-osgi.md) **Day CQ Commerce Hybris Catalog Importer**; see also [Configure the Catalog Importer](#configurethecatalogimporter).

   Activate the following properties:

    * **Enable product removal**
    * **Enable product asset removal**

   >[!NOTE]
   >
   >When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../deploying/using/configuring-osgi.md) for full details. Also see the console for a full list of configurable parameters and their defaults.

1. Initialize the importer by performing two incremental updates (see [Catalog Import](#catalogimport)):

    * The first time run result in a set of changed products - indicated in the log list.  
    * For the second time no products should be updated.

   >[!NOTE]
   >
   >The first import is to initialize the product information. The second import verifies that everything worked and the is product set is ready.

1. Check the category page that contains the product you want to remove. The product details should be visible.

   For example, the following category shows details of the Cajamara product:

   [http://localhost:4502/editor.html/content/geometrixx-outdoors/en_US/equipment/biking.html](http://localhost:4502/editor.html/content/geometrixx-outdoors/en_US/equipment/biking.html)

1. Remove the product in the hybris console. Use the option **Change approval status** to set the status to `unapproved`. The product will be removed from the live-feed.

   For example:

    * Open the page [http://localhost:9001/productcockpit](http://localhost:9001/productcockpit)
    * Select the catalog `Outdoors Staged`
    * Search for `Cajamara`
    * Select this product and change the approval status to `unapproved`

1. Perform another incremental update (see [Catalog Import](#catalogimport)). The log will list the deleted product.
1. 

   <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:32.377-0500

<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">need a link when catalog rollout is specifically documented; see:</p> 
<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">https://issues.adobe.com/browse/DOC-3933</p> 
<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">https://issues.adobe.com/browse/DOC-3929</p> 
<p style="font-family: tahoma, arial, helvetica, sans-serif; font-size: 12px;">https://issues.adobe.com/browse/DOC-4734</p>

 -->

   [Rollout](../../administering/using/generic.md#rollingoutacatalog) the appropriate catalog. The product and product page will have been removed from within AEM.

   For example:

    * Open:  
      [http://localhost:4502/aem/catalogs.html/content/catalogs/geometrixx-outdoors-hybris](http://localhost:4502/aem/catalogs.html/content/catalogs/geometrixx-outdoors-hybris)
    
    * Rollout the `Hybris Base` catalog
    * Open:  
      [http://localhost:4502/editor.html/content/geometrixx-outdoors/en_US/equipment/biking.html](http://localhost:4502/editor.html/content/geometrixx-outdoors/en_US/equipment/biking.html)
    
    * The `Cajamara` product will have been removed from the `Bike` category

1. To reinstate the product:

    1. In hybris, set the approval status back to **approved** 
    
    1. In AEM:

        1. perform an incremental update
        1. rollout the appropriate catalog again  
        1. refresh the appropriate category page

## Add Order History Trait to the Client Context {#add-order-history-trait-to-the-client-context}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:00:32.469-0500

<p>might need updating for 6.1 - "Deprecate the ClientContext":</p> 
<p>https://issues.adobe.com/browse/CQ-7796</p> 
<p>Martin: Correct -&gt; the whole commerce module is not yet on context hub</p>

 -->

To add order history to the [client context](../../developing/using/client-context.md):

1. Open the [client context design page](../../administering/using/client-context.md), by either:

    * Open a page for editing, then open the client context using **Ctrl-Alt-c** (windows) or **control-option-c** (Mac). Use the pencil icon in the top left corner of the client context to **Open the ClientContext design page**.  
    
    * Navigate directly to [http://localhost:4502/etc/clientcontext/default/content.html](http://localhost:4502/etc/clientcontext/default/content.html)

1. [Add the **Order History** component](../../administering/using/client-context.md#addingapropertycomponent) to the **Shopping Car**t component of the client context.
1. You can confirm that the client context is showing details of your order history. For example:

    1. Open the [client context](../../administering/using/client-context.md).
    1. Add an item to the cart.
    1. Complete the checkout.
    1. Check the client context.
    1. Add another item to the cart.
    1. Navigate to the checkout page:

        * The client context shows a summary of the order history.  
        * The message "You're a returning customer" is shown.

   >[!NOTE]
   >
   >The message is realized by:  

   >
   >    
   >    
   >    * Navigate to  
   >      [http://localhost:4502/content/campaigns/geometrixx-outdoors/hybris-returning-customer.html](http://localhost:4502/content/campaigns/geometrixx-outdoors/hybris-returning-customer.html)  
   >      The campaign consists of one experience.
   >    
   >    * Click on the segment  
   >      ( [http://localhost:4502/etc/segmentation/geometrixx-outdoors/returning-customer.html](http://localhost:4502/etc/segmentation/geometrixx-outdoors/returning-customer.html))
   >    
   >    * The segment is built using the **Order History Property** trait.
   >    
   >

<!-- 

Comment Type: draft

<h2>Potential Promotion</h2>

 -->

<!-- 

Comment Type: draft

<p>It is possible to get a list of all potential promotions for a cart. You can use it in a potential promotion trait and to show on the cart page.</p>

 -->

<!-- 

Comment Type: draft

<ol> 
 <li><p>Open the <a href="../../administering/using/client-context.md">client context design page</a>, by either:</p> 
  <ul> 
   <li>Open</li> 
  </ul> </li> 
 <li><p>e <strong>Shopping Car</strong>t component of the client context.</p> </li> 
 <li><p>You can confirm that the client context is showing details of your order history. For example:</p> 
  <ol> 
   <li>Open the <a href="../../administering/using/client-context.md">client context</a>.</li> 
   <li>Add an item to the cart.</li> 
   <li>Complete the checkout.</li> 
   <li>Check the client context.</li> 
   <li>Add another item to the cart.</li> 
   <li>Navigate to the checkout page: 
    <ul> 
     <li>The client context shows a summary of the order history.<br /> </li> 
     <li>The message "You're a returning customer" is shown.<br /> </li> 
    </ul> </li> 
  </ol> 
  <note type="note"> 
   <p>The message is realized by:<br /> </p> 
   <ul> 
    <li>Navigate to<br /> <a href="http://localhost:4502/content/campaigns/geometrixx-outdoors/hybris-returning-customer.html">http://localhost:4502/content/campaigns/geometrixx-outdoors/hybris-returning-customer.html</a><br /> The campaign consists of one experience.</li> 
    <li>Click on the segment<br /> (<a href="http://localhost:4502/etc/segmentation/geometrixx-outdoors/returning-customer.html">http://localhost:4502/etc/segmentation/geometrixx-outdoors/returning-customer.html</a>)</li> 
    <li>The segment is built using the <strong>Order History Property</strong> trait.</li> 
   </ul> 
  </note></li> 
 <li></li> 
 <li></li> 
 <li><p>this is</p> </li> 
</ol>

 -->

