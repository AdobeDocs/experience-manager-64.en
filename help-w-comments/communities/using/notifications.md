---
title: Communities Notifications
seo-title: Communities Notifications
description: AEM Communities has notifications that display events of interest to the signed-in community member
seo-description: AEM Communities has notifications that display events of interest to the signed-in community member
uuid: 2a1145b4-a839-43f5-8f85-8142d2ee6a5f
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: ec1c9b44-19dd-41f8-a26e-5398f690812a
index: y
internal: n
snippet: y
---

# Communities Notifications{#communities-notifications}

## Overview {#overview}

AEM Communities provides a notifications section which displays events of interest to the signed in community member.

Notifications are similar to [activities](../../communities/using/essentials-activities.md) and [subscriptions](../../communities/using/subscriptions.md) as they may result from

* the member posting content
* the member choosing to follow another member
* the member choosing to follow specific topics, articles and other threads of content

What distinguishes notifications from activities and subscriptions is

* a link to the notifications section is always present in a community site's header

    * activities require the [activity stream function](../../communities/using/functions.md#activity-stream-function) to be included in the community site's structure
    * subscriptions require [configuration of email](../../communities/using/email.md)

* the implementation of notifications is through scalable and pluggable channels

    * activities are only available on the web
    * subscriptions are only available using email

As of Communities [FP1](../../communities/using/deploy-communities.md#latestfeaturepack), the notification channels available are

* the web channel, accessed using the `Notifications` link
* the email channel, available when email is properly configured

Future channels are mobile and desktop.

### Requirements {#requirements}

**Configure Email**

Email must be configured in order for the email channel for notifications to be functional.

For instructions on setting up email, see [Configuring Email](../../communities/using/analytics.md).

**Enable Follow**

Components must be configured to enable following. Features that allow following are [blog](../../communities/using/blog-feature.md), [forum](../../communities/using/forum.md), [QnA](../../communities/using/working-with-qna.md), [calendar](../../communities/using/calendar.md), [filelibrary](../../communities/using/file-library.md), and [comments](../../communities/using/comments.md).

Note that

* components used within community [site templates](../../communities/using/sites.md) and [group templates](../../communities/using/tools-groups.md) may already be configured to allow following

* member profiles are already configured to allow other memebers to follow

## Notifications from Following {#notifications-from-following}

![](assets/chlimage_1-262.png)

The **Follow **button provides a means to follow entries as activities, subscriptions and/or notifications. Each time the **Follow **button is selected, it is possible to toggle on or off a selection. The `Email Subscriptions` selection is only present when configured.

If any method of following is selected, the text of the button changes to **Following**. For convenience, it is possible to select `Unfollow All` to toggle off all methods.

The **Follow **button will appear

* when viewing another member's profile
* on a main feature page, such as forums, QnA, and blogs

    * follows all activity for that general feature

* for a specific entry, such as a forum topic, QnA question, or blog article

    * follows all activity for that specific entry

## Managing Notification Settings {#managing-notification-settings}

By selecting the Notification Settings link from the Notifications page, it is possible for each member to manage how notifications are received.

The web channel is always enabled.

![](assets/chlimage_1-263.png)

The email channel, which relies on proper [configuration of email](../../communities/using/email.md), provides the same settings as for the web channel.

The email channel is off by default.

![](assets/chlimage_1-264.png)

It may be turned on by a member, but still depends on email being configured.

![](assets/chlimage_1-265.png)

## Viewing Notifications {#viewing-notifications}

### Web Notifications {#web-notifications}

A [wizard created community site](../../communities/using/sites-console.md) now includes a link to the `Notifications` feature in the site's header bar above the banner. Unlike messages, notifications are created for every community site, while messages must be enabled during the site creation process.

When visiting the published site, selecting the `Notifications` link will display all notifications for the member.

![](assets/chlimage_1-266.png)

### Email Notifications {#email-notifications}

When the email channel is enabled, the member receives an email which contains a link to the content on the web.

![](assets/chlimage_1-267.png)

