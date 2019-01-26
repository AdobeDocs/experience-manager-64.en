---
title: Personalization
seo-title: Personalization
description: null
seo-description: Learn how to create personalized content in AEM
uuid: c6c2d637-2ddc-4abd-b62a-347f3f8e647a
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: personalization
discoiquuid: a36f6308-a589-4d41-8852-a993aeaca076
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Personalization{#personalization}

## Personalization and Content Targeting {#personalization-and-content-targeting}

AEM provides a framework of tools for authoring targeted content and presenting personalized experiences.

### Targeting mode {#targeting-mode}

[Author targeted content](../../authoring/using/content-targeting-touch.md) using Targeting mode of AEM. Targeting mode and the Target component provide tools for creating content for the experiences of your marketing activities.

### Activities {#activities}

Activities define and organize your marketing efforts. Activities comprise the audiences that you are targeting, and the period of time when the targeting is applied.

For example, the Geometrixx Outdoors product catalog includes teasers that focus attention on seasonal products. The Summer Sports activity defines the marketing segments that the teasers target during summer months.

Activities also identify the [targeting engine](../../authoring/using/personalization.md#main-pars-title-2) that your pages use.

Use the [Activites console](../../authoring/using/activitylib.md) to create and manage the activities for your brands. You can also create activities as you [author targeted content](../../authoring/using/content-targeting-touch.md).

### Experiences {#experiences}

For each activity, you define one or more experiences that identify the audiences that you are targeting. AEM enables you to control the content that comprises each experience.

Audiences are based on marketing segments that are created either in AEM or Adobe Target. When a visitor opens a web page, the page logic determines the audience to which they belong and displays the content that you have created for that audience.

For example, an activity defines experiences for two separate audiences: women over the age of 30 and women under the age of 30. The Women's page of the Geometrixx Outdoors web site displays different products for each experience.

You define experiences for an activity. You can use the [Activities console](../../authoring/using/activitylib.md#main-pars-title-0) or [Targeting mode](../../authoring/using/content-targeting-touch.md#main-pars-title-1) to add experiences to an activity.

### Offers {#offers}

An offer is content that appears at a location on a page for an experience. Use different offers for different experiences to maximize the effectiveness of the content for your audiences.

For example, the Women's page of the Geometrixx Outdoors sample web site can use offers as the teaser image that appears at the top of the page. A different offer is used as the teaser for the Female Over 30 experience and for the Female Under 30 experience.

Use the [Offers console](../../authoring/using/offerlib.md) to create offers that you can use in multiple experiences. Create single-use offers or add offers from an offer library when [authoring targeted content](../../authoring/using/content-targeting-touch.md).

### Targeting Engine {#targeting-engine}

The targeting engine is the mechanism that drives the logic for targeted content. [Activities](../../authoring/using/activitylib.md) are configured to use one of two targeting engines that are available: AEM and Adobe Target.

#### AEM {#aem}

AEM provides a built-in targeting engine that processes page requests and determines the content to display. When using the AEM targeting engine, you are limited to using segments that are created in AEM for defining the audiences of your experiences.

#### Adobe Target {#adobe-target}

The Adobe Target targeting engine causes information gathered from page visits to be tracked in Adobe Target.

* When using this targeting engine, you use the segments that you import from Adobe Target to define the audiences for your experiences.
* Activities that use the Adobe Target engine are [synchronized to Target](../../authoring/using/activitylib.md#main-pars-title-1192575824).

You can use this engine when you have [integrated with Adobe Target](../../administering/using/opt-in.md).
