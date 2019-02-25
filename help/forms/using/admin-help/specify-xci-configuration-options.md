---
title: Specify XCI configuration options
seo-title: Specify XCI configuration options
description: Learn how to specify XCI configuration options.
seo-description: Learn how to specify XCI configuration options.
uuid: 34e17a77-2c86-4b78-9074-533de352df45
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: de085d2f-e265-48c0-99d0-68eccd4853e2
---

# Specify XCI configuration options{#specify-xci-configuration-options}

Output enables you to specify a custom XCI file that it uses for rendering. (See [Specify file locations for Output](../../../forms/using/admin-help/specify-file-locations-output.md#specify-file-locations-for-output).) By default, Output overrides some of the options specified in the XCI file, including the following:

* 
* 
* 
*

You can select options that cancel the override for the options listed above, in which case Output uses the values specified in the custom XCI file.

1. In administration console, click Services &gt; output.
1. Select or deselect the Use System Default XCI Options check box. When this option is selected, Output uses its default values for the packets, creator, producer, and compressObjectStream settings. When this option is deselected, Output uses the values specified in the custom XCI file.
1. Click Save.

