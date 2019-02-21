---
title: Extend Comments Component
seo-title: Extend Comments Component
description: Extend the Comments component to alter its appearance or behavior for specific uses
seo-description: Extend the Comments component to alter its appearance or behavior for specific uses
uuid: 8e3acdd9-4410-4b5e-8541-8563b45fc656
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4ebe0de1-5212-421f-80e1-42f4338496d0
index: y
internal: n
snippet: y
---

# Extend Comments Component{#extend-comments-component}

The intention of [extending](../../communities/using/client-customize.md#extensions) a default component is to alter the appearance or behavior of a component for specific uses.

The path to the component is unique and references the default component as a super resource type. There is less risk as the scope is limited compared to the global scope of a component overlay.

>[!NOTE]
>
>Extending an [overlaid](../../communities/using/client-customize.md#overlays) component is not supported.

### Example {#example}

Suppose the header for the comment component must display with an alternate appearance on one site of the AEM instance, while appearing with the default display on another site. Instead of overlaying the default comment, which changes the comment component for all instances, a better solution is to ensure there are multiple comment components available for use on various sites.

To implement this solution, create a new component that extends (overrides) the existing one and modify the Handlebars script. The area of the site that uses the new comments can use the extended one, while the sites that use the default appearance remain unaffected.

The comment component is actually one of two components which comprise the comment system. Thus, there are two components to extend : *comments* and *comment*. The script to edit is in the *comment *component's `header.hbs` file, while the parent *comments* component (the comment system) is what an author actually adds to the page.

To extend comments you will need to:

1. [Create the Components](../../communities/using/extend-create-components.md)
1. [Add Comment to Sample Page](../../communities/using/extend-sample-page.md)
1. [Alter the Appearance](../../communities/using/extend-alter-appearance.md)

