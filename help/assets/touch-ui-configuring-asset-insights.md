---
title: Configuring Assets Insights
description: Learn how to configure Assets Insights in AEM Assets.
contentOwner: AG
feature: Asset Insights,Asset Reports
role: User,Admin
exl-id: b0d62dd3-1868-4d73-95f7-3d6c3ff474d9
---
# Configuring Assets Insights {#configuring-asset-insights}

Adobe Experience Manager Assets fetches usage data around AEM assets used by third-party websites from Adobe Analytics. To enable Assets Insights to retrieve this data and generate insights, first configure the feature to integrate with Adobe Analytics.

>[!NOTE]
>
>Insights are only supported and provided for images.

1. In AEM, click **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Click the **[!UICONTROL Insights Configuration]** card.
1. In the wizard, select a data center and provide your credentials including the name of your organization, user name, and password.

   ![chlimage_1-211](assets/insights_config2.png)

1. Click/tap **[!UICONTROL Authenticate]**.
1. After AEM authenticates your credentials, from the **[!UICONTROL Report Suite]** list, choose an Adobe Analytics report suite from where you want Assets Insights to fetch data. Click **[!UICONTROL Add]**.
1. After AEM sets up your report suite, click/tap **[!UICONTROL Done]**.

## Page Tracker {#page-tracker}

After you configure your Analytics account, the Page Tracker code is generated for you. To enable Assets Insights to track AEM assets used in third-party websites, include the page tracker code in the website code. Use the Page Tracker utility in AEM Assets to generate the page tracker code. For more information on how to include your Page Tracker code in third-party web pages, see [Using Page Tracker and Embed code in web pages](touch-ui-using-page-tracker.md).

1. In AEM, click the **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. From the **[!UICONTROL Navigation]** page, click the **[!UICONTROL Insights Page Tracker]** card.
1. Click the **[!UICONTROL Download]** icon to download the page tracker code.
