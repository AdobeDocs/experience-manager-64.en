---
title: PDF Generator backup limitations
seo-title: PDF Generator backup limitations
description: null
seo-description: Learn about PDF Generator backup limitations.
uuid: 3ba5d4d3-6d34-4228-92ad-b2a97a696827
acrolinxdate: 2016-05-31T07 02 26.275-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/pdf_generator_backup_limitations_admin_5e12de0b318c6865_2351_report.xml
acrolinxsentences: 2
acrolinxwords: 55
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 85fe6c90-8739-4319-b503-ecca086b3061
isreadyforlocalization: false
noindex: true
index: y
internal: n
snippet: y
---

# PDF Generator backup limitations{#pdf-generator-backup-limitations}

<!--
Comment Type: remark
Last Modified By:
Last Modified Date:
<p>Bug 1771172</p>
-->

The temporary directory that PDF Generator uses to convert files cannot be backed up. Even though the service will be restored properly, data can get lost because PDF Generator reviews and clears the contents of the temporary directory at set intervals. 
