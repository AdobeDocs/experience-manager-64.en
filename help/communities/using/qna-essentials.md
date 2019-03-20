---
title: QnA Essentials
seo-title: QnA Essentials
description: Questions and answers forum feature
seo-description: Questions and answers forum feature
uuid: c718a8e3-b3bd-4db9-8c0f-6dd973d40583
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: ceace3aa-78a5-485e-b519-630479e087d8
---

# QnA Essentials{#qna-essentials}

This page provides the essential information for working with the questions and answers (QnA) forum feature.

## Essentials for Client-Side {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> resourceType</td> 
   <td>social/qna/components/hbs/qnaforum</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#add-or-include-a-communities-component">includable</a></td> 
   <td>No</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/clientlibs.md">clientllibs</a></td> 
   <td>cq.ckeditor<br /> cq.social.hbs.voting<br /> cq.social.hbs.qna</td> 
  </tr>
  <tr>
   <td> templates</td> 
   <td> /libs/social/qna/components/hbs/qnaforum/qnaforum.hbs<br /> /libs/social/qna/components/hbs/qnaforum/activity-title.hbs</td> 
  </tr>
  <tr>
   <td> css</td> 
   <td> /libs/social/qna/components/hbs/qnaforum/clientlibs/qnaforum.css</td> 
  </tr>
  <tr>
   <td> properties</td> 
   <td>see <a href="../../communities/using/working-with-qna.md">Q&amp;A Forum Feature</a></td> 
  </tr>
 </tbody>
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [QnA API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/qna/client/api/package-summary.md)

* [QnA Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/qna/client/endpoints/package-summary.md)

* [Server-side Customizations](../../communities/using/server-customize.md)

### QnA Function {#qna-function}

A community site structure that includes the [QnA function](../../communities/using/functions.md#qna-function) will have a configured `QnA` component, as well as settings affecting moderation and tagging. The QnA function supports identifying a [privileged member user group](../../communities/using/users.md#privileged-members-group).

### Accessing QnA Forum Posts (UGC) {#accessing-qna-forum-posts-ugc}

UGC should be moderated using one of the standard methods for moderation.  
See [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See:

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods
