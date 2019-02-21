---
title: Integrating with Adobe Target
seo-title: Integrating with Adobe Target
description: Learn about integrating AEM with Adobe Target.
seo-description: Learn about integrating AEM with Adobe Target.
uuid: 110d40aa-d40e-4a1d-919c-7a2b0394e36a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 0f5d02d7-8fe5-474f-a043-a5e65721af9e
index: y
internal: n
snippet: y
---

# Integrating with Adobe Target{#integrating-with-adobe-target}

As part of the Adobe Marketing Cloud, [Adobe Target](http://www.adobe.com/solutions/testing-targeting/testandtarget.html) lets you increase content relevance through targeting and measuring across all channels. Adobe Target is used by marketers to design and execute online tests, create on-the-fly audience segments (based on behavior) and automate the targeting of content and online experiences. AEM has adopted the targeting workflow that is used in Adobe Target Standard. If you use Target, you will be familiar with the targeting editing environment in AEM.

Integrate your AEM sites with Adobe Target to personalize content in your pages:

* Implement content targeting.
* Use Target audiences to create personalized experiences.
* Submit context data to Target when visitors interact with your pages.
* Track conversion rates.

To integrate with Target, perform the following tasks:

1. [Perform prerequisite tasks](../../../sites/administering/using/target-requirements.md): Register with Adobe Target and configure certain aspects of the AEM author instance. Your Adobe Target account must have **approver **level permissions at a minimum. In addition, you must secure the activity settings on the publish node so that it is inaccessible to users.

1. Either:

    1. [Opt into Adobe Target](../../../sites/administering/using/opt-in.md): The opt-in wizard takes your Target account information and creates an Adobe Target cloud configuration and a Target Framework. The wizard also associates your sites with the Target Framework. If the wizard cannot connect to target, refer to the [connection trouble shooting](../../../sites/administering/using/target-configuring.md#main-pars-title-274478668) section. You can then [Modify the default cloud configurations](../../../sites/administering/using/target-configuring.md#modifyingtheoptinwizardconfigurations): If necessary, modify the cloud configuration and framework that the opt-in wizard created. For example, modify the framework to send additional context data to Target. If you want to use Adobe Analytics as a reporting source for Adobe Target, you need to modify the cloud configuration to point to the A4T configuration.
    
    1. [Manually Integrate with Adobe Target](../../../sites/administering/using/target-configuring.md#manuallyintegratingwithadobetarget).

1. [Configure Activities](../../../sites/authoring/using/activitylib.md): Associate your Activities with the Target cloud configuration.

>[!NOTE]
>
>See also [Integrating AEM with Adobe Target and Adobe Analytics using DTM](https://helpx.adobe.com/experience-manager/using/integrate-digital-marketing-solutions.html).

>[!NOTE]
>
>If you are using Target with a custom proxy configuration, you need to configure both HTTP Client proxy configurations as some functionalities of AEM are using the 3.x APIs and some others the 4.x APIs:
>
>* 3.x is configured with [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
>* 4.x is configured with [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)
>

>[!CAUTION]
>
>You must secure the activity settings node **cq:ActivitySettings** on the publish instance so that it is inaccessible to normal users. The activity settings node should only be accessible to the service handling the activity synchronization to Adobe Target.
>
>See [Prerequisites for Integrating with Adobe Target](../../../sites/administering/using/target-requirements.md#securingtheactivitysettings) for detailed information.

When the integration is complete, you can [author targeted content](../../../sites/authoring/using/content-targeting-touch.md) that sends visitor data to Adobe Target. Note that page components require specific code to enable content targeting. (See [Developing for Targeted Content](../../../sites/developing/using/target.md).)

>[!NOTE]
>
>When you target a component in AEM author, the component makes a series of server-side calls to Adobe Target to register the campaign, set up offers, and retrieve Adobe Target segments (if configured). No server-side calls are made from AEM publish to Adobe Target.

### Background Information Sources {#background-information-sources}

Integrating AEM with Adobe Target requires knowlege of Adobe Target, AEM Activities management, and AEM Audiences management. You should be familiar with the following information:

* Adobe Target (See the [Adobe Target documentation](https://marketing.adobe.com/resources/help/en_US/target/)).
* AEM Activities console (See [Managing Activities](../../../sites/authoring/using/activitylib.md)).
* AEM Audiences (See [Managing Audiences](../../../sites/authoring/using/managing-audiences.md)).

>[!NOTE]
>
>When working with Adobe Target, the following is the maximum number of artifacts allowed within a campaign:
>
>* 50 locations
>* 2,000 experiences
>* 50 metrics
>* 50 reporting segments
>

