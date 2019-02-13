---
title: Member Contribution Limits
seo-title: Member Contribution Limits
description: Contribution limits feature lets you limit the contributions to protect against spam
seo-description: Contribution limits feature lets you limit the contributions to protect against spam
uuid: d4eb85d1-c477-4c08-a13e-a1167686aa34
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: decf4773-6aef-473b-9a99-71d99dad39c3
index: y
internal: n
snippet: y
---

# Member Contribution Limits{#member-contribution-limits}

## Overview {#overview}

The contribution limits feature provides the ability to limit the contributions of community members as a means of protecting against spam.

When a member is limited, any post that exceeds the allowed number of contributions will result in an alert that the limit was exceeded and the post is rejected. The community member may then go to the community message center and contact a community manager who can remove the limits if appropriate.

Contribution limits may be enabled individually from the [Members console](../../communities/using/members.md) and/or configured to be automatically enabled when site visitors become new members.

Using the Members console, contribution limits can be proactively removed for a member by a community manager at any time, or reactively removed when a member sends a message to a community manager making such a request.

## AEM Communities User Generated Content Contribution Limits Configuration {#aem-communities-user-generated-content-contribution-limits-configuration}

This OSGi configuration

* defines the characteristics of the contribution limits (number of posts within a time period)
* identifies who the member will be able to message when the limit has been reached
* identifies domains that need never be constrained

To reach this OSGi configuration :

* on the primary publisher
* sign in with administrator privileges
* access the [Web Console](../../sites/deploying/using/configuring-osgi.md)

    * for example, [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* locate `AEM Communities User Generated Content Contribution Limits Configuration`
* select the edit icon

![](assets/chlimage_1-127.png)

* **Automatically Apply UGC Contribution Limits** 
  If checked, automatically set contribution limits on users when they register as community members. This is reflected in the community member's profile and may be enabled/disabled from the [members console](../../communities/using/members.md). New members with an email address from a white listed domain are never constrained.  
  Default is unchecked.

* **UGC Limit** 
  Maximum number of contributions.  
  Default is 10 posts.

* **UGC Limit Frequency** 
  The time period constraining the UGC limit.  
  Default is 60 minutes.

* **Domains** 
  A white list of one or more email domains. Select the + icon to make addtional entries.  
  Users with email addresses in the white listed domains are not affected when UGC contribution limits are automatically applied. For example, if domain `mycompany.com` is added to the list of domains, then a member with email address `me@mycompany.com` is never restricted from posting.  
  Default is an empty white list.

* **Messaging Recipients** 
  List of one or more authorizable IDs of members able to modify the contribution limits for members. Select the + icon to make addtional entries.  
  Members may only reach out to specified members when their limit has been reached.  
  Default is no messaging recipients.

Note: The default configuration results in a limit of 10 posts within a period of one hour.
