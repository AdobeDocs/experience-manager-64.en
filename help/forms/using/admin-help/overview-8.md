---
title: Overview of output service
seo-title: Overview of output service
description: Output lets you merge XML form data with a form design created in Designer to create a document output stream in various formats.
seo-description: Output lets you merge XML form data with a form design created in Designer to create a document output stream in various formats.
uuid: fe783924-de70-4869-92c1-f873c00ddb7a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e5afe0ea-a66c-493d-bc98-62e1dc1f381e
index: y
internal: n
snippet: y
---

# Overview of output service{#overview-of-output-service}

Output lets you merge XML form data with a form design created in Designer to create a document output stream in various formats. The output stream can be sent to a network printer, a local printer, or a disk file

You can use the Output page in administration console to administer the Output service. The settings you configure are used at run time when the equivalent settings were not specified through the AEM forms API. Configuration done through the AEM forms SDK overrides the settings configured using administration console.

For additional information about the Output service, see [Services Reference](http://www.adobe.com/go/learn_aemforms_services_61).

On the Output pages in administration console, you can perform several tasks:

* Specify character sets for internationalization. (See [Change the character set](../../../forms/using/admin-help/change-character-set.md#change-the-character-set).)
* Specify absolute and relative paths for URLs, URIs, XCIs, and file locations. (See [Specify file locations for Output](../../../forms/using/admin-help/specify-file-locations-output.md#specify-file-locations-for-output).)
* Configure cache sizes and policies. (See [Specifying the cache mode](../../../forms/using/admin-help/configuring-caching-output.md#specifying-the-cache-mode) and [Configuring cache settings](../../../forms/using/admin-help/configuring-caching-output.md#configuring-cache-settings).)
* Make fonts available on the application server. (See [Make fonts available](../../../forms/using/admin-help/make-fonts-available.md#make-fonts-available).)
* Specify fonts to embed. (See [Specify fonts to embed](../../../forms/using/admin-help/specify-fonts-embed.md#specify-fonts-to-embed).)
* Specify XCI configuration options. (See [Specify XCI configuration options](../../../forms/using/admin-help/specify-xci-configuration-options.md#specify-xci-configuration-options).)
* Specify security settings. (See [Specify security settings](../../../forms/using/admin-help/specify-security-settings.md#specify-security-settings).)

After you change the settings, click Save to apply them to Output. You do not need to restart the server for the changes to take effect, but you may need to restart the Output service when configuring cache settings. 
