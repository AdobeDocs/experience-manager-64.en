---
title: Featured Content Feature
seo-title: Featured Content Feature
description: The Featured Content feature lets signed-in site visitors highlight content 
seo-description: The Featured Content feature lets signed-in site visitors highlight content 
uuid: 3a0942f1-fb42-4730-ac06-6dcd4fb21941
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 8138f87f-2fb3-424f-937d-90dc87f11972
index: y
internal: n
snippet: y
---

# Featured Content Feature{#featured-content-feature}

### Introduction {#introduction}

The featured content feature provides an area for signed-in site visitors (community members) in the publish environment to highlight content for

* [blogs](../../communities/using/blog-feature.md)
* [calendars](../../communities/using/calendar.md)
* [forums](../../communities/using/forum.md)
* [ideas](../../communities/using/ideation-feature.md)
* [QnA](../../communities/using/working-with-qna.md)

Once content is flagged as featured, it will be listed within this component, which may be placed in specific landing pages or areas that easily catches the attention of community members.

The ability to feature content may be allowed or disallowed per component.

This section of the documentation describes

* adding featured content to a community site
* configuration settings for the `Featured Content`component

### Adding Featured Content to a Page {#adding-featured-content-to-a-page}

To add a `Featured Content` component to a page in author mode, use the component browser to locate

* `Communities / Featured Content`

and drag it into place on a page where the featured contentshould appear.

For necessary information, visit [Communities Components Basics](../../communities/using/basics.md).

When the [required client-side libraries](../../communities/using/essentials-featured.md#essentialsforclientside) are included, this is how the `Featured Content`component will appear :

![](assets/chlimage_1-12.png)

### Configuring Featured Content {#configuring-featured-content}

Select the placed `Featured Content` component to access and select the `Configure` icon which opens the edit dialog.

![](assets/chlimage_1-13.png) ![](assets/chlimage_1-14.png)

#### Settings tab {#settings-tab}

Under the **Settings **tab, identify the content to feature :

* **Display Name** 
  The title for the list of featured content. For example `Featured Questions` or `Featured Ideas`. Default is `Featured Content` if left empty.

* **Location of the Featured Content** 
  *(Required)* Browse to the page containing the content that may be feature (components of that page must be configured to Allow Featured Content). For example, `/content/sites/engage/en/forum`

* **Display Limit** 
  The maximum number of featured content to display. Default is 5.

### Site Visitor Experience {#site-visitor-experience}

The ability to flag content as featured content requires moderator privileges.

When a moderator views posted content, they have access to the in-context moderation flags, which includes the new `Feature` flag.

![](assets/chlimage_1-15.png)

Once flagged as feature, the modeartion flag becomes `Unfeature`.

The page containing the `Featured Content` component, will now include this post.

![](assets/chlimage_1-16.png)

`Read More` is a link to the actual post.

### Additional Information {#additional-information}

More information may be found on the [Featured Content](../../communities/using/essentials-featured.md) page for developers.

For flagging content as featured, see [Moderating User Generated Content](../../communities/using/moderate-ugc.md).
