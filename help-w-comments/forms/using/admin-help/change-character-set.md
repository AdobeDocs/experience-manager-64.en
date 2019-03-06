---
title: Change the character set
seo-title: Change the character set
description: You can specify the character set used to encode the output stream. Learn how you can change the character set.
seo-description: You can specify the character set used to encode the output stream. Learn how you can change the character set.
uuid: 86cd8e04-83a4-4369-a981-7f8b9d499f2b
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 6a67e1f7-80d6-429b-96fc-bb299f9b1015
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

