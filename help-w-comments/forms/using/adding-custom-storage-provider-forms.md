---
title: Custom storage for drafts and submissions component
seo-title: Custom storage for drafts and submissions component
description: See how to customize the storage of user data for drafts and submissions.
seo-description: See how to customize the storage of user data for drafts and submissions.
uuid: c227b5a4-ed1f-4985-9a0e-93b3ce20755c
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 30db602a-ecc7-4844-90c8-3a748a97cb61
index: y
internal: n
snippet: y
---

# Custom storage for drafts and submissions component{#custom-storage-for-drafts-and-submissions-component}

## Overview {#overview}

AEM Forms allows you to save a form as a draft. The draft functionality lets you maintain a work-in-progress form, which you can complete and submit later from any device.

By default, AEM Forms stores the user data associated with the draft and submission of a form in the `/content/forms/fp` node on the Publish instance. In addition, the AEM Forms portal components provide data services, which you can use to customize the implementation of storing user data for drafts and submissions. For example, you can store user data in a data store.

## Prerequisites  {#prerequisites}

* Enable F [orms portal components](../../forms/using/enabling-forms-portal-components.md) 
* Create a [forms portal page](../../forms/using/creating-form-portal-page.md) 
* Enable [adaptive forms for forms portal](../../forms/using/draft-submission-component.md)
* Learn [implementation details of custom storage](../../forms/using/draft-submission-component.md#customizing-the-storage)

## Draft data service {#draft-data-service}

To customize the storage of user data for drafts, you need to implement all the methods of the `DraftDataService` interface. The following sample code describes the methods and arguments.

```java
/**
 * DraftDataService service will get/delete/save user data (attachments and form data) filled with a draft instance of Form  
 */

public interface DraftDataService {
    
    /**
     * To save/modify user data for this userDataID, it will be null in case of creation 
     * @param draftDataID: unique identifier associated with the form data
     * @param formName: name of the form whose draft is being saved
     * @param formData: user data associated with this draft
     * @return userdataID corresponding to which user data has been stored and which can be used later to retrieve this user data
     * @throws FormsPortalException
     */
    public String saveData (String draftDataID, String formName, String formData) throws FormsPortalException;
     
    /**
     * Returns the user data stored against the ID passed as the argument
     * @param userDataID: unique data id for user data associated with a draft
     * @return user data associated with this data ID
     * @throws FormsPortalException
     */
     
    public byte[] getData (String userDataID) throws FormsPortalException;
     
    /**
     * To delete data associated with this draft
     * @param userDataID: unique data id for data associated with a draft
     * @return status of delete operation on data associated with this draft 
     * @throws FormsPortalException
     */
     
    public boolean deleteData (String userDataID) throws FormsPortalException;
     
    /**
     * Saves the attachment for current form instance
     * @param attachmentsBytes: byte array of the attachment to be saved
     * @return unique id (attachmentID) for the attachment just saved (so that it could be retrieved later)
     * @throws FormsPortalException
     */
    public String saveAttachment (byte[] attachmentBytes) throws FormsPortalException;
     
    /**
     * To delete an attachment
     * @param attachmentID: unique id for this attachment
     * @return status of delete operation performed on attachment corresponding to this attachment ID
     * @throws FormsPortalException
     */
    public boolean deleteAttachment (String attachmentID) throws FormsPortalException;
     
    /**
     * To get attachment bytes
     * @param attachmentID: unique id for this attachment
     * @return data corresponding to this attachmentID
     * @throws FormsPortalException
     */
    public byte[] getAttachment (String attachmentID) throws FormsPortalException;
}
```

## Submission data service {#submission-data-service}

To customize the storage of user data for submissions, you need to implement all the methods of the `SubmitDataService` interface. The following sample code describes the methods and arguments.

```java
/**
 * SubmitDataService service will get/delete/submit user data (attachments and form data) filled with a submission of Form  
 */
public interface SubmitDataService {
    
    /**
     * Submits the user data passed in argument map
     * @param userDataID, unique identifier associated with this user data
     * @param formName, name of the form whose draft is being submitted
     * @param formData, user data associated with this submission
     * @return userdataID, corresponding to which the user data has been stored and which can be used later to retrieve this data
     * @throws FormsPortalException
     */
    public String saveData (String userDataID, String formName, String formData) throws FormsPortalException;

    /**
     * Submits the user data provided as byte array
     * @param id
     * @param data
     * @return id corresponding to saved data
     * @throws FormsPortalException
     */
    public String saveData (String id, byte[] data) throws FormsPortalException;
    
    /** Submits the user data provided as byte array asynchronously for the user name provided in the options map 
     * @param data data to be saved in bytes
     * @param options map containing options that affect this save
     * @return id of the saved data instance
     */
    public String saveDataAsynchronusly(byte[] data, Map<String, Object> options) throws FormsPortalException; 
     
    /**
     * Gets the user data stored against the ID passed as argument
     * @param userDataID: unique id associated with this user data for this submission
     * @return user data associated with this submission
     * @throws FormsPortalException
     */
    public byte[] getData(String userDataID) throws FormsPortalException;
     
    /**
     * Deletes user data stored against the userDataID
     * @param userDataID: unique id associated with this user data for this submission
     * @return status of the delete operation on this submission
     * @throws FormsPortalException
     */
     
    public boolean deleteData(String userDataID) throws FormsPortalException;

    /**
     * Submits the attachment bytes passed as argument
     * @param attachmentsBytes: would expect byte array of the attachment for this submission
     * @return attachmentID for the attachment just saved (so that it could be retrieved later) 
     * @throws FormsPortalException
     */
    public String saveAttachment(byte[] attachmentBytes) throws FormsPortalException;
    
    /** Submits the attachment bytes passed as argument asynchronously for the user id provided in options map.
     * @param attachmentBytes would expect byte array of the attachment for this submission
     * @param options map containing options that affect this save
     * @return attachmentID for the attachment just saved (so that it could be retrieved later)
     * @throws FormsPortalException
     */
    public String saveAttachmentAsynchronously(byte[] attachmentBytes, Map<String, Object> options) throws FormsPortalException;
 
    /**
     * To delete an attachment
     * @param attachmentID: Unique id for this attachment
     * @return status of delete operation performed on attachment corresponding to this attachment ID
     * @throws FormsPortalException
     */
    public boolean deleteAttachment (String attachmentID) throws FormsPortalException;
     
    /**
     * To get attachment bytes
     * @param attachmentID: unique id for this attachment
     * @return data corresponding to this attachmentID
     * @throws FormsPortalException
     */
    public byte[] getAttachment (String attachmentID) throws FormsPortalException;
}
```

Forms portal uses Universally unique identifier (UUID) concept to generate a unique ID for every draft and submitted form. You can also generate a unique ID of your own. You can implement the interface FPKeyGeneratorService, override its methods, and develop a custom logic to generate a custom unique ID for every draft and submitted form. Also, set service rank of custom ID generation implementation higher than 0. It ensures that the custom implementation is used instead of the default implementation.

```java
public interface FPKeyGeneratorService {
    /**
     * returns a unique id for draft and submission
     *
     * @param none
     * @return unique id in string format as per the implementation
     * @throws FormsPortalException
     */
    public String getUniqueId() throws FormsPortalException;
}
```

You can use the below annotation to increase the service ranking for custom ID generated with above code:

`@Properties(value = { @Property(name = "service.ranking", intValue = 15) } )`

To use the above annotation, imports the following to your project:

```
import org.apache.felix.scr.annotations.Properties;
 import org.apache.felix.scr.annotations.Property;
```

<!--
<related-links>
<a href="../../forms/using/configuring-draft-submission-storage.md" target="_blank">Configuring storage services for drafts and submissions</a>
<a href="../../forms/using/draft-submission-component.md" target="_blank">Drafts and Submissions components</a>
<a href="../../forms/using/creating-form-portal-page.md" target="_blank">Creating a forms portal page</a>
</related-links>
-->

