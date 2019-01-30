---
title: Applying translation cloud services to folders 
seo-title: Applying translation cloud services to folders 
description: null
seo-description: null
uuid: 8320ed7c-7324-49cd-8445-b0fed5572813
acrolinxdate: 2019-01-12T17 36 50.829-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/transition_cloud_services_krs_workflow_f3c2f2ccebf6138e_211_report.xml
acrolinxsentences: 27
acrolinxwords: 381
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
discoiquuid: 28d8fb19-a965-4d78-986f-547f5d298d22
disttype: dist5
gnavtheme: light
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Applying translation cloud services to folders {#applying-translation-cloud-services-to-folders}

Adobe Experience Manager (AEM) lets you avail cloud-based translation services from the translation provider of your choice to ensure your assets are translated based on your requirements.

You can apply the translation cloud service directly to your asset folder so they can be utilized during translation workflows.

## Applying the translation services {#applying-the-translation-services}

Applying translation cloud services directly to your asset folder eliminates the need to configure translation services when you create or update translation workflows.

1. From the Assets UI, select the folder to which you want to apply translation services.
1. From the toolbar, click/tap the **Properties** icon to display the **Folder Properties** page.

   ![](assets/chlimage_1-168.png)

1. Navigate to the **Cloud Services** tab.
1. From the Cloud Service Configurations list, choose the desired translation provider. For example, if you want to avail translation services from Microsoft, choose **Microsoft Translator**.

   ![](assets/chlimage_1-169.png)

1. Choose the connector for the translation provider.

   ![](assets/chlimage_1-170.png)

1. From the toolbar, click/tap **Save**, and then click **OK** to close the dialog.The translation service is applied to the folder.

## Applying custom translation connector  {#applying-custom-translation-connector}

If you want to apply a custom connector for the translation services you want to use in translation workflows. To apply a custom connector, first install the connector from Package Manager. Then, configure the connector from the Cloud Services console. After you configure the connector, it is available in the list of connectors in the Cloud Services tab described in [Applying the translation services](../../assets/using/transition-cloud-services.md#main-pars-title-1392200838). After you apply the custom connector and run translation workflows, the **Translation Summary** tile of the translation project displays the connector details under the heads **Provider** and **Method**.

1. Install the connector from Package Manager.
1. Click/tap the AEM logo, and navigate to **Tools** &gt; **Deployment** &gt; **Cloud Services**.
1. Locate the connector you installed under **Third Party Services** in the **Cloud Services** page.

   ![](assets/chlimage_1-171.png)

1. Click/tap the **Configure now** link to open the **Create Configuration** dialog.

   ![](assets/chlimage_1-172.png)

1. Specify a title and a name for the connector, and then click/tap **Create**. The custom connector is available in the list of connectors in the **Cloud Services** tab described in step 5 of [Applying the translation services](#main-pars-title-1392200838). 
1. Run any translation workflow described in [Creating Translation Projects](../../assets/using/translation-projects.md) after you apply the custom connector. Verify the details of the connector in the **Translation Summary** tile of the translation project in the **Projects** console.

   ![](assets/chlimage_1-173.png)

