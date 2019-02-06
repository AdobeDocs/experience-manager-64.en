---
title: Structure of the AEM Touch-Enabled UI
seo-title: Structure of the AEM Touch-Enabled UI
description: The touch-optimized UI, as implemented in AEM, has several underlying principles and is made up of several key elements
seo-description: The touch-optimized UI, as implemented in AEM, has several underlying principles and is made up of several key elements
uuid: 77e93ac1-f5f0-4354-b3dd-bd91592f5c4e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: e43d9e71-7438-4c87-8fb6-13386a30f984
index: y
internal: n
snippet: y
---

# Structure of the AEM Touch-Enabled UI{#structure-of-the-aem-touch-enabled-ui}

The AEM touch-enabled UI has several underlying principles and is made up of several key elements:

## Consoles {#consoles}

### Basic Layout and Resizing {#basic-layout-and-resizing}

The UI caters for both mobile and desktop devices, though rather than creating two styles Adobe has decided to use one style that works for all screens and devices.

All modules use the same basic layout, in AEM this can be seen as: 

![](assets/chlimage_1-155.png)

The layout adheres to a responsive design style and will accomodate itself to the size of the device/window you are using.

For example, when the resolution goes below 1024px (as on a mobile device) the display will be adjusted accordingly:

![](assets/chlimage_1-156.png) 

### Header Bar {#header-bar}

![](assets/chlimage_1-157.png)

The header bar shows global elements including:

* the logo and the specific product/solution that you are currently using; for AEM this also forms a link to the Global Navigation
* Search
* icon for accessing the help resources
* icon for accessing other Solutions
* a indicator of (and access to) any alerts or Inbox items that are waiting for you
* the user icon, together with a link to your profile management

### Toolbar {#toolbar}

This is contextual to your location and surfaces tools relevant to controlling the view or assets in the page below. The toolbar is product specific, but there is some commonality to the elements.

In any location the toolbar shows the actions currently available: 

![](assets/chlimage_1-158.png)

Also dependent on whether a resource is currently selected:

![](assets/chlimage_1-159.png) 

### Left Rail {#left-rail}

The left rail can be opened/hidden as required to show:

* **Timeline**
* **References**
* **Filter**

The default is **Content Only** (rail hidden).

![](assets/chlimage_1-160.png) 

## Page Authoring {#page-authoring}

When authoring pages the structural areas are as follows.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-02-09T03:19:27.176-0500
<p>need cross references to javadocs / etc (when available) <br /> </p>
-->

### Content Frame {#content-frame}

The page content is rendered in the content frame. The content frame is completely independent of the editor - to ensure that there are no conflicts due to CSS or javascript.

The content frame is on the right-hand section of the window, under the toolbar. 

![](assets/chlimage_1-161.png) 

### Editor Frame {#editor-frame}

The editor frame realises the editing features.

The editor frame is a container (abstract) for all the *page authoring elements*. It lives on top of the content frame, and includes:

* the top toolbar
* the side panel
* all the overlays
* any other page authoring element; for example, the component toolbar

<!--
Comment Type: draft

<h4>Editors</h4>
-->

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-57F1056A4CD116590A746C15@AdobeID)
Last Modified Date: 2018-02-09T03:19:27.859-0500
<p>need more details (see <a href="https://jira.corp.adobe.com/browse/DOC-7978">https://jira.corp.adobe.com/browse/DOC-7978</a>)</p>
<ul>
<li>basically the concept of the Editor registry (where "editor.html" acts like a switch and redirects to different components)</li>
<li>relate to <a href="https://docs.adobe.com/docs/en/aem/6-2/develop/ref/jsdoc/ui-touch/editor-core/index.html">https://docs.adobe.com/docs/en/aem/6-2/develop/ref/jsdoc/ui-touch/editor-core/index.html</a>?</li>
</ul>
-->

<!--
Comment Type: draft

<p>All (most) editors (such as the page editor, template editor, etc) use the same internal base, accessed using the same URL section (<span class="code">/editor.html</span>).</p>
-->

<!--
Comment Type: draft

<note type="note">
<p>The following editors do not use this common internal base:</p>
<ul>
<li><a href="../../../sites/authoring/using/content-fragments.md">Content Fragment editor</a></li>
<li><a href="../../../sites/authoring/using/rich-text-editor.md">Rich Text editor</a></li>
</ul>
</note>
-->

![](assets/chlimage_1-162.png) 

### Side Panel {#side-panel}

This contains two default tabs to allow you to select assets and components; they can be dragged from here and dropped onto the page.

The side panel is hidden by default. When selected it will either be shown at the left side, or will slide across to cover the entire window (when the window size is below a width of 1024px; as, for example, on a mobile device).

![](assets/chlimage_1-163.png) 

### Side Panel - Assets {#side-panel-assets}

In the Assets tab you can select from the range of assets. You can also filter on a specific term, or select a group.

![](assets/chlimage_1-164.png) 

### Side Panel - Asset Groups {#side-panel-asset-groups}

In the Asset tab there is a drop down that you can use to select the specific asset groups.

![](assets/chlimage_1-165.png) 

### Side Panel - Components {#side-panel-components}

In the Components tab you can select from the range of components. You can also filter on a specific term, or select a group.

![](assets/chlimage_1-166.png) 

### Overlays {#overlays}

These overlay the content frame and are used by the [layers](#layer) to realize the mechanics of how you can interact (completely transparently) with the components and their content.

The overlays live in the editor frame (with all other page authoring elements), though they actually overlay the appropriate components in the content frame.

![](assets/chlimage_1-167.png) 

### Layer {#layer}

A layer is an independent bundle of functionality that can be activated to:

* provide a different view of the page  
* allow you to manipulate and/or interact with a page

The layers provide sophisticated functionality for the entire page, as opposed to specific actions on an individual component.

AEM comes with several layers already implemented for page authoring; including for example, edit, preview, annotate.

>[!NOTE]
>
>Layers are a powerful concept that affect the user's view of and interaction with the page content. When developing your own layers you need to ensure that the layer cleans up when it is exited.

### Layer Switcher {#layer-switcher}

The layer switcher allows you to choose the layer you want to use. When closed, it indicates the layer currently in use.

The layer switcher is available as a drop down from the toolbar (at the top of the window, within the editor frame). 

![](assets/chlimage_1-168.png) 

### Component Toolbar {#component-toolbar}

Each instance of a component will reveal its toolbar when clicked (either once or with a slow double-click). The toolbar contains the specific actions (e.g. copy, paste, open-editor) that are available for the component instance (Editable) on the page.

Depending on the space available, the component toolbars are positioned at the top-, or bottom-, right corner of the appropriate component.

![](assets/chlimage_1-169.png) 

## Further Information {#further-information}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-57F1056A4CD116590A746C15@AdobeID)
Last Modified Date: 2018-02-09T03:19:30.453-0500
<p>check links when JS docs etc available</p>
-->

For more details about the concepts around the touch-enabled UI, continue to the article [Concepts of the AEM Touch-Enabled UI](../../../sites/developing/using/touch-ui-concepts.md).

For further technical information see the [JS documentation set](/sites/developing/using/reference-materials/jsdoc/ui-touch/editor-core/index) for the touch-enabled page editor.  

