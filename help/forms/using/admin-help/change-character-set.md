---
title: Change the character set
seo-title: Change the character set
description: null
seo-description: You can specify the character set used to encode the output stream. Learn how you can change the character set.
uuid: f85a6a64-5ae1-4d9f-b328-47d74c10625a
acrolinxdate: 2016-05-31T06 53 15.448-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/change_character_set_admin_5e12de0b318c6865_2265_report.xml
acrolinxsentences: 9
acrolinxwords: 117
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: ae8a501a-6757-4e5b-852e-a557d76a239e
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Change the character set{#change-the-character-set}

You can specify the character set used to encode the output stream.

1. In administration console, click Services &gt; output.
1. Under Internationalization, in the Character Set list, select a character set. This setting is dependent on the `TransformationFormat` and `PrintFormat` specified through the API. To specify a character set other than those listed, select Custom and specify an encoding value in the box that is displayed.

   If `TransformationFormat` is PDF and PDF/A or `PrintFormat` is PCL, PostScript, Zebra label, IPL, DPL, TPCL, GenericColorPCL, or GenericPSLevel3, only specific character sets are supported.

   The character set must be a valid canonical name. The default value is ISO-8859-1.

1. Click Save.

