---
title: Setting timeout values for use with Acrobat Reader DC extensions 
seo-title: Setting timeout values for use with Acrobat Reader DC extensions 
description: null
seo-description: Learn how to set timeout values for use with Acrobat Reader DC extensions.
uuid: 912d6f61-fb5a-47d5-a8dd-bad509f8fc4c
acrolinxdate: 2016-05-31T07 03 01.593-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/setting_timeout_values_acrobat_reader_admin_5e12de0b318c6865_2366_report.xml
acrolinxsentences: 7
acrolinxwords: 172
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: fbb221c6-b55d-48b1-a632-a6d9811c83a0
isreadyforlocalization: false
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
