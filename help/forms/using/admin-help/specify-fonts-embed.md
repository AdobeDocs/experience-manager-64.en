---
title: Specify fonts to embed
seo-title: Specify fonts to embed
description: null
seo-description: Learn how to specify fonts to embed.
uuid: be80be6e-a422-4a76-ac06-2123663a0498
acrolinxdate: 2016-05-31T07 03 05.048-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: yellow
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/specify_fonts_embed_admin_5e12de0b318c6865_2368_report.xml
acrolinxsentences: 15
acrolinxwords: 248
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 182f0f40-26fb-4c73-8163-be5432e370ac
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Specify fonts to embed{#specify-fonts-to-embed}

You can specify which fonts are always embedded or never embedded with the forms used by Output. Embedding fonts increases the file size of the forms. Embed unusual fonts that users are not likely to have on their systems, and do not embed common fonts that they will have installed.

>[!NOTE]
>
>If you have specified a custom XCI file for Output, the embed font option in the XCI file overrides these settings. (See [Specify file locations for Output](../../../forms/using/admin-help/specify-file-locations-output.md#specify-file-locations-for-output).)

1. In administration console, click Services &gt; output.
1. Under Font Embedding Settings, in the Always Embed Fonts box, type the names of the fonts to embed with the forms, separated by commas. The fonts that you specify are only embedded in the generated form if they are used in the form. This setting is ignored if the embed font option has been turned on in the XCI file passed to the service. In that case, all fonts used in the PDF are always embedded.
1. In the Never Embed Fonts box, type the names of the fonts not to embed with the forms, separated by commas. The fonts that you specify are not embedded in the PDF, even if they are used in the generated PDF. This setting is ignored if the embed font option has been turned off in the XCI file passed to the service. In that case, none of the fonts used in the PDF are embedded.
1. Click Save.

