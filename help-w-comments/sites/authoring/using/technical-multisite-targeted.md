---
title: How Multisite Management for Targeted Content is Structured
seo-title: How Multisite Management for Targeted Content is Structured
description: A diagram shows how multisite support for targeted content is structured
seo-description: A diagram shows how multisite support for targeted content is structured
uuid: b2b158c7-91ed-4b60-9b98-0e40c5eca600
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: personalization
discoiquuid: af1485bf-acd0-4b36-ad26-2fab7c61645c
index: y
internal: n
snippet: y
---

# How Multisite Management for Targeted Content is Structured{#how-multisite-management-for-targeted-content-is-structured}

The following diagram shows how multisite support for targeted content is structured.

Areas appear underneath **/content/campaigns/&lt;brand&gt;** and by default each brand has a master area, which is created automatically. Each area contains its own set of activities, experiences, and offers.

![](assets/chlimage_1-323.png)

To look up targeted content, the pages or sites can map to an area. If there is no area configured, AEM falls back to the master area for this specific brand.

The following diagram is an example of how the logic works for three sites, called site1, site2, and site3.

![](assets/chlimage_1-324.png)

* site1 looks up myarea1 for brand1 and otherarea2 for brand2 based on area mapping.
* site2 looks up myarea1 for brand1 and master area for brand2 as only the area mapping for brand1 is defined.
* site3 looks up the master area for brand1 and brand2 as no other area mapping is defined at all for this site.

