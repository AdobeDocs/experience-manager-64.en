---
title: Deleting forms and related resources
seo-title: Deleting forms and related resources
description: How to delete a form or an asset in AEM Forms and the impact on referenced and referring assets and XFA forms.
seo-description: How to delete a form or an asset in AEM Forms and the impact on referenced and referring assets and XFA forms.
uuid: 35e62fd7-ea2b-447a-8097-77f83b20a242
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: 75bc75d5-2923-4278-905b-0b39c73b44a2
index: y
internal: n
snippet: y
---

# Deleting forms and related resources{#deleting-forms-and-related-resources}

You can delete the forms and assets to remove these assets from the repository. Delete operation works on all asset types and folders.

If you delete an asset from the Author instance, the asset is also deleted from the Publish instance. AEM Forms server consists of Author and Publish instances. The Author instance is for creating and managing forms assets and resources. The Publish instance contains the published forms assets and related resources that are available for end users.

## How to delete a form {#how-to-delete-a-form}

1. Log in to the AEM Forms user interface, by accessing `http://[hostname]:[portport]/aem/forms.html.`
1. Navigate to and select the form you want to delete. Click Delete ![](assets/aem6forms_delete2.png) from the toolbar and confirm the delete operation.

   >[!NOTE]
   >
   >Only one form can be deleted at a time. Delete multiple forms either individually or delete the parent folder.

1. Before you delete an asset, AEM Forms checks for references and requests an explicit confirmation. Click Force Delete if you want to delete the asset irrespective of the relationship status.

   >[!NOTE]
   >
   >Deleting an asset that is referred by other assets can cause functional issues.

   >[!NOTE]
   >
   >If the selected asset is a folder and it contains such an asset in its hierarchy, delete other assets either individually or delete the entire folder.

## Impact of deleting a referenced XFA form {#impact-of-deleting-a-referenced-xfa-form}

In AEM Forms, an XFA form template can be referred by an adaptive form or another XFA form template. Also, a template can refer to a resource or another XFA template.

It is not advisable to delete an XFA form that is being referred by an adaptive form, as it can corrupt the adaptive form. When an adaptive form refers to an XFA form, their fields are bound. After XFA deletion, the adaptive form cannot synchronize its fields with the XFA fields and displays an error message for such fields. To know more about the impact of referenced XFA deletion and about dirty AFs, see [Updating referenced XFA forms](../../forms/using/get-xdp-pdf-documents-aem.md#p-updating-referenced-xfa-forms-p).

To delete such an XFA form, update the adaptive form and remove the bindings with the XFA fields.
