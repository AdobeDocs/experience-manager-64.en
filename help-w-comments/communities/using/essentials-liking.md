---
title: Liking Essentials
seo-title: Liking Essentials
description: Liking component overview
seo-description: Liking component overview
uuid: d60c0690-8929-4d3c-a6ea-ff7272bdc5dc
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 58102194-a986-42b4-95a9-199995df8c9d
pagetitle: Liking Essentials
index: y
internal: n
snippet: y
---

# Liking Essentials{#liking-essentials}

The liking component, a [tally](../../communities/using/tally.md) subclass, is a useful tool that allows members to express a positive opinion about a particular piece of content by simply selecting the heart icon.

Placing multiple instances of a liking component on the same page is allowed; each instance must be configured with an unique `tally name` property.

Anonymous posting of a like is not supported. Site visitors must register and sign in to participate in liking. The signed in visitor (member) may toggle like on and off at any time.

## Essentials for Client-Side {#essentials-for-client-side}

<table border="1" cellpadding="4" cellspacing="4" width="100%"> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td>social/tally/components/hbs/liking</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/scf.md#addorincludeacommunitiescomponent"><strong>includable</strong></a></td> 
   <td>Yes - properties are editable in <i>design </i>mode</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/client-customize.md#clientlibsforscf"><strong>clientlibs</strong></a></td> 
   <td> cq.social.hbs.liking</td> 
  </tr> 
  <tr> 
   <td> <strong>templates</strong></td> 
   <td><p> /libs/social/tally/components/hbs/liking/liking.hbs<br /> /libs/social/tally/components/hbs/liking/activity-icon.hbs<br /> /libs/social/tally/components/hbs/liking/activity-title.hbs</p> </td> 
  </tr> 
  <tr> 
   <td><strong>CSS</strong></td> 
   <td> /libs/social/tally/components/hbs/liking/clientlibs/likingcomponent.css</td> 
  </tr> 
  <tr> 
   <td><strong>properties</strong></td> 
   <td><p>see <a href="../../communities/using/liking.md">Using Liking</a></p> </td> 
  </tr> 
 </tbody> 
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Tally APIs](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/api/package-summary)

* [Tally Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/endpoints/package-summary)

* [Server-side Customizations](../../communities/using/server-customize.md)

### Accessing Posted Voting (UGC) {#accessing-posted-voting-ugc}

UGC should be moderated using one of the standard methods for moderation.  
See [Moderating User Generated Content](../../communities/using/moderate-ugc.md).

As of AEM 6.1 Communities, use of a [common store](../../communities/using/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See :

* [Storage Resource Provider Overview](../../communities/using/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](../../communities/using/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](../../communities/using/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](../../communities/using/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

