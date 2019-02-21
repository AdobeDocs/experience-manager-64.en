---
title: Working with a Form
seo-title: Working with a Form
description: View and update the form associated with a task or Startpoint in the AEM Forms app
seo-description: View and update the form associated with a task or Startpoint in the AEM Forms app
uuid: 903338db-efaf-4ee3-b5c2-68c4094c7b59
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 9590cb6e-02df-4cb1-ac64-647a32356178
index: y
internal: n
snippet: y
---

# Working with a Form{#working-with-a-form}

If a form is enabled for syncing in the forms app, the form is downloaded and you can work with it directly.

The forms are downloaded on your app, and are available offline. For example, you are running a banking firm, and a customer fills an application on your site. The application is an adaptive form that accepts information from your customers, and stores it for review. The administrator reviews the form, and creates a verification form in AEM author instance. The admin enables syncing of the form with AEM Forms app. If the verification form is available in AEM Forms app, your field agent can use a mobile device to verify your customer's details. The mobile device syncs with the server, and the verification form is loaded in the app. Your field agent can visit your customer, verify the details, save data as draft, or submit the verification form. The form is synced with the server every time your app is online.

To sync your form in AEM Forms app:

1. In author instance, select a form, and click **View Properties**.  

1. In the properties page, click **Advanced.**
1. Under Advanced, enable option: **Sync with AEM Forms App, **and tap **Save**.

To sync multiple forms, in the author instance, select multiple forms in forms manager and tap **Sync with AEM Forms App**. When the form is published, the AEM Forms app can connect to the publish server and fetch the forms.

>[!NOTE]
>
>Supported forms:
>
>* Adaptive forms (without lazy loading)
>* Mobile forms
>
>Form level attachments are not supported in the adaptive forms fetched in the AEM Forms app synced with AEM Forms OSGi server. Users can attach files in a field, if the author has enabled field level attachments at the time of authoring the form.

**To open and update a form**

1. To open a form, tap the form in the home screen.
1. You can update the fields of the form, add attachments, save as draft, and submit it.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

<!--
<related-links>
<a href="../../forms/using/open-task.md">Opening a task</a>
<a href="../../forms/using/working-with-form.md">Working with a Form</a>
<a href="../../forms/using/add-attachments.md">Adding attachments</a>
<a href="../../forms/using/save-as-draft.md">Saving a task (Save as Draft)</a>
</related-links>
-->

