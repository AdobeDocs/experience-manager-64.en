---
title: Communities Components Basics
seo-title: Communities Components Basics
description: Add Communities features to AEM sites in edit mode and configure components
seo-description: Add Communities features to AEM sites in edit mode and configure components
uuid: 9d96bb8e-b0ab-4314-b0ac-31b6274290a0
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 235e37d5-1cd0-4ba6-990e-b943e4dd0868
---

# Communities Components Basics{#communities-components-basics}

## Overview {#overview}

The authoring section of the documentation describes adding Communities features to AEM sites in author edit mode, as well as describing component configurations.

Components may be explored using an AEM instance and the interactive [Community Components guide](../../communities/using/components-guide.md).

## Accessing Communities Components {#accessing-communities-components}

When authoring page content, if the underlying template permits changes to the design of the page, it is possible to enable components that are not already available in the components browser as part of the site design.

The available Communities components are listed [here](../../communities/using/author-communities.md#availablecommunitiescomponents).

>[!NOTE]
>
>For general authoring information, view the [quick guide to authoring pages](../../sites/authoring/using/qg-page-authoring.md).
>
>If not familiar with AEM, view the documentation on [basic handling](../../sites/authoring/using/basic-handling.md).

### Entering Design Mode {#entering-design-mode}

If a **Communities **component is not found in the components browser (sidekick), it will be necessary to enter `Design Mode` to add other Communities components. [Required client-side libraries](#requiredclientlibs) (clientlibs) may also need to be added.

For details, see [Configuring Components in Design Mode](../../sites/authoring/using/default-components-designmode.md).

Following are images of selecting a few Communities components and viewing them in the components browser :

![](assets/chlimage_1-424.png)

The selected components are now available in the components browser :

![](assets/chlimage_1-425.png)

## Required Clientlibs {#required-clientlibs}

[Client-side libraries](../../sites/developing/using/clientlibs.md) (clientlibs) are required for the proper functioning (JavaScript) and styling (CSS) of a component.

When adding a Communities component to a page, if the result is an error or an unexpected appearance, the first thing to try is adding the required clientlibs for the Communities component. For details, see [Clientlibs for Communities Components](../../communities/using/clientlibs.md).

### Example : initially placed reviews without client libraries ... {#example-initially-placed-reviews-without-client-libraries}

![](assets/chlimage_1-426.png)

### ... and with client libraries {#and-with-client-libraries}

![](assets/chlimage_1-427.png)

## Tagging {#tagging}

Many Communities features may be configured to allow members to tag content entered (posted) in the publish environment.

If tagging is allowed, the community site's configuration may be set to limit the namespaces presented to members in the publish environment. See the [Community Sites console](../../communities/using/sites-console.md#tagging).

Features which allow tagging : [blog](../../communities/using/blog-feature.md), [calendar](../../communities/using/calendar.md), [file library](../../communities/using/file-library.md), [forum](../../communities/using/forum.md)

Features which use tags : [catalog](../../communities/using/catalog.md), [search](../../communities/using/search.md), [social tag cloud](../../communities/using/tagcloud.md)

For authoring information :

* [Using Tags](../../sites/authoring/using/tags.md)

For administrative information :

* Creating tag namespaces (taxonomy) : [Administering Tags](../../sites/administering/using/tags.md)
* Community Site configuration : see [TAGGING](../../communities/using/sites-console.md#tagging)
* [Tagging User Generated Content](../../sites/authoring/using/tags.md)
* [Tagging Enablement Resources](../../communities/using/tag-resources.md)

For developer information :

* [AEM Tagging Framework](../../sites/developing/using/framework.md)
* [Tagging Essentials](../../communities/using/tag.md)

