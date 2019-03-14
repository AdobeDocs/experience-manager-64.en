---
title: Voting Essentials
seo-title: Voting Essentials
description: Voting component overview
seo-description: Voting component overview
uuid: ed0a771d-1c14-4fbf-ab6a-a028e5ee2e2a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 1a947a06-6a5c-4be9-b2fa-e5fa809ff3b8
---

# Voting Essentials{#voting-essentials}

The voting component, a [tally](../../communities/using/tally.md) subclass, is a useful tool that allows members to rate a particular piece of content by simply selecting up or down arrows to indicate their opinion.

Placing multiple instances of a voting component on the same page is allowed; each instance must be configured with an unique `tally name` property.

Anonymous posting of a vote is not supported. Site visitors must register and sign in to participate in voting only once, The signed in visitor (member) may change their vote at any time.

## Essentials for Client-Side {#essentials-for-client-side}

<table> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td>social/tally/components/hbs/voting</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/scf.md#add-or-include-a-communities-component"><strong>includable</strong></a></td> 
   <td>Yes - properties are editable in <i>design </i>mode</td> 
  </tr> 
  <tr> 
   <td> <a href="../../communities/using/client-customize.md#clientlibs-for-scf"><strong>clientlibs</strong></a></td> 
   <td> cq.social.hbs.voting</td> 
  </tr> 
  <tr> 
   <td> <strong>templates</strong></td> 
   <td><p> /libs/social/tally/components/hbs/voting/voting.hbs<br /> /libs/social/tally/components/hbs/voting/activity-title.hbs</p> </td> 
  </tr> 
  <tr> 
   <td><strong>CSS</strong></td> 
   <td> /libs/social/tally/components/hbs/voting/clientlibs/votingcomponent.css</td> 
  </tr> 
  <tr> 
   <td><strong>properties</strong></td> 
   <td><p>see <a href="../../communities/using/voting.md">Using Voting</a></p> </td> 
  </tr> 
 </tbody> 
</table>

* [Client-side Customizations](../../communities/using/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Tally APIs](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/api/package-summary.md)

* [Tally Endpoints](/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/endpoints/package-summary.md)

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

