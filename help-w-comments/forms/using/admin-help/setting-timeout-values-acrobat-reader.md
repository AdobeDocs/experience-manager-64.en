---
title: Setting timeout values for use with Acrobat Reader DC extensions 
seo-title: Setting timeout values for use with Acrobat Reader DC extensions 
description: Learn how to set timeout values for use with Acrobat Reader DC extensions.
seo-description: Learn how to set timeout values for use with Acrobat Reader DC extensions.
uuid: 54dc1c68-de7d-4bbd-a678-4d92afb3a489
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 7970f673-e19d-427a-9c02-dedcf9cf8981
index: y
internal: n
snippet: y
---

# Setting timeout values for use with Acrobat Reader DC extensions {#setting-timeout-values-for-use-with-acrobat-reader-dc-extensions}

<!--
Comment Type: remark
Last Modified By:
Last Modified Date:
<p>Bug 1539440:</p>
-->

When working on many PDF files in Acrobat Reader DC extensions, ensure that the following time-out values are set appropriately to prevent jobs from timing out and failing:

**Document Disposal Timeout**

This value can be set in administration console. Click Settings > Core System Settings > Configurations and specify a value for Default Document Disposal Timeout.

**User Manager AEM forms Timeout:** This value can be set by editing the config.xml file. In administration console, click Settings > User Management > Configuration > Import and export configuration files, and then click Export. Open the exported config.xml file and edit the following lines:

&lt;entry key="assertionValidityInMinutes" value="600"/&gt;

&lt;entry key="SessionTimeout" value="600"/&gt;

Save and then import the config.xml file back into administration console.

**Application Server Session Timeout:** This value can be set on the application server. For more information, see the documentation provided with your application server.
