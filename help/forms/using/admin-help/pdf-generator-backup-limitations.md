---
title: PDF Generator backup limitations
seo-title: PDF Generator backup limitations
description: Learn about PDF Generator backup limitations.
seo-description: Learn about PDF Generator backup limitations.
uuid: 0919c0d2-9dac-4d7f-8373-0ea2003ac2c5
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e770e157-06ae-4af3-8073-8bf34a1b8d32
noindex: true
index: y
internal: n
snippet: y
---

# PDF Generator backup limitations{#pdf-generator-backup-limitations}

The temporary directory that PDF Generator uses to convert files cannot be backed up. Even though the service will be restored properly, data can get lost because PDF Generator reviews and clears the contents of the temporary directory at set intervals. 
