---
title: Overlay Comments Component
seo-title: Overlay Comments Component
description: null
seo-description: Overlay Comments component overview
uuid: 63046547-01d6-48b7-8a73-a793bdccee17
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 26424c41-cba9-4f5c-ab29-9d4edd3a90aa
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Overlay Comments Component{#overlay-comments-component}

The intention of [overlaying](../../communities/using/client-customize.md#overlays) a default component is to alter the appearance or behavior of a component globally, for all relative references to the component. It relies on the nature of sling to resolve to the /apps folder before searching in the /libs folder. Thus the path to the component is identical to the path to the default component, except it is in the /apps folder and not the /libs folder.

### Example {#example}

Suppose you would like to modify the comment feature so it matches the design of your website, by changing the comment header so it no longer displays the avatar for any comment. The solutions for hiding the avatar are either using CSS, or, as described here, overlaying the header.jsp in the apps folder so the HTML containing the avatar is never sent to the client.

To overlay comments you will need to:

1. [Comments Page](../../communities/using/overlay-create-comments-page.md)
1. [Create Nodes](../../communities/using/overlay-create-nodes.md)
1. [Alter the Appearance](../../communities/using/overlay-alter-appearance.md)

