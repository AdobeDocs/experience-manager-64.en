---
title: Designs and the Designer
seo-title: Designs and the Designer
description: null
seo-description: You will need to create a design for your website and in AEM, you do so by using the Designer
uuid: f7dcbf31-2b54-4c30-9883-2e37816c6e99
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: eb1558e0-6417-46d0-a455-a7ae98841fd9
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Designs and the Designer{#designs-and-the-designer}

You will need to create a design for your website and in AEM, you do so by using the Designer.

>[!NOTE]
>
>For more information about Web accessibility, see [AEM and the Web Accessibility Guidelines](/content/help/en/experience-manager/6-4/managing/using/web-accessibility).

### Using the Designer {#using-the-designer}

Your design can be defined in the ******designs** section of the **Tools** tab:

![](assets/screen_shot_2012-02-01at30237pm.png)

Here you can create the structure required to store the design, then upload the cascaded style sheets and images required.

Designs are stored under `/etc/designs`. The path to the design to be used for a website is specified using the `cq:designPath` property of the `jcr:content` node.

![](assets/chlimage_1-85.png)

>[!NOTE]
>
>All the changes that are made on a page in design mode are persisted below the design node of the site and are automatically applied to all pages that have the same design.

### What you will need {#what-you-will-need}

To realize your design you will need:

**CSS** The Cascading Style Sheets define the formats of specific areas on your pages.

**Images** Any images that you use for features such as backgrounds, buttons.

### Considerations When Designing Your Website {#considerations-when-designing-your-website}

<!--
Comment Type: remark
Last Modified By: (colligno@adobe.com)
Last Modified Date: 2018-01-18T11:19:17.680-0500
<p>Clientlibs should be used instead.</p>
-->

When developing a website, it is highly recommended to store images and CSS files under `/etc/design/<project>` so you can reference your resources based on the current design like described by the following snippet.

```xml
<%= currentDesign.getPath() + "/static/img/icon.gif %>
```

The preceding example offers severals benefits:

* Components can have a different look/feel based on each site using a different design path.
* Re-design of the website can be simply done by pointing the design path to a different node at the root of the site from `design/v1` to `design/v2.`

* `/etc/designs` and `/content` are the only external URLs that the browser sees protecting you of an external user getting curious about what is under your `/apps` tree. The above URL benefits also aid your System Administrator to setup better security because you are limiting the exposure of the assets to a few distinct locations.

