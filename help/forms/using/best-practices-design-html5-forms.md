---
title: DO NOT PUBLISH - Best practices for designing HTML5 forms
seo-title: DO NOT PUBLISH - Best practices for designing HTML5 forms
description: null
seo-description: Guidelines for form developers to ensure that the behavior and appearance of HTML5 forms and XFA-based PDF is consistent.
page-status-flag: de-activated
uuid: 4332a1d1-8a6c-425b-a436-fdb15b1142cc
acrolinxdate: 2016-05-31T06 46 58.343-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: yellow
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/best_practices_design_html5_forms_admin_5e12de0b318c6865_2099_report.xml
acrolinxsentences: 24
acrolinxwords: 382
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: cc80e31d-b513-4a6b-80c0-33931d8d515d
firstpublishqadate: 2013-03-14T10 48 47.898-0400
lastpublishqadate: 2015-06-12T04 29 42.091-0400
preview: true
publishqadate: 2015-06-12T04 29 42.091-0400
publishqaurl: https //helpx-preview.corp.adobe.com/content/help/en/aem-forms/6-1/html5-forms/best-practices-design-html5-forms.html
unpublishexternaldate: 2016-11-25T01 17 07.060-0500
index: y
internal: n
snippet: y
---

# DO NOT PUBLISH - Best practices for designing HTML5 forms{#do-not-publish-best-practices-for-designing-html-forms}

This article lists some of the best practices for enabling a form template for HTML5 renditions. By following these guidelines, form developers can ensure that the behavior and appearance of HTML5 forms and XFA-based PDF is consistent.

### Layout {#layout}

1. In new forms, add the non-interactive (Draw) elements before the interactive (Fields) elements. Add the elements in Hierarchy (Dom Order) if there is an overlap between them. Similarly, between overlapping Draw Text and other Draw elements (like Rectangle, Circle), put in Text after Rectangle so that it is visible. Avoid any overlap between Draw and Field.
1. HTML5 rendition of Form Template does not embed any fonts. Avoid using fonts that you do not expect on your client computers or you risk a not so optimum rendition on the client devices.
1. For Repeatable Subforms, mark the **initial count** as 1 or more. If you require zero initial instances, remove or hide the initial instance in form ready or initialize the script based on data.
1. If you are targeting the same form for both PDF and HTML, make sure that you protect the Acrobat-specific JavaScript by checking the environment type. Also ensure that you write equivalent scripts for the browser environment.
1. If you have a **hidden** subform with a complex hierarchy that is split across pages, make the form visible at design time. Hide the form in the initialize script based on your logic.

### Scripting {#scripting}

HTML5 forms contain a client-side XFA scripting library that supports form logic execution in both the scripting languages that the Adobe XFA Implementation supports: JavaScript and FormCalc. This library includes implementation for most of the commonly used APIs on the **client side**. The list of supported APIs and Events can be found [here](../../forms/using/scripting-support.md). If you need APIs that are not implemented yet, you can mark your script to **run at server. **HTML5 forms also support **Web Service** invocation from the client. The service runs on the server.

HTML5 forms and PDF forms support different set of features. For the complete list of features, see [Feature differentiation between HTML5 forms and PDF Forms.](../../forms/using/feature-differentiation-html5-forms-pdf-forms.md)

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

>[!MORE_LIKE_THIS]
>
>* [Best practices to design a Mobile form](../../forms/using/best-practices-design-html5-forms.md)
>* [Previewing your XDP form in HTML](../../forms/using/preview-xdp-forms-html.md)
>* [Using Scribble Signature](../../forms/using/scribble-signature.md)
>* [Rendering Form Template](../../forms/using/rendering-form-template.md)
>* [Designing form templates](../../forms/using/designing-form-template.md)
