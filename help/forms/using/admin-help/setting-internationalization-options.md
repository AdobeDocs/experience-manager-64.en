---
title: Setting internationalization options
seo-title: Setting internationalization options
description: null
seo-description: Learn how to specify the locale used to render forms and how to specify the character set used to encode the output stream.
uuid: 213529ea-f2cf-438d-95c2-91f144117f6c
acrolinxdate: 2016-05-31T07 02 59.174-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/setting_internationalization_options_admin_5e12de0b318c6865_2364_report.xml
acrolinxsentences: 16
acrolinxwords: 203
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 514affba-8643-4101-a00c-6f1635393459
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Setting internationalization options{#setting-internationalization-options}

## Specify the locale used to render forms {#specify-the-locale-used-to-render-forms}

You can specify the locale used when rendering a PDF form. The fields on a PDF form use the specified locale to display data. For example, if the locale is set to German, the form uses German decimal separators for numeric values. The locale is also used to send validation messages to client devices, such as web browsers, as part of HTML transformations.

1. In administration console, click Services &gt; Forms.
1. Under Internationalization, in the Language list, select the locale used to render a form. The default value is English (United States).
1. Click Save.

## Specify the character set used to encode the output stream {#specify-the-character-set-used-to-encode-the-output-stream}

1. Under Internationalization, in the Character Set list, select a character set. This setting is dependent on the API used, either renderHTMLForm or renderPDFForm. To specify a character set other than those listed, select Custom and specify an encoding value in the box that is displayed.

   For HTML transformations, AEM forms supports character encoding values defined by the `java.nio.charset` package. If sFormPreference is PDFForm, only specific character sets are supported. The character set must be a valid canonical name. The default value is ISO-8859-1.

1. Click Save.

