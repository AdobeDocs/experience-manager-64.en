---
title: Overlay Comments Component
seo-title: Overlay Comments Component
description: Overlay Comments component overview
seo-description: Overlay Comments component overview
uuid: 6b4baa4e-983d-489b-8329-acadedb5459f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: cfc48caa-e38e-4a54-9349-0b60f21b62b6
---

# Overlay Comments Component{#overlay-comments-component}

The intention of [overlaying](../../communities/using/client-customize.md#overlays) a default component is to alter the appearance or behavior of a component globally, for all relative references to the component. It relies on the nature of sling to resolve to the /apps folder before searching in the /libs folder. Thus the path to the component is identical to the path to the default component, except it is in the /apps folder and not the /libs folder.

## Example {#example}

Suppose you would like to modify the comment feature so it matches the design of your website, by changing the comment header so it no longer displays the avatar for any comment. The solutions for hiding the avatar are either using CSS, or, as described here, overlaying the header.jsp in the apps folder so the HTML containing the avatar is never sent to the client.

To overlay comments you will need to:

1. [Comments Page](../../communities/using/overlay-create-comments-page.md)
1. [Create Nodes](../../communities/using/overlay-create-nodes.md)
1. [Alter the Appearance](../../communities/using/overlay-alter-appearance.md)

