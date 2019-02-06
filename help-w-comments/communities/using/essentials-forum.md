---
title: Forum Essentials
seo-title: Forum Essentials
description: Forum overview
seo-description: Forum overview
uuid: 9cffdcb4-9905-4ec0-b46f-1b1a60e4699f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 3411b1c8-dddb-498c-949f-2313951691fe
index: y
internal: n
snippet: y
---

# Forum Essentials{#forum-essentials}

This page provides the essential information for working with the forum feature.

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceTypes</strong></td> 
   <td>social/forum/components/hbs/forum<br /> social/forum/components/hbs/topic<br /> social/forum/components/hbs/post</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md"><strong>clientllibs</strong></a></td> 
   <td>cq.ckeditor<br /> cq.social.hbs.voting<br /> cq.social.hbs.forum</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/forum/components/hbs/forum/forum.hbs<br /> /libs/social/forum/components/hbs/post/post.hbs<br /> /libs/social/forum/components/hbs/topic/topic.hbs<br /> /libs/social/forum/components/hbs/topic/list-item.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/forum/components/hbs/forum/clientlibs/forum.css</td> 
  </tr>
  <tr>
   <td><strong> properties</strong></td> 
   <td>see <a href="../../communities/using/forum.md">Forum Feature</a></td> 
  </tr>
 </tbody>
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Forum API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/forum/client/api/package-summary)

* [Forum Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/forum/client/endpoints/package-summary)

* [Server-side Customizations](../../communities/using/server-customize.md)

### Forum Function {#forum-function}

A community site structure that includes the [Forum function](../../communities/using/functions.md#forumfunction), includes a configured `forum` component, as well as settings affecting moderation, tagging and translation.

### Accessing Forum Posts (UGC) {#accessing-forum-posts-ugc}

UGC should be moderated using one of the standard methods for moderation.  
See [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See :

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

