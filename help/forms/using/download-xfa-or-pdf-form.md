---
title: Download an XFA or a PDF form template
seo-title: Download an XFA or a PDF form template
description: null
seo-description: You can export forms from the repository to the local system and migrate the downloaded forms to new repository.
uuid: c2954666-d4ac-4031-968e-e16553121a75
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: e5742e58-1558-4adc-8388-9005e6eb8acf
index: y
internal: n
snippet: y
---

# Download an XFA or a PDF form template{#download-an-xfa-or-a-pdf-form-template}

The download operation, as the name implies, lets you export forms from the repository to the local system. In combination with the upload operation, this operation helps you migrate your forms from one repository to another.

In AEM Forms, the download operation is supported for the following asset types:

* Form templates (XFA Forms)
* PDF forms
* Documents (flat PDF files)

AEM Forms supports download of these form types individually or in a folder containing one or more supported forms.  

Aside from these assets, you can download the `Resource` type of asset if it is present in a folder. This functionality is provided to enable you to download the resource referred to by an XFA form along with the form.

### Download one or more forms {#download-one-or-more-forms}

1. Log in to the AEM Forms user interface at `http://<server>:<port>/aem/forms.html`.  

1. Navigate to the location of the asset you want to download.  

1. Select the asset. Click the **[!UICONTROL Download]** ![](assets/Aem6Forms_download.png){width="16"} icon in the toolbar.

   >[!NOTE]
   >
   >You can select only one form for download. If you want to download multiple forms, you must download them as a folder.

1. In the dialog box that appears, click **[!UICONTROL Download]**.

   AEM Forms generates a ZIP file containing the selected file or the selected folder.

   If you're downloading a folder, the supported assets inside the folder are downloaded in their existing hierarchy.

   The ZIP file is saved to the `Downloads` folder on your system.

### Related considerations for the upload operation {#related-considerations-for-the-upload-operation}

* You can upload the ZIP file to any other location in the same repository or another repository
* The hierarchy of the assets in a folder is retained during the upload operation
* Any metadata changes made to the downloaded assets before download are reflected upon upload

>[!MORE_LIKE_THIS]
>
>* [Introduction to managing forms](../../forms/using/introduction-managing-forms.md)
