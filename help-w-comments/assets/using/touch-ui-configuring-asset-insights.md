---
title: Configuring Asset Insights
seo-title: Configuring Asset Insights
description: Learn how to configure Asset Insights in AEM Assets.
seo-description: Learn how to configure Asset Insights in AEM Assets.
uuid: e6a4a2d5-1721-43ee-bd1e-9f1d11b8c60e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 838591b1-8642-4182-803d-02549eb09a6e
index: y
internal: n
snippet: y
---

# Configuring Asset Insights{#configuring-asset-insights}

Adobe Experience Manager (AEM) Assets fetches usage data around AEM assets used by third-party websites from Adobe Analytics. To enable Asset Insights to retrieve this data and generate insights, first configure the feature to integrate with Adobe Analytics.

1. From the **Navigation** page, click the **Tools** icon.

   ![](assets/chlimage_1-216.png)

1. From the rail, click **Assets**. 

   ![](assets/chlimage_1-217.png)

1. From the **Navigation** page, click the **Insights Configuration** card.
1. In the wizard, select a data center and provide your credentials including the name of your organization, user name, and password.

   ![](assets/chlimage_1-218.png)

1. Click/tap **Authenticate**.
1. After AEM authenticates your credentials, from the **Report Suite** list, choose an Adobe Analytics report suite from where you want Asset Insights to fetch data. Click **Add**.
1. After AEM sets up your report suite, click/tap **Next** on the top right. 
1. In the **Preferences** screen, define events and corresponding variables for the clicks and impressions data you want capture for assets.

   ![](assets/chlimage_1-219.png)

1. Click/tap **Done** and then click/tap **Ok** to close the confirmation message.

## Page Tracker {#page-tracker}

After you configure your Analytics account, the Page Tracker code is generated for you. To enable Assets Insights to track AEM assets used in third-party websites, include the page tracker code in the website code. Use the Page Tracker utility in AEM Assets to generate the page tracker code. For more information on how to include your Page Tracker code in third-party web pages, see [Using Page Tracker and Embed code in web pages](../../assets/using/touch-ui-using-page-tracker.md).

1. From the **Navigation** page, click the **Tools** icon.

   ![](assets/chlimage_1-220.png)

1. From the rail, click **Assets**.

   ![](assets/chlimage_1-221.png)

1. From the **Navigation** page, click the **Insights Page Tracker** card.
1. Click the **Download** icon to download the page tracker code.

