---
title: Create new folders to categorize forms
seo-title: Create new folders to categorize forms
description: Use folders to organize your form templates, PDFs, resources, and adaptive forms.
seo-description: Use folders to organize your form templates, PDFs, resources, and adaptive forms.
uuid: ceeff597-5420-48b4-90fc-97647eea2263
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: b21fbb1d-28d9-4d4c-b49b-c3e40a3db29f
index: y
internal: n
snippet: y
---

# Create new folders to categorize forms{#create-new-folders-to-categorize-forms}

<!--
Comment Type: remark
Last Modified By: (svashish)
Last Modified Date: 2017-11-30T06:07:06.869-0500
<p><strong>General writing guidelines</strong></p>
<ul>
<li>Do not use the gerund form while writing article headings. For example, <em>"Create forms"</em> and not "Creating forms".</li>
<li>Section headings (H2 headings) in the gerund form are generally OK.<br /> </li>
<li>Use the second person to document features. Do not use the first person.</li>
<li>Do not include inline links. They distract readers from the task at hand. Include the "Recommended reads" towards the end of the article as a <strong>See also</strong> section.<br /> </li>
<li>Ensure that all dialog boxes have captions. This is required for accessibility purposes.</li>
<li>"Click the icon" instead of "Click on the icon"...</li>
</ul>
-->

You can organize your assets better using folders. Since AEM Forms supports several types of assets—form templates, PDFs, documents, resources, and adaptive forms, with various metadata—you can use folders to categorize your forms based on the desired criteria.

AEM Forms lets you change the title of a folder. The title is not the same as the name of the node under which the folder is stored in the repository. Rather, the title is maintained as metadata for the folder. If you change the title of a folder, the path of any asset present inside the folder is not affected.

## Create a folder {#create-a-folder}

<!--
Comment Type: remark
Last Modified By: (svashish)
Last Modified Date: 2017-11-30T06:07:06.916-0500
<p>Please add the article explaining how to upload the ZIP file to the See Also section below.<br /> </p>
-->

You can create a folder in AEM Forms in one of the following ways:

* Upload a ZIP file containing assets in the desired folder structure (See, [Getting XDP and PDF documents in AEM Forms](../../forms/using/get-xdp-pdf-documents-aem.md))  

* Create a new empty folder

1. Log in to the AEM Forms user interface at `http://<server>:<port>/aem/forms.html`.  
   ``
1. Navigate to the location under which you want to create a folder.  

1. Click the ![](assets/aem6forms_add.png) icon in the toolbar and then select **[!UICONTROL Create Folder]**.  

1. Enter the following details:

    * **Title:** Display name for the folder 
    * **Name:** *(Mandatory)* The node name under which you want to store the folder in the repository

   >[!NOTE]
   >
   >By default, the value of name field is automatically populated from the title. The name can only contain alphanumeric characters, or the hyphen (-) and underscore (_) special characters. Any other special characters entered in the title are automatically replaced with a hyphen and you are prompted to confirm the new name. You can choose to continue with suggested name or edit it further.

1. Click **[!UICONTROL Submit]****.**

   A new folder with the title you defined is displayed at the current location in the asset listing.

   If a folder exists with the name specified, the submission fails with an error. You can view the error message by hovering over the error ![](assets/aem6forms_error_alert.png) icon that appears beside the name field.

### Edit the folder title <br> {#edit-the-folder-title-br}

1. Select the folder whose title you want to edit.
1. Click the edit ![](assets/aem6forms_edit.png) icon in the toolbar.  

1. Enter the new title. The text field is prepopulated with the current value of folder title. You can change it to a new value.  

1. Click **[!UICONTROL Submit]****.**

>[!MORE_LIKE_THIS]
>
>* [Manage form metadata](../../forms/using/manage-form-metadata.md)
>* [Getting XDP and PDF documents in AEM Forms](../../forms/using/get-xdp-pdf-documents-aem.md)
