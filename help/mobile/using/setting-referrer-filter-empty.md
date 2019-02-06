---
title: Setting Your Referrer Filter to Allow Empty
seo-title: Setting Your Referrer Filter to Allow Empty
description: Follow this page to learn about Referrer Filter. In order to allow the AEM Mobile Application Viewer to view apps on your Author instance, you'll need to set your HTML referrer filter to 'allow empty'.
seo-description: Follow this page to learn about Referrer Filter. In order to allow the AEM Mobile Application Viewer to view apps on your Author instance, you'll need to set your HTML referrer filter to 'allow empty'.
uuid: f4e5fc5f-c689-4c8d-bad2-c0654017cb64
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: administering-adobe-phonegap-enterprise
discoiquuid: 328ff4b8-560b-4abb-8e52-33d6f1dda6f7
index: y
internal: n
snippet: y
---

# Setting Your Referrer Filter to Allow Empty{#setting-your-referrer-filter-to-allow-empty}

>[!NOTE]
>
>Adobe recommends using the SPA Editor for projects that require single page application framework-based client-side rendering (e.g. React). [Learn more](../../sites/developing/using/spa-overview.md).

In order to allow the AEM Mobile Application Viewer to view apps on your Author instance, you'll need to set your HTML referrer filter to 'allow empty'.

If you do not intend to use the Applicaiton Viewer to review applications within development and staging states, you do not need to change the default setting of the referrer filter.

Within your running Author instance of AEM, navigate to: [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr) and search for 'Apache Sling Referrer Filter'. Click to edit the referrer filter and check the 'allow empty' checkbox (see image below). Next hit the save button and close the browser page.

![Referrer Filter settings](assets/chlimage_1-111.png)

