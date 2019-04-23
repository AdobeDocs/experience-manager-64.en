---
title: Tally Essentials
seo-title: Tally Essentials
description: Tally class overview
seo-description: Tally class overview
uuid: c369c6a1-9ced-4b5c-af43-8c03236eaa52
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 9941ba90-3d40-4c90-bca8-5db49603cbfa
---

# Tally Essentials{#tally-essentials}

Tally is an abstract class providing a standard method of collecting feedback from members on how they value specific products and services. Anonymous feedback is not supported. The site visitor must register and sign in to participate and sign in to change their feedback. The requirement to sign in facilitates moderation and enhances the value of the feedback by preventing multiple posts.

A custom tally component can be created by extending the abstract tally class.

[Liking](/help/communities/essentials-liking.md) is an implementation of tally that is simple form of expressing a positive opinion.

[Voting](/help/communities/essentials-voting.md) is an implementation of tally that is simple form of expressing a positive or negative opinion.

[Rating](/help/communities/rating-basics.md) is an implementation of tally that uses a star system for expressing a range of opinions from positive to negative.

As of AEM 6.1, the [poll](/help/communities/poll-basics.md) component is not currently available.

[Reviews](/help/communities/reviews-basics.md) is an SCF component that is a hybrid of [comments](/help/communities/essentials-comments.md) and [rating](/help/communities/rating-basics.md).

## Essentials for Client-Side {#essentials-for-client-side}

* [Client-side Customizations](/help/communities/client-customize.md)

## Essentials for Server-Side {#essentials-for-server-side}

* [Tally APIs](https://helpx.adobe.com/experience-manager/6-4/sites-developing/reference-materials/javadoc/com/adobe/cq/social/tally/client/api/package-summary.html)

* [Tally Endpoints](https://helpx.adobe.com/experience-manager/6-4/sites-developing/reference-materials/javadoc/com/adobe/cq/social/tally/client/endpoints/package-summary.html)

* [Server-side Customizations](/help/communities/server-customize.md)

### Accessing Posted Tallies (UGC) {#accessing-posted-tallies-ugc}

UGC should be moderated using one of the standard methods for moderation.  
See [Moderating User Generated Content](/help/communities/moderate-ugc.md).

As of AEM 6.1 Communities, use of a [common store](/help/communities/working-with-srp.md) for UGC includes programmatic access to UGC regardless of the chosen storage option (such as ASRP, MSRP or JSRP).

**The location and format of the UGC in the repository is subject to change without warning**.

See:

* [Storage Resource Provider Overview](/help/communities/srp.md) - introduction and repository usage overview
* [SRP and UGC Essentials](/help/communities/srp-and-ugc.md) - SRP utility methods and examples
* [Accessing UGC with SRP](/help/communities/accessing-ugc-with-srp.md) - coding guidelines
* [SocialUtils Refactoring](/help/communities/socialutils.md) - mapping deprecated utility methods to current SRP utility methods

