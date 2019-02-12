---
title: Specifying fonts to embed
seo-title: Specifying fonts to embed
description: Learn how to specify fonts to embed.
seo-description: Learn how to specify fonts to embed.
uuid: 754f5f46-4b88-4216-ab15-3bc16767aa95
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: eb1708d0-231f-4b96-b846-d0958a887bf4
index: y
internal: n
snippet: y
---

# Specifying fonts to embed{#specifying-fonts-to-embed}

You can specify which fonts are always embedded or never embedded with the forms that the Forms service generates. Embedding fonts increases the file size of the forms. Embed unusual fonts that users rarely have on their systems. Do not embed common fonts that they typically have installed.

>[!NOTE]
>
>If you have specified a custom XCI file for Forms, the embed font option in the XCI file overrides these settings. (See [Configuring locations for Forms](../../../forms/using/admin-help/configuring-locations-forms.md#configuring-locations-for-forms).)

1. In administration console, click Services &gt; Forms.
1. Under Font Embedding Settings, in the Always Embed Fonts box, type the names of the fonts to embed with the forms, separated by commas. The fonts that you specify are only embedded in the generated form if they are used in the form. This setting is ignored if the embed font option has been turned on in the XCI file passed to the service because in that case, all fonts used in the PDF are always embedded.
1. In the Never Embed Fonts box, type the names of the fonts not to embed with the forms, separated by commas. The fonts that you specify are not embedded in the PDF, even if they are used in the generated PDF. This setting is ignored if the embed font option has been turned off in the XCI file passed to the service because in that case, none of the fonts used in the PDF are embedded.
1. Click Save.

