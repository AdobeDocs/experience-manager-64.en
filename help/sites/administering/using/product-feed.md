---
title: Product Feed
seo-title: Product Feed
description: null
seo-description: Learn about the AEM Product Feed.
uuid: 421aba42-f571-4a0b-87f9-f59b519fe282
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 91352c2b-53e6-403a-810f-cba0277a8bd2
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Product Feed{#product-feed}

AEM integrates with [Search&Promote](http://www.adobe.com/solutions/testing-targeting/searchandpromote.html) and allows you to:

* use the eCommerce API, independently of the underlying repository structure and commerce platform.
* leverage the Index Connector feature of Search&Promote to provide a product feed in XML format.
* leverage the Remote Control feature of Search&Promote to perform on-demand or scheduled requests of the product feed
* feed generation for different Search&Promote accounts, configured as cloud services configurations.

You need to have a valid acount and to [configure the connection to Search&Promote](../../../sites/administering/using/search-and-promote.md#configuringtheconnectiontosearchpromote). You also have to verify that you are using the correct [data center](../../../sites/administering/using/search-and-promote.md#configuringthedatacenter) and make sure that the **Remote server URI **is configured.

## Set up the Product Feed {#set-up-the-product-feed}

You first have to enter a web site root and an identifier attribute. To do this:

1. Navigate to your Search&Promote configuration.
1. Click **Edit**.
1. Click the **Index Connector Feed Configuration** tab.
1. Enter the **Web site root** and **Identifier attribute**.

   >[!NOTE]
   >
   >The **Web site root** is the root of your eCommerce website, for example `/content/geometrixx-outdoors/en`.
   >
   >
   >The **Identifier attribute** is a JCR property that uniquely identifies the product: `identifier`.

1. Click **OK**.

Then you also have to edit two configurations in the Web Console before you can generate product feeds.

### Configuring the Day CQ Search&Promote Products Crawler Implementation for Geometrixx {#configuring-the-day-cq-search-promote-products-crawler-implementation-for-geometrixx}

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Click **Day CQ Search&Promote products crawler implementation for Geometrixx**.
1. Specify the Search&Promote account number that this crawler is linked to. It will be used to look up the cloud services configuration used by this crawler.
1. Click **Save**.

### Configuring the Day CQ Search&Promote Products Feed Generator for Geometrixx {#configuring-the-day-cq-search-promote-products-feed-generator-for-geometrixx}

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Click **Day CQ Search&Promote products feed generator for Geometrixx**.
1. Specify the Search&Promote account number that this generator is linked to. It will be used to look up the cloud services configuration used by this generator.
1. Click **Save**.

## Schedule the Product Feed {#schedule-the-product-feed}

To enable scheduled feed generation, you must configure a scheduler for it.  
A scheduler is configured as a child configuration of your specific Search&Promote cloud services configuration.

1. Navigate to your Search&Promote configuration.
1. Click **+** next to **Scheduler configuration**.
1. Enter a **Title** that is recognizable to page authors, and a unique **Name**.
1. Click **Create**. A dialog opens.

   ![](assets/chlimage_1-120.png)

1. Enter the **Remote Control Password**. It is the password you configured in your Search&Pronote account.

   >[!NOTE]
   >
   >This is not the password to your Search&Promote account. You can find and change this password by logging into your Search&Promote account and going to **Index** and then to **Remote control**.

1. Check **Enable schedule** box.
1. Select a **Schedule**. It is the actual feed generation schedule.
1. Enable the **On-demand indexing** or not. This feature is used to manually call the Search&Promote index. If **Request full products feed** is checked, Search&Promote will request a full products feed. Otherwise, an incremental products feed is requested.

   >[!NOTE]
   >
   >The on-demand indexing feature makes use of the Remote Control feature of Search&Promote. When a remote indexing is called, the indexing will not start immediately, but an indexing request will be posted to Search&Promote using the remote control feature.

1. Click **OK**.

Now that you configured everything, you can see an XML page containing all the products under the configured web site root: [http://localhost:4502/etc/commerce/searchpromote/feed/full](http://localhost:4502/etc/commerce/searchpromote/feed/full).
