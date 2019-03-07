---
title: Setting timeout values for use with Acrobat Reader DC extensions 
seo-title: Setting timeout values for use with Acrobat Reader DC extensions 
description: Learn how to set timeout values for use with Acrobat Reader DC extensions.
seo-description: Learn how to set timeout values for use with Acrobat Reader DC extensions.
uuid: 7656ed08-bd38-4cea-a3e7-3c67ca409798
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 6d7a12a3-9f34-4af5-b07e-7badc622c5bc
index: y
internal: n
snippet: y
---

# Setting timeout values for use with Acrobat Reader DC extensions {#setting-timeout-values-for-use-with-acrobat-reader-dc-extensions}

When working on many PDF files in Acrobat Reader DC extensions, ensure that the following time-out values are set appropriately to prevent jobs from timing out and failing:

**Document Disposal Timeout**

This value can be set in administration console. Click Settings > Core System Settings > Configurations and specify a value for Default Document Disposal Timeout.

**User Manager AEM forms Timeout:** This value can be set by editing the config.xml file. In administration console, click Settings > User Management > Configuration > Import and export configuration files, and then click Export. Open the exported config.xml file and edit the following lines:

&lt;entry key="assertionValidityInMinutes" value="600"/&gt;

&lt;entry key="SessionTimeout" value="600"/&gt;

Save and then import the config.xml file back into administration console.

**Application Server Session Timeout:** This value can be set on the application server. For more information, see the documentation provided with your application server.
