---
title: Using Reviews and Reviews Summary (Display)
seo-title: Using Reviews and Reviews Summary (Display)
description: Adding the Reviews and Reviews Summary components to a page
seo-description: Adding the Reviews and Reviews Summary components to a page
uuid: bd1ccee7-b26b-4a27-b1ea-89609f5080af
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: bf4e7809-8def-4647-aaa6-3ac36865511f
---

# Using Reviews and Reviews Summary (Display){#using-reviews-and-reviews-summary-display}

The `Reviews`component is a composite of [ `Comments`](../../communities/using/comments.md) and [ `Rating`](../../communities/using/rating.md) components ready for use.

The `Reviews Summary (Display)` component provides a summary of an active or closed instance of a `Reviews` component for display elsewhere on the site.

>[!NOTE]
>
>Anonymous posting of a review is not supported. Site visitors must register (become a member) and sign in to participate. The signed in visitor may update their review at any time.

## Adding a Review to a Page {#adding-a-review-to-a-page}

To add a `Reviews` component to a page in author mode, use the component browser to locate

* `Communities / Reviews`

and drag it into place on a page, such as a position relative to the feature for users to review.

For necessary information, visit [Communities Components Basics](../../communities/using/basics.md).

When the [required client-side libraries](../../communities/using/reviews-basics.md#essentials-for-client-side) are included, this is how the `Reviews`component will appear.

![](assets/chlimage_1-340.png)

## Configuring Reviews {#configuring-reviews}

Select the placed `Reviews` component to access and select the `Configure` icon which opens the edit dialog.

![](assets/chlimage_1-341.png)

Under the **Allowed Ratings **tab, specify the complete list of ratings to be shown to members. The first rating should be an overall/general rating, as it is the rating which provides the average rating for the `Review Summary (Display)` component. The next two ratings in the default configuration should be given a different title, other than "Subrating 1" or "Subrating 2".

![](assets/chlimage_1-342.png)

* **Allowed Ratings** 
  A list of ratings from which a member can choose.  
  Use the up arrow, down arrow and delete buttons to modify the visible selections.  
  Click **Add Item **to add another rating choice.

Under the **Required Ratings **tab, re-enter items from the list of **Allowed Ratings** that are required to be rated. If an item is only specified on the Allowed Ratings tab, it may be left unmarked when submitted by the member.

On the website, required ratings are marked with an asterisk. If an item is required and left unmarked, a message is displayed to the member and the submission is denied until all required ratings are marked.

![](assets/chlimage_1-343.png)

* **Required Ratings** 
  A subset of allowed ratings, indicating which ratings are required.  
  Use the up arrow, down arrow and delete buttons to modify the visible selections.  
  Click **Add Item **to add another response choice.

>[!NOTE]
>
>If an item is entered on the **Required Ratings** tab that is not specified on the **Allowed Ratings** tab, then it is not included in the items to rate.

Under the **Reviews **tab, specify how reviews are handled.

![](assets/chlimage_1-344.png)

* **Allow Replies** 
  If checked, allow replies to reviews. Default is unchecked.

* **Closed** 
  If checked, the review is closed to new reviews and replies. Default is unchecked.

* **Allow File Uploads** 
  If checked, allow file attachments to be uploaded for the review. Default is unchecked.

* **Max File Size** 
  Relevant only if **Allow File Uploads** is checked. This field limits the size (in bytes) of an uploaded file. Default is 10 MB.

* **Max Message Length** 
  Maximum number of characters that may be entered into the text box. Default is 4096 characters.

* **Allowed File Types** 
  Relevant only if **Allow File Uploads** is checked. A comma separated list of file extensions with the "dot" separater. For example: .jpg, .jpeg, .png, .doc, .docx, .pdf. If any file types are specifed, then those not specified will not be allowed. Default is none specified such that** **all file types are allowed.

* **Rich Text Editor** 
  If checked, posts may be entered with markup. Default is unchecked.

* **Allow Voting** 
  If checked, include the Voting feature for a topic. Default is unchecked.

Under the **User Moderation **tab, specify how the posted reviews are managed. For more information, see [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

![](assets/chlimage_1-345.png)

* **Pre-Moderation** 
  If checked, reviews must be approved before they will appear on a publish site. Default is unchecked.

* **Delete Reviews** 
  If checked, the member who posted the review is provided the ability to delete it. Default is unchecked.

* **Deny Reviews** 
  If checked, allow moderators to deny reviews. Default is unchecked.

* **Close / Reopen Reviews** 
  If checked, allow moderators to close and reopen reviews. Default is unchecked.

* **Flag Reviews** 
  If checked, allow members to flag reviews as inappropriate. Default is unchecked.

* **Flag Reason List** 
  If checked, allow members to choose, from a drop-down list, their reason for flagging a review as inappropriate. Default is unchecked.

* **Custom Flag Reason** 
  If checked, allow members to enter their own reason for flagging a review as inappropriate. Default is unchecked.

* **Moderation Threshold** 
  Enter the number of times a review has to be flagged by members before moderators are notified. Default is one time (1).

* **Flagging Limit** 
  Enter the number of times a review has to be flagged before it is hidden from public view. This number must be greater than or equal to the **Moderation Threshold**. Default is 5.

### Adding a Review Summary (Display) to a Page {#adding-a-review-summary-display-to-a-page}

To add a `Reviews Summary (Display)` component to a page in author mode, locate the component

* `Communities / Reviews Summary (Display)`

and drag it into place on a page where a summary of an active or closed review is to be displayed.

For necessary information, visit [Communities Components Basics](../../communities/using/basics.md).

When the [required client-side libraries](../../communities/using/reviews-basics.md#essentials-for-client-side) are included, this is how the `Reviews Summary (Display)`component will appear.

![](assets/chlimage_1-346.png)

>[!NOTE]
>
>The "Average" reflects the votes for the first item listed on the Allowed Ratings tabs of the review being summarized.

### Configuring Reviews Summary (Display) {#configuring-reviews-summary-display}

Select the placed `Reviews Summary (Display)` component to access and select the `Configure` icon which opens the edit dialog.

![](assets/chlimage_1-347.png)

Under the **Review Summary** tab

![](assets/chlimage_1-348.png)

* `Review Path`  
  enter or browse to the placed instance of the `reviews`component to summarize, for example, if added to the Web Page of the [Geometrixx Engage site,](../../communities/using/getting-started.md) the path would be:  
  /content/sites/engage/en/page/jcr:content/content/primary/reviews

* `Include histogram`  
  If checked, include the display of a bar graph indicating how many of each star rating there are in the reviews being summarized. Default is unchecked.

### Changing to a Custom Review Type {#changing-to-a-custom-review-type}

The Reviews component uses the Comment System.

By changing the Comment Resource Type, the comment system will no longer generate an instance of a comment using the default, but rather one that has been customized (extended) by developers.

Once the custom resource types is known, enter [Design Mode](../../sites/authoring/using/default-components-designmode.md) and double click on the placed `Comments` component to open a dialog with an additional tab.

Under the **Resource Types **tab, specify the custom resourceType for new instances of the `Comments or Voting`components:

![](assets/chlimage_1-349.png)

* **Comment Resource Type** 
  Navigate to the resourceType of an extended `comment`component (single comment) in /apps. For example, `/apps/social/commons/components/hbs/comments/comment`  
  This resource will identify the resourceType of the UGC created when a visitor posts a comment.

* **Voting Resource Type** 
  Navigate to the resourceType of an extended `voting`component in /apps. For example, `/apps/social/components/hbs/voting`  
  This resource will identify the resource type of the UGC created when a visitor posts a vote.

* **Comment System Resource Type** 
  Navigate to the resourceType of an extended `comments`component (Comment System) in /apps. Leave blank unless the page template [dynamically includes](../../communities/using/scf.md#add-or-include-a-communities-component) the Comment System in the underlying script instead of being added to the page as a resource (comments node). Learn more by reading about the [{{include}} helper](../../communities/using/handlebars-helpers.md#include)

## Site Visitor Experience {#site-visitor-experience}

### Moderators and Administrators {#moderators-and-administrators}

When the signed in user has moderator or administrator privileges, they are able to perform the moderation tasks permitted by the configuration of the component, regardless of who authored the review.

### Members {#members}

When the site visitor is signed in, depending on the configuration, they may

* post a new review
* edit their own review
* delete their own review
* flag others' review comments

Only one rating per member is allowed. The member may change their rating at any time.

### Anonymous {#anonymous}

Site visitors who are not signed in may only read posted reviews, translate them if supported, but may not add a rating or a review, nor flag others' review comments.

## Additional Information {#additional-information}

More information may be found on the [Review Essentials](../../communities/using/reviews-basics.md) page for developers.

For moderation of posted comments, see [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

For translation of posted comments, see [Translating User Generated Content](../../communities/using/translate-ugc.md).
