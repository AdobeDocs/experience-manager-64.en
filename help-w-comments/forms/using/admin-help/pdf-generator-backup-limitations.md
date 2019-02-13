---
title: PDF Generator backup limitations
seo-title: PDF Generator backup limitations
description: Learn about PDF Generator backup limitations.
seo-description: Learn about PDF Generator backup limitations.
uuid: 04324d26-d811-40ea-bd99-bd9571742131
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 7337a0a9-106e-42d3-93c5-0b0df5ef24fc
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
