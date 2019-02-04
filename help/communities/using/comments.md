---
title: Using Comments
seo-title: Using Comments
description: null
seo-description: Comments feature lets signed-in site visitors share their opinions and knowledge
uuid: 1d81b119-9d61-41c6-94a6-bb176c0f20f4
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 1e556b61-32a1-4ae2-a039-9f672d357e0b
index: y
internal: n
snippet: y
---

# Using Comments{#using-comments}

### Introduction {#introduction}

The comments feature is used to allow signed-in site visitors (members) to share their opinions and knowledge regarding content on the site. This feature is often already present in other features, but may be added to any website.

This section of the documentation describes

* adding `Comments`to a page
* configuration settings for the `Comments`component

>[!NOTE]
>
>Anonymous posting of a comment is not supported. Site visitors must register (become a member) and sign in to participate.

### Adding Comments to a Page {#adding-comments-to-a-page}

To add a `Comments`component to a page in author mode, use the component browser to locate

* `Communities / Comments`

and drag it into place on a page, such as a position relative to the feature for users to comment on, or simply at the bottom of the page.

For necessary information, visit [Communities Components Basics](../../communities/using/basics.md).

When the [required client-side libraries](../../communities/using/essentials-comments.md#essentialsforclientside) are included, this is how the `Comments`component will appear.

![](assets/chlimage_1-440.png)

>[!NOTE]
>
>Only one `Comments`component may exist on a page. Be aware that several Communities features already include comments, such as a blog, calendar, forum, QnA, and reviews.

### Configuring Comments {#configuring-comments}

Select the placed `Comments` component to access and select the `Configure` icon which opens the edit dialog.

![](assets/Configure.PNG) ![](assets/CommentsSettings.png)

#### Comments tab {#comments-tab}

Under the **Comments **tab, specify how comments are entered by visitors.

* **Allow replies** 
  If checked, allows members to reply to existing comments. Default is unchecked.

* **Comments Per Page** 
  Limits the number of comments shown per page as well as the number of replies shown. Default is 10.

* **Allow File Uploads** 
  If checked, the option to upload a file will be presented with the text entry box. Default is unchecked.

* **Max File Size** 
  Relevant only if Allow File Uploads is checked. This value will limit the uploaded file size. Default limit is 10 MB.

* **Max Message Length** 
  Maximum number of characters that may be entered into the text box. Default is 4096 characters.

* **Allowed File Types** 
  Relevant only if Allow File Uploads is checked. A comma separated list of file extensions with the "dot" separater. For example : .jpg, .jpeg, .png, .doc, .docx, .pdf. If any file types are specifed, then those not specified will not be allowed. Default is none specified such that** **all file types are allowed.

* **Rich Text Editor** 
  If checked, comments may be entered with markup. Default is unchecked.

* **Allow Voting** 
  If checked, the option to vote up or down will be presented with the text entry box. Default is unchecked.

* **Allow Following** 
  If checked, allow members to follow comments. Default is unchecked.

* **Display Badges** 
  If checked, allow earned and awarded badges to be displayed. Default is unchecked.

#### User Moderation tab {#user-moderation-tab}

Under the **User Moderation **tab, specify how the posted comments are managed. For more information, see [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

* **Pre-Moderation** 
  If checked, comments must be approved before they will appear on a publish site. Default is unchecked.

* **Delete Comments** 
  If checked, the member who posted the comment is provided the ability to delete it. Default is unchecked.

* **Deny Comments** 
  If checked, allow moderators to deny comments. Default is unchecked.

* **Close / Reopen Comments** 
  If checked, allow moderators to close and reopen comments. Default is unchecked.

* **Flag Comments** 
  If checked, allow members to flag comments as inappropriate. Default is unchecked.

* **Flag Reason List** 
  If checked, allow members to choose, from a drop-down list, their reason for flagging a comment as inappropriate. Default is unchecked.

* **Custom Flag Reason** 
  If checked, allow members to enter their own reason for flagging a comment as inappropriate. Default is unchecked.

* **Moderation Threshold** 
  Enter the number of times a comment has to be flagged by members before moderators are notified. Default is one time (1).

* **Flagging Limit** 
  Enter the number of times a comment has to be flagged before it is hidden from public view. This number must be greater than or equal to the **Moderation Threshold**. Default is 5.

#### Sort Settings tab {#sort-settings-tab}

Under the **Sort Settings **tab, specify how the posted comments are sorted when displayed.

* **Sort Field** 
  Pull down to select one of `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed`, or `Most Liked`.

* **Sort Order** 
  Pull down to select one of `Ascending` or `Descending`.

### Changing to a Custom Comment Type {#changing-to-a-custom-comment-type}

By changing the Comment Resource Type, the comment system will no longer generate an instance of a comment using the default, but rather one that has been customized (extended) by developers.

Once the custom resource types is known, enter [Design Mode](../../sites/authoring/using/default-components-designmode.md) and double click on the placed `Comments` component to open a dialog with an additional tab.

Under the **Resource Types **tab, specify the custom resourceType for new instances of the `Comments or Voting`components :

![](assets/chlimage_1-441.png)

* **Comment Resource Type** 
  Navigate to the resourceType of an extended `comment`component (single comment) in /apps. For example, `/apps/social/commons/components/hbs/comments/comment`  
  This resource will identify the resourceType of the UGC created when a visitor posts a comment.

* **Voting Resource Type** 
  Navigate to the resourceType of an extended `voting`component in /apps. For example, `/apps/social/components/hbs/voting`  
  This resource will identify the resource type of the UGC created when a visitor posts a vote.

* **Comment System Resource Type** 
  Navigate to the resourceType of an extended `comments`component (Comment System) in /apps. Leave blank unless the page template [dynamically includes](../../communities/using/scf.md#addorincludeacommunitiescomponent) the Comment System in the underlying script instead of being added to the page as a resource (comments node). Learn more by reading about the [{{include}} helper](../../communities/using/handlebars-helpers.md#include).

### Site Visitor Experience {#site-visitor-experience}

#### Moderators and Administrators {#moderators-and-administrators}

When the signed in user has moderator or administrator privileges, they are able to perform the moderation tasks permitted by the configuration of the component, regardless of who authored the comment.

#### Members {#members}

When the site visitor is signed in, depending on the configuration, they may

* post a new comment
* edit their own comment
* delete their own comment
* flag others' comments

#### Anonymous {#anonymous}

Site visitors who are not signed in may only read posted comments, translate them if supported, but may not add a comment nor flag others' comments.

### Additional Information {#additional-information}

More information may be found on the [Comments Essentials](../../communities/using/essentials-comments.md) page for developers.

For moderation of posted comments, see [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

For translation of posted comments, see [Translating User Generated Content](../../communities/using/translate-ugc.md).
