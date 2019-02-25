---
title: Specifying XCI configuration options
seo-title: Specifying XCI configuration options
description: Learn how to specify XCI configuration options.
seo-description: Learn how to specify XCI configuration options.
uuid: e93281a3-0eb3-4814-baad-6f56b5455a5c
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 729b3dcf-9958-4327-a096-681283400d5c
---

# Specifying XCI configuration options{#specifying-xci-configuration-options}

Forms enables you to specify a custom XCI file that it will use for rendering. (See [Configuring locations for Forms](../../../forms/using/admin-help/configuring-locations-forms.md#configuring-locations-for-forms).) By default, Forms overrides some of the options specified in the XCI file, including the following:

* 
* 
* 
*

You can select options that cancel the override for the options listed above, in which case Forms will use the values specified in the custom XCI file.

1. In administration console, click Services &gt; Forms.
1. Select or deselect the Use System Default XCI Options check box. When this option is selected, Forms uses its default values for the packets, creator, producer, and compressObjectStream settings. When this option is deselected, Forms uses the values specified in the custom XCI file.
1. Click Save.

