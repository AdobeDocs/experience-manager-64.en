---
title: PDF Generator backup limitations
seo-title: PDF Generator backup limitations
description: Learn about PDF Generator backup limitations.
seo-description: Learn about PDF Generator backup limitations.
uuid: b232a9f1-c855-4f8e-8c7f-680af91a65b1
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 333a3768-f3d7-480e-af8d-2df636336052
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
