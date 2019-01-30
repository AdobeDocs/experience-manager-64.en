---
title: Creating and managing reviews for assets in forms
seo-title: Creating and managing reviews for assets in forms
description: null
seo-description: A Review is a mechanism that allows one or more reviewers to comment on an asset that is available in a form. 
uuid: a397b954-f084-4e9d-99fc-ad32aeb47f4f
acrolinxdate: 2016-05-31T06 35 15.010-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: yellow
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/create_reviews_forms_admin_5e12de0b318c6865_1981_report.xml
acrolinxsentences: 51
acrolinxwords: 691
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: e1f594ee-16dc-4ca6-9311-c965cc1ad6f6
isreadyforlocalization: false
lastpublishqadate: 2015-06-12T04 25 36.402-0400
index: y
internal: n
snippet: y
---

# Creating and managing reviews for assets in forms{#creating-and-managing-reviews-for-assets-in-forms}

<!--
Comment Type: remark
Last Modified By: (sakarora)
Last Modified Date: 2017-11-30T06:06:57.649-0500
<p>CHANGE THE URL OF THIS ARTICLE BEFORE LOC HO.</p>
-->

## Review {#review}

A Review is a mechanism that allows one or more reviewers to comment on an asset that is available in a form.

## Setting up a review {#setting-up-a-review}

1. Navigate to the Forms tab and select a form.
1. If the asset does not have a review in progress, a Start Review  ![](assets/Aem6Forms_review_chat_comment.png){width="16"} icon appears in the Action bar. Click the Start Review  ![](assets/Aem6Forms_review_chat_comment.png){width="16"}

   icon.
1. Enter the following information:

    * Review name: Mandatory, can contain alphanumeric characters, hyphen, or underscore.
    * Review description: Optional, description of the purpose / content for review.
    * Review deadline: Optional, the date on which the review ends. When past the deadline the task appears as 'Overdue'.
    * Reviewers: A minimum of one is mandatory. Use the combo-box to add reviewers. Typing a name lists all matching names; select a name and click Add.

1. Fill in all the remaining details, and then click Start.

### Actions that occur when a review is set up {#actions-that-occur-when-a-review-is-set-up}

This section describes what happens when a review is created or set up.

1. A new review task is created and assigned to the initiator of the review. 
1. All reviewers are assigned a review task. The task appears in their Notifications section. A reviewer can click a notification, or go to the Inbox to view the task. A reviewer can click to open the review task, to view the form, and start adding comments.

   ![Reviewer Notification Alert](assets/noti.png)

1. The comment box is available to the initiator and reviewers of the asset. Others can view the comments, but cannot write comments.

## Managing a review {#managing-a-review}

>[!NOTE]
>
>Only reviews that are in progress can be modified. Reviews that are complete cannot be modified.

1. Navigate to the Forms tab and select a form.  

1. If an asset has a review in progress and you are the initiator of the review, a Manage Review  ![](assets/Aem6Forms_review_chat_comment.png){width="16"}

   icons appears in the Action bar. Only review initiator can manage (update/end) the review.

   Click the Manage Review  ![](assets/Aem6Forms_review_chat_comment.png){width="16"}

   icon.

   For user other than initiator the Manage Review icon is disabled. 

1. You get a screen that displays information:

    * **Review name**: Cannot be edited.  
    
    * **Review description**: Available for editing.  
    
    * **Review deadline**: Available for editing. One can modify the deadline to any date and time beyond the current date and time.  
    
    * **Reviewers**: Available for editing. You can add or remove reviewers. If a task is overdue, you can add reviewers only after extending the deadline beyond the current date.

1. Edit the necessary fields, and then click Update.

   ![Review updated state in Task Manager](assets/tskmgr.png)

1. To end the review, click End.

### Actions that occur when a review is modified {#actions-that-occur-when-a-review-is-modified}

This section describes, what happens on Review end / modification:

1. If the Review description is modified, the corresponding task of reviewers and the initiator is updated.
1. If the Review deadline is modified, the corresponding task for the reviewers is updated with the new date.   

1. If a reviewer is removed:

   ![Removing a reviewer](assets/removeduser.png)

    1. If incomplete, the assigned task is terminated.
    1. The reviewer can no longer comment on the asset.

1. If a reviewer is added:

   ![Adding a reviewer](assets/addedreviewer.png)

    1. A review task is created and assigned to the newly added reviewer.
    1. The newly added reviewer can add comments for the asset.

1. When a review ends:

    1. **Reviewers**: For each reviewer, the incomplete task related to the review is terminated. The task no longer appears as 'Pending' in the reviewer's Notifications section.
    1. **Initiator**: The task assigned to the Review initiator is marked complete. The task is removed from the Notification section of the review initiator.
    1. **All**: The review appears in the Previous Reviews section. No further comments can be added.

>[!MORE_LIKE_THIS]
>
>* [Managing form metadata](../../forms/using/manage-form-metadata.md)
>* [Downloading an XFA or a PDF form template](../../forms/using/download-xfa-or-pdf-form.md)
>* [Creating and managing reviews of an Adaptive Form](../../forms/using/create-reviews-forms.md)
>* [Creating new folders to categorize forms](../../forms/using/creating-new-folders-categorize-forms.md)
