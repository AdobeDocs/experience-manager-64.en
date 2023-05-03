---
title: Adding custom action on form lister items
seo-title: Adding custom action on form lister items
description: Form developers can add more actions to the listing of forms on the forms portal page. By default, the form listing allows you to access the form, fill it, and submit it.
seo-description: Form developers can add more actions to the listing of forms on the forms portal page. By default, the form listing allows you to access the form, fill it, and submit it.
uuid: 02c64f7d-f726-4a5b-a303-ec96934e9c01
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
discoiquuid: 0e0a9b6b-fd2f-4cec-b233-500c940ee4d5
exl-id: d8f60be3-474a-4dd1-aaa5-7b6a97e1a9bd
---
# Adding custom action on form lister items {#adding-custom-action-on-form-lister-items}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

In AEM Forms, you can create a portal page listing the available forms. By default, you can search and list forms on a portal page. You can open forms for filling and submit your information. Only rendering actions are provided out of the box for forms listed on a portal page. To know more about the available actions on a portal page, see [Creating a forms portal page](/help/forms/using/creating-form-portal-page.md).

You can add other options to the portal page. These options or actions can be customized by customizing the template of forms portal.

This article showcases how to create a button to send the link of a form, directly from a forms portal page. This customization requires updating the template for Search & Lister component.

The required code to add the action to the template is available below. The `onclick` attribute in the code snippet has a script to send a link of a form via email.

```mxml
<div class="__FP_boxes-container __FP_single-color">
    <div class="boxes __FP_boxes __FP_single-color" data-repeatable="true">
  <div class="__FP_boxes-thumbnail">
            <img src ="${contextPath}${path}/jcr:content/renditions/cq5dam.thumbnail.319.319.png">
        </div>
        <h3 class="__FP_single-color" title="${name}" tabindex="0">${name}</h3>
        <p>${description}</p>
        <div class="boxes-icon-cont __FP_boxes-icon-cont">
            <div class="op-dow">
                <a href="${formUrl}" target="_blank" class="__FP_button ${htmlStyle}" title="${config-htmlLinkText}">Apply</a>
                <a class="__FP_button" title="Email a friend" href="#" onclick="javascript:window.location=&apos;mailto:?subject=Interesting information&body=I thought you might find {name} form helpful :  &apos;+window.location.protocol+window.location.host+&apos;${formUrl}&apos; ;">Email</a>
                <a href="${pdfUrl}" class="__FP_button ${pdfStyle}" title="${config-pdfLinkText}">Download</a>
            </div>
        </div>
    </div>
</div>
```

You can add similar actions in your custom template. To define a JavaScript function, add the function on a page-level script and link it with the requisite HTML element. In the above example, the `onclick` expression is the linked function.

After making the edits to the template, the sample portal page contains a button to send the link of the form via email, as shown below.

![email](assets/email.png)
