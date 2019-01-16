---
title: How Multisite Management for Targeted Content is Structured
seo-title: How Multisite Management for Targeted Content is Structured
description: null
seo-description: A diagram shows how multisite support for targeted content is structured
uuid: 1b99da30-7c99-4a09-9ca6-41afb57c96c9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: personalization
discoiquuid: 8cd25ca1-a9b5-493a-9004-c69993d43a96
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# How Multisite Management for Targeted Content is Structured{#how-multisite-management-for-targeted-content-is-structured}

The following diagram shows how multisite support for targeted content is structured.

Areas appear underneath **/content/campaigns/&lt;brand&gt;** and by default each brand has a master area, which is created automatically. Each area contains its own set of activities, experiences, and offers.

![](assets/chlimage_1-296.png)

To look up targeted content, the pages or sites can map to an area. If there is no area configured, AEM falls back to the master area for this specific brand.

The following diagram is an example of how the logic works for three sites, called site1, site2, and site3.

![](assets/chlimage_1-297.png)

* site1 looks up myarea1 for brand1 and otherarea2 for brand2 based on area mapping.
* site2 looks up myarea1 for brand1 and master area for brand2 as only the area mapping for brand1 is defined.
* site3 looks up the master area for brand1 and brand2 as no other area mapping is defined at all for this site.

