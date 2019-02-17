---
title: Saving an HTML5 form as a draft
seo-title: Saving an HTML5 form as a draft
description: Save an HTML5 form as a draft and resume filling the form at a later stage.
seo-description: Save an HTML5 form as a draft and resume filling the form at a later stage.
uuid: 9f62b234-dd96-427f-a432-40c676f78e88
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: d57f4786-9d7a-4b93-acc2-cb16b4facd94
index: y
internal: n
snippet: y
---

# Saving an HTML5 form as a draft{#saving-an-html-form-as-a-draft}

You can save an HTML5 form as a draft and resume filling the form at a later stage. Forms Portal allows any user to save and restore an HTML5 form. To enable the Save as Draft functionality, add the following configurations to the profile node:

### Custom Profile to allow Save as Draft feature {#custom-profile-to-allow-save-as-draft-feature}

Out of the box, AEM Forms provide a **Save as Draft **profile. You can render a form with the Save as Draft profile to enable draft functionality for an HTML5 form. You can specify HTML render profile for a form in [Forms Manager](../../forms/using/introduction-managing-forms.md).

To enable Save as Draft functionality for your existing [custom profile](../../forms/using/custom-profile.md), add the following properties to your custom profile node: 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Property Name</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Value</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td>mfAllowFPDraft</td> 
   <td>String</td> 
   <td>true</td> 
   <td><p>Enables save as draft feature</p> <p>for this profile.</p> </td> 
  </tr> 
  <tr> 
   <td>mfAllowAttachments</td> 
   <td>String</td> 
   <td>true</td> 
   <td><p>Allows uploading of attachments</p> <p>with this profile.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Drafts storage and listing {#drafts-storage-and-listing}

After enabling Save as Draft functionality for a form; when the form is saved, it is listed in the [Drafts and Submission component](../../forms/using/draft-submission-component.md). You can retrieve and start filling the saved form form the Draft and Submission component.

To enable forms listing for the Draft and Submission component, add the following property to the profile node: 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Property Name</strong></td> 
   <td><strong>Type</strong></td> 
   <td><strong>Value</strong></td> 
   <td><strong>Description</strong></td> 
  </tr> 
  <tr> 
   <td>fp.enablePortalSubmit</td> 
   <td>String</td> 
   <td>true</td> 
   <td>To enable drafts and forms to get listed in<br /> Forms Portal Drafts &amp; Submissions component after submission</td> 
  </tr> 
 </tbody> 
</table>

By default, AEM Forms stores the user data associated with the draft and submission of a form in the /content/forms/fp node on the Publish instance. You can add your custom storage provider, for details see [Custom storage for Drafts and Submissions component](../../forms/using/adding-custom-storage-provider-forms.md).

>[!MORE_LIKE_THIS]
>
>* [Drafts and Submissions components](../../forms/using/draft-submission-component.md)
>* [Creating a forms portal page](../../forms/using/creating-form-portal-page.md)
>* [Custom storage for drafts and submissions component](../../forms/using/adding-custom-storage-provider-forms.md)
