---
title: Specifying XCI configuration options
seo-title: Specifying XCI configuration options
description: null
seo-description: Learn how to specify XCI configuration options.
uuid: 2fa82c7c-fbf7-402c-9d8f-eb9a621dd3d3
acrolinxdate: 2016-05-31T07 03 10.360-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/specifying_xci_configuration_options_admin_5e12de0b318c6865_2373_report.xml
acrolinxsentences: 8
acrolinxwords: 131
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 27f80656-dbfd-45b6-8596-eb4319068dfc
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Specifying XCI configuration options{#specifying-xci-configuration-options}

Forms enables you to specify a custom XCI file that it will use for rendering. (See [Configuring locations for Forms](../../../forms/using/admin-help/configuring-locations-forms.md#configuring-locations-for-forms).) By default, Forms overrides some of the options specified in the XCI file, including the following:

* `config/present/xdp/packets`
* `config/present/pdf/creator`
* `config/present/pdf/producer`
* `config/present/pdf/compression/compressObjectStream`

You can select options that cancel the override for the options listed above, in which case Forms will use the values specified in the custom XCI file.

1. In administration console, click Services &gt; Forms.
1. Select or deselect the Use System Default XCI Options check box. When this option is selected, Forms uses its default values for the packets, creator, producer, and compressObjectStream settings. When this option is deselected, Forms uses the values specified in the custom XCI file.
1. Click Save.

