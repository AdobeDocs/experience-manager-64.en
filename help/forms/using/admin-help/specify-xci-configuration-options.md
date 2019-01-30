---
title: Specify XCI configuration options
seo-title: Specify XCI configuration options
description: null
seo-description: Learn how to specify XCI configuration options.
uuid: 664a65aa-a196-4484-bd78-a1d1dbd4392e
acrolinxdate: 2016-05-31T07 03 07.006-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/specify_xci_configuration_options_admin_5e12de0b318c6865_2370_report.xml
acrolinxsentences: 8
acrolinxwords: 130
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: c9aa6d89-c04e-4ebf-8dca-e7829c370ba7
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Specify XCI configuration options{#specify-xci-configuration-options}

Output enables you to specify a custom XCI file that it uses for rendering. (See [Specify file locations for Output](../../../forms/using/admin-help/specify-file-locations-output.md#specify-file-locations-for-output).) By default, Output overrides some of the options specified in the XCI file, including the following:

* `config/present/xdp/packets`
* `config/present/pdf/creator`
* `config/present/pdf/producer`
* `config/present/pdf/compression/compressObjectStream`

You can select options that cancel the override for the options listed above, in which case Output uses the values specified in the custom XCI file.

1. In administration console, click Services &gt; output.
1. Select or deselect the Use System Default XCI Options check box. When this option is selected, Output uses its default values for the packets, creator, producer, and compressObjectStream settings. When this option is deselected, Output uses the values specified in the custom XCI file.
1. Click Save.

