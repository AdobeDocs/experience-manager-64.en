---
title: Reviews Essentials
seo-title: Reviews Essentials
description: Reviews and Review Summary components
seo-description: Reviews and Review Summary components
uuid: e3e904e4-feca-4c85-acb6-c45fa3ac3d0d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: d702357b-d831-475e-b61a-39e034ca48d7
index: y
internal: n
snippet: y
---

# Reviews Essentials{#reviews-essentials}

This feature consists of two components that work together : reviews and review summary.

Reviews is a composite component based on a [comment system](../../communities/using/essentials-comments.md) which contains one or more [rating](../../communities/using/rating-basics.md) (tally) components.

Anonymous posting of a review is not supported. Site visitors must register and sign in to add a review. The signed in visitor (member) may update their review at any time.

## Essentials for Client-Side {#essentials-for-client-side}

#### Reviews {#reviews}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/reviews/components/hbs/reviews</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>Yes - properties are editable in <i>design </i>mode</td> 
  </tr>
  <tr>
   <td> <a href="../../communities/using/client-customize.md#clientlibsforscf"><strong>clientllibs</strong></a></td> 
   <td>cq.social.hbs.reviews</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/reviews/components/hbs/reviews/reviews.hbs<br /> /libs/social/reviews/components/hbs/reviews/review/review.hbs<br /> /libs/social/reviews/components/hbs/reviews/review/status.hbs<br /> /libs/social/reviews/components/hbs/reviews/review/toolbar.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/reviews/components/hbs/reviews/clientlibs/review.css</td> 
  </tr>
  <tr>
   <td><strong>properties</strong></td> 
   <td>see <a href="../../communities/using/reviews.md">Using Reviews</a></td> 
  </tr>
 </tbody>
</table>

#### Review Summary {#review-summary}

|  **resourceType** |social/reviews/components/hbs/summary |
|---|---|
|  [**includable**](../../communities/using/scf.md#addorincludeacommunitiescomponent) |Yes - properties are editable in *design *mode |
|  [**clientllibs**](../../communities/using/client-customize.md#clientlibsforscf) |cq.social.hbs.reviews |
|  **templates** | /libs/social/reviews/components/hbs/summary/summary.hbs |
|  **css** | /libs/social/reviews/components/hbs/reviews/clientlibs/review.css |
| **properties** |see [Using Reviews](../../communities/using/reviews.md) |

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Review API](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/review/client/api/package-summary)

* [Review Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/review/client/endpoints/package-summary)

* [Server-side Customizations](../../communities/using/server-customize.md)

### Accessing Posted Reviews (UGC) {#accessing-posted-reviews-ugc}

UGC should be moderated using one of the standard methods for moderation.  
See [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See :

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

