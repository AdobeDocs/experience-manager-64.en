---
title: Reusing adaptive forms
seo-title: Reusing adaptive forms
description: You can reuse an existing adaptive form to create new adaptive forms. 
seo-description: You can reuse an existing adaptive form to create new adaptive forms. 
uuid: beba9110-5ecb-4bb3-a2c8-f57368d40fe2
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 63376de4-b17a-42f8-a2ba-3a517d79da99
index: y
internal: n
snippet: y
---

# Reusing adaptive forms{#reusing-adaptive-forms}

## Introduction {#introduction}

If you want to use some of the properties of an existing adaptive form to generate a new one, you can simply use the copy-paste functionality. In addition, you can paste the new adaptive form at the desired folder path. All metadata properties are replicated and the XFA and XSDs for XFA- and XSD-based adaptive forms are also copied.

>[!NOTE]
>
>The status and the review details are not copied. For example, if your adaptive form is published and then if you copy it, the pasted adaptive form is in unpublished state. Similarly, if a copied asset is under review, the pasted asset is not under the same review.

<!--
Comment Type: draft

<note>
<p>To know more about how to start a review of a form, see <a href="../../forms/using/create-reviews-forms.md">Creating and managing reviews of forms</a></p>
</note>
-->

### Copy an adaptive form {#copy-an-adaptive-form}

Copy an adaptive form using either of the following approaches:

1. Click copy ![](assets/aem6forms_copy.png) icon from Quick actions.

   >[!NOTE]
   >
   >Quick actions are the action items that get displayed over a thumbnail on mouse hover.

1. Select the adaptive form. The selection process is different for different views.

   If you are in card view, go to selection mode by clicking the selection ![](assets/aem6forms_check-circle.png) icon and click all the adaptive forms that you want to copy.

   If you are in list view, click the check boxes of all adaptive forms to select them.

   >[!NOTE]
   >
   >All selected assets must be adaptive forms because copy-paste functionality is supported only for adaptive forms, and all assets that are selected must be present in the same folder.

   After selecting the assets, click the copy ![](assets/aem6forms_copy.png) icon present in the toolbar to copy the selected adaptive form.

### Paste an adaptive form {#paste-an-adaptive-form}

Clicking the copy action automatically exits the selection mode and makes the paste ![](assets/aem6forms_paste.png) icon visible. Now go to the desired folder path and click the paste ![](assets/aem6forms_paste.png) icon to paste the copied adaptive form.

If you are pasting in the same folder or another file with the same node name (with which it is stored in the CRX repository) exists in this target folder, 1 is appended to the suffix (for example, myaf becomes myaf1 and if myaf1 exists at the same location, myaf becomes myaf2. All other properties remain same as the original adaptive form.

After clicking the paste ![](assets/aem6forms_paste.png) icon, it will again become hidden. At one time, you can only paste once. To again create a copy of same asset, copy it again.

### Change contents of new adaptive form {#change-contents-of-new-adaptive-form}

The content of a pasted adaptive forms can be changed using the following approaches to make it different from the copied form:

1. You can change the metadata properties of the adaptive form for example, title and description. For more details about metadata properties and how they can be changed, see [Managing Form Metadata](../../forms/using/manage-form-metadata.md)
1. You can change the XFA/XSD used in adaptive forms. To know how these adaptive forms can be changed, see [Managing form metadata](../../forms/using/manage-form-metadata.md)
1. The pasted asset is different from the copied one. You can publish it as a new asset to make it available for end users. To know how to publish an asset, see [Publishing and unpublishing forms](../../forms/using/publishing-unpublishing-forms.md)

<!--
<related-links>
<a href="../../forms/using/creating-adaptive-form.md" target="_blank"> Creating an adaptive form</a>
</related-links>
-->

