---
title: How Multisite Management for Targeted Content is Structured
seo-title: How Multisite Management for Targeted Content is Structured
description: null
seo-description: A diagram shows how multisite support for targeted content is structured
uuid: f27a239f-6833-424c-84ac-6a0798677ff6
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: personalization
discoiquuid: b028d530-c6c0-4254-84ae-9f2d7c31f2f7
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# How Multisite Management for Targeted Content is Structured{#how-multisite-management-for-targeted-content-is-structured}

The following diagram shows how multisite support for targeted content is structured.

Areas appear underneath **/content/campaigns/&lt;brand&gt;** and by default each brand has a master area, which is created automatically. Each area contains its own set of activities, experiences, and offers.

![](assets/chlimage_1-266.png)

To look up targeted content, the pages or sites can map to an area. If there is no area configured, AEM falls back to the master area for this specific brand.

The following diagram is an example of how the logic works for three sites, called site1, site2, and site3.

![](assets/chlimage_1-267.png)

* site1 looks up myarea1 for brand1 and otherarea2 for brand2 based on area mapping.
* site2 looks up myarea1 for brand1 and master area for brand2 as only the area mapping for brand1 is defined.
* site3 looks up the master area for brand1 and brand2 as no other area mapping is defined at all for this site.

