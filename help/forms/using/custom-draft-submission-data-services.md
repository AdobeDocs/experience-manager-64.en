---
title: Customizing Draft and Submission data services
seo-title: Customizing Draft and Submission data services
description: null
seo-description: AEM Forms, by default, stores draft and submitted adaptive forms in a default node on the Publish instance. However, you can configure the draft and submission data services of AEM Forms to customize the storage of draft and submitted adaptive forms.
uuid: eb1de20c-7225-47d0-a8cb-6453a992e42b
acrolinxdate: 2016-05-31T06 36 28.407-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: yellow
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/custom_draft_submission_data_services_admin_5e12de0b318c6865_1992_report.xml
acrolinxsentences: 12
acrolinxwords: 613
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
discoiquuid: ae28b0ca-01ae-4472-a1c3-22e84d992762
isreadyforlocalization: false
lastpublishqadate: 2015-06-12T04 25 39.272-0400
index: y
internal: n
snippet: y
---

# Customizing Draft and Submission data services{#customizing-draft-and-submission-data-services}

## Overview {#overview}

AEM Forms allows users to save an adaptive form as a draft. The draft functionality provides users with the option to maintain a work-in-progress form. A user can then complete and submit the form at any time from any device.

By default, AEM Forms stores the user data associated with the draft and submission on the Publish instance in the `/content/forms/fp` node.

However, AEM Forms portal components provides data services that allow you to customize the implementation of storing user data for drafts and submissions. For example, you can store the data in a data store currently implemented in your organization.

To customize the storage of user data, you need to implement the [Draft Data](../../forms/using/custom-draft-submission-data-services.md#main-pars-header) and [Submission Data](../../forms/using/custom-draft-submission-data-services.md#main-pars-header-1) services.

## Prerequisites {#prerequisites}

* Enable [Forms portal components](../../forms/using/enabling-forms-portal-components.md) 
* Create a [forms portal page](../../forms/using/creating-form-portal-page.md) 
* Enable [adaptive forms for forms portal](../../forms/using/draft-submission-component.md)
* Learn [implementation details of custom storage](../../forms/using/draft-submission-component.md#main-pars-header)

## Draft data service {#draft-data-service}

To customize the storage of user draft data, you need to provide implementation for all the methods of the `DraftAFDataService` interface.

A description of the methods and their arguments are provided in the following code sample of the interface:

```java
public interface DraftAFDataService {
 
 /**
  * Deletes the user data stored against the ID passed as the argument
  * 
  * @param draftDataID
  * @return status for the just occurred delete draft UserData operation 
  * @throws FormsPortalException
  */
 public Boolean deleteAFDraftUserData (String draftDataID) throws FormsPortalException;
 
 /**
  * Saves user data provided in the argument map
  * 
  * @param draftUserDataMap contains Form Data (key - "guideState"), Adaptive Form Name (Key - "guideName"), and Draft DataID (Key - "userDataID") in case of update
  * @return userData ID would be returned which needs to be saved in metadata node 
  * @throws FormsPortalException
  */
 public String saveAFUserData (Map<String, Object> draftUserDataMap) throws FormsPortalException;
 
 /**
  * Gets the user data stored against the ID passed as the argument
  * 
  * @param Draft DataID
  * @return guideState (which would then be populated in adaptive form to reload the draft) which is stored against draftDataID
  * @throws FormsPortalException
  */
 public byte[] getAFDraftUserData(String draftDataID) throws FormsPortalException;
 
 /**
  * Saves the attachments for current adaptive form instance 
  * 
  * @param attachmentsBytes would expect byte array of the attachment to be saved
  * @return id for the attachment just saved (so that it could be retrieved later)
  * @throws FormsPortalException
  */
 public String saveAttachments(byte[] attachmentBytes) throws FormsPortalException;
}
```

## Submission data service {#submission-data-service}

To customize the storage of user submission data, you need to provide implementation for all the methods of the `SubmittedAFDataService` interface.

A description of the methods and their arguments are provided in the following code sample of the interface:

```java
public interface SubmittedAFDataService {
 
 /**
  * Submits the user data passed in argument map
  * 
  * @param submittedAFUserdataMap contains Form Data (key - "guideState"), Adaptive Form Name (Key - "guideName"), and Draft DataID (Key - "userDataID")
  * @return userData ID is returned that needs to be saved in the metadata node
  * @throws FormsPortalException
  */
 public String submitAFUserData (Map<String, Object> submittedAFUserdataMap) throws FormsPortalException;
 
 /**
  * Gets the user data stored against the ID passed as argument
  * 
  * @param submitDataID
  * @return guideState which would be used to open DOR
  * @throws FormsPortalException
  */
 public byte[] getSubmittedAFUSerData(String submitDataID) throws FormsPortalException;
 
 /**
  * Deletes user data stored against the ID passed as argument
  * 
  * @param Submit DataID
  * @return status of the delete operation on Submitted User data
  * @throws FormsPortalException
  */
 
 public Boolean deleteSubmittedAFUserData(String submitDataID) throws FormsPortalException;
 
 /**
  * Submits the attachment bytes passed as argument
  * 
  * @param attachmentsBytes would expect byte array of the attachment to be saved
  * @return id for the attachment just saved (so that it could be retrieved later) 
  * @throws FormsPortalException
  */
 public String submitAttachments(Object attachmentBytes) throws FormsPortalException;

}

```

>[!MORE_LIKE_THIS]
>
>* [Drafts and submissions component](../../forms/using/draft-submission-component.md)
>* [Creating a custom toolbar action](../../forms/using/creating-custom-toolbar-action.md)
>* [Creating custom adaptive form themes](../../forms/using/creating-custom-adaptive-form-themes.md)
>* [Customizing form event tracking](../../forms/using/customizing-form-event-tracking.md)
