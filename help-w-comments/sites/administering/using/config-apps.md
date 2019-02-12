---
title: Configuring for AEM Apps
seo-title: Configuring for AEM Apps
description: Learn how to configure AEM Apps.
seo-description: Learn how to configure AEM Apps.
uuid: 4d016f5e-c3dd-423c-b607-31a0112da746
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: a5ed0a59-239e-4144-85b3-ba19b19cbbe6
index: y
internal: n
snippet: y
---

# Configuring for AEM Apps{#configuring-for-aem-apps}

Adobe Experience Manager Apps provides the ability to update the content of your application over the air (OTA). The updated content is stored on the publish instance. To allow the App on your device to connect to the publish instance and check for updates the publish instance needs to be configured to allow an empty referrer header.

### Configuring Empty Referrer Header {#configuring-empty-referrer-header}

To configure the referrer filter service:

* Open the Apache Felix console (**Configurations**) at:  
* http://&lt;server&gt;:&lt;port_number&gt;/system/console/configMgr*
* Login as admin.
* In the **Configurations** menu, select:
* Check the Allow Empty field, to allow empty/missing referrer headers.
* Click **Save** to save your changes.

![](assets/chlimage_1-65.png)

See the [OSGI Configuration Settings](../../../sites/deploying/using/osgi-configuration-settings.md) and [Security Checklist - Issues with Cross-Site Request Forgery](/content/docs/en/aem/6-3/administer/security/crx-security-checklist#Issues%20with%20Cross-Site%20Request%20Forgery) for further details. 
