---
title: Configuring Asset Insights
seo-title: Configuring Asset Insights
description: null
seo-description: Learn how to configure Asset Insights in AEM Assets.
uuid: a47df344-835a-4b10-a6b0-22067070fffc
acrolinxdate: 2019-01-12T17 33 29.469-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: green
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/touch_ui_configuring_asset_insights_krs_workflow_f3c2f2ccebf6138e_169_report.xml
acrolinxsentences: 25
acrolinxwords: 281
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 5fde956d-e888-4e58-8d91-0a98e1c324a6
firstpublishinternaldate: 2017-12-01T10 25 13.583-0500
isreadyforlocalization: false
lastpublishinternaldate: 2017-12-01T10 25 13.583-0500
publishinternaldate: 2017-12-01T10 25 13.583-0500
publishinternalurl: https //helpx-internal.corp.adobe.com/content/help/en/experience-manager/6-4/assets/using/touch-ui-configuring-asset-insights.html
index: y
internal: n
snippet: y
---

# Configuring Asset Insights{#configuring-asset-insights}

Adobe Experience Manager (AEM) Assets fetches usage data around AEM assets used by third-party websites from Adobe Analytics. To enable Asset Insights to retrieve this data and generate insights, first configure the feature to integrate with Adobe Analytics.

1. From the **Navigation** page, click the **Tools** icon.

   ![](assets/chlimage_1-162.png)

1. From the rail, click **Assets**. 

   ![](assets/chlimage_1-163.png)

1. From the **Navigation** page, click the **Insights Configuration** card.
1. In the wizard, select a data center and provide your credentials including the name of your organization, user name, and password.

   ![](assets/chlimage_1-164.png)

1. Click/tap **Authenticate**.
1. After AEM authenticates your credentials, from the **Report Suite** list, choose an Adobe Analytics report suite from where you want Asset Insights to fetch data. Click **Add**.
1. After AEM sets up your report suite, click/tap **Next** on the top right. 
1. In the **Preferences** screen, define events and corresponding variables for the clicks and impressions data you want capture for assets.

   ![](assets/chlimage_1-165.png)

1. Click/tap **Done** and then click/tap **Ok** to close the confirmation message.

## Page Tracker {#page-tracker}

After you configure your Analytics account, the Page Tracker code is generated for you. To enable Assets Insights to track AEM assets used in third-party websites, include the page tracker code in the website code. Use the Page Tracker utility in AEM Assets to generate the page tracker code. For more information on how to include your Page Tracker code in third-party web pages, see [Using Page Tracker and Embed code in web pages](../../assets/using/touch-ui-using-page-tracker.md).

1. From the **Navigation** page, click the **Tools** icon.

   ![](assets/chlimage_1-166.png)

1. From the rail, click **Assets**.

   ![](assets/chlimage_1-167.png)

1. From the **Navigation** page, click the **Insights Page Tracker** card.
1. Click the **Download** icon to download the page tracker code.

