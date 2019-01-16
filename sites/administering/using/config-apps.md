---
title: Configuring for AEM Apps
seo-title: Configuring for AEM Apps
description: null
seo-description: Learn how to configure AEM Apps.
uuid: d511579b-6596-4145-8c3c-e14902766bc9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: c6b585dc-d9f8-43a2-bbe5-4d544a8f8b15
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configuring for AEM Apps{#configuring-for-aem-apps}

Adobe Experience Manager Apps provides the ability to update the content of your application over the air (OTA). The updated content is stored on the publish instance. To allow the App on your device to connect to the publish instance and check for updates the publish instance needs to be configured to allow an empty referrer header.

### Configuring Empty Referrer Header {#configuring-empty-referrer-header}

To configure the referrer filter service:

*

  Open the Apache Felix console (**Configurations**) at:  
* http://&lt;server&gt;:&lt;port_number&gt;/system/console/configMgr*

*

  Login as admin.

*

  In the **Configurations** menu, select:

  *Apache Sling Referrer Filter*

*

  Check the Allow Empty field, to allow empty/missing referrer headers.

*

  Click **Save** to save your changes.

![](assets/chlimage_1-66.png)

See the [OSGI Configuration Settings](../../deploying/using/osgi-configuration-settings.md) and [Security Checklist - Issues with Cross-Site Request Forgery](/content/docs/en/aem/6-3/administer/security/crx-security-checklist#Issues%20with%20Cross-Site%20Request%20Forgery) for further details. 
