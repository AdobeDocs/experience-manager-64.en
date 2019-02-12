---
title: PDF Generator backup limitations
seo-title: PDF Generator backup limitations
description: Learn about PDF Generator backup limitations.
seo-description: Learn about PDF Generator backup limitations.
uuid: f45723a2-e2e4-4f32-8ea3-af45e6262431
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 2cdb6f06-bd74-46b8-be0a-5830550a86a5
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
