---
title: PDF Generator backup limitations
seo-title: PDF Generator backup limitations
description: Learn about PDF Generator backup limitations.
seo-description: Learn about PDF Generator backup limitations.
uuid: 6c198d5c-61b0-45e5-8842-7fe7a93b1a65
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 793dd74c-aeb3-4ef4-8b2b-59b0cfe8150c
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
