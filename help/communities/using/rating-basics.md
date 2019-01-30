---
title: Rating Essentials
seo-title: Rating Essentials
description: null
seo-description: Rating component overview
uuid: 5b1b93cb-9b22-4456-8201-a898875a938a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 484321e9-28e3-4130-b162-c9c1a3a6a54e
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Rating Essentials{#rating-essentials}

The rating component, a [tally](../../communities/using/tally.md) subclass, allows signed in community members to rate a feature on the website.

Placing multiple instances of a voting component on the same page is allowed; each instance must be configured with an unique `tally name` property.

Anonymous posting of a rating is not supported. Site visitors must register and sign in to participate in a rating only once. The signed in visitor (member) may change their rating at any time.

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td> social/tally/components/hbs/rating</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>Yes - properties are editable in <i>design </i>mode</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/client-customize.md#clientlibsforscf"><strong>clientlibs</strong></a></td> 
   <td> cq.social.hbs.rating</td> 
  </tr> 
  <tr> 
   <td> <strong>templates</strong></td> 
   <td><p> /libs/social/tally/components/hbs/rating/rating.hbs<br /> /libs/social/tally/components/hbs/rating/display.hbs<br /> /libs/social/tally/components/hbs/rating/histogram.hbs</p> </td> 
  </tr> 
  <tr> 
   <td><strong>CSS</strong></td> 
   <td> /libs/social/tally/components/hbs/rating/clientlibs/ratingcomponent.css</td> 
  </tr> 
  <tr> 
   <td><strong>properties</strong></td> 
   <td><p>see <a href="../../communities/using/rating.md">Using Rating</a></p> </td> 
  </tr> 
 </tbody> 
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Tally APIs](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/api/package-summary)

* [Tally Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/endpoints/package-summary)

* [Server-side Customizations](../../communities/using/server-customize.md)

### Accessing Posted Ratings (UGC) {#accessing-posted-ratings-ugc}

UGC should be moderated using one of the standard methods for moderation.  
See [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See :

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

