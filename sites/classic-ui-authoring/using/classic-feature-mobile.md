---
title: Authoring a Page for Mobile Devices
seo-title: Authoring a Page for Mobile Devices
description: null
seo-description: When authoring a mobile page, the page is displayed in a way that emulates the mobile device. When authoring the page, you can switch between several emulators to see what the end-user sees when accessing the page.
uuid: fb80a299-c9a5-45f7-afe8-88e35ddaf441
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 05123432-de86-4f8a-b502-3dddefdaa41c
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Authoring a Page for Mobile Devices{#authoring-a-page-for-mobile-devices}

When authoring a mobile page, the page is displayed in a way that emulates the mobile device. When authoring the page, you can switch between several emulators to see what the end-user sees when accessing the page.

Devices are grouped into the categories feature, smart, and touch according to the capabilities of the devices to render a page. When the end-user accesses a mobile page, AEM detects the device and sends the representation that corresponds to its device group.

>[!NOTE]
>
>To create a mobile site based on an existing standard site, create a live copy of the standard site. (See [Creating a Live Copy for Different Channels](../../administering/using/msm-livecopy.md).)
>
>AEM developers can create new device groups. (See [Creating Device Group Filters.](../../developing/using/groupfilters.md))

Use the following procedure to author a mobile page:

1. In your browser, go to the **Siteadmin** console.
1. Open the **Products** page below **Websites** &gt;&gt; **Geometrixx Mobile Demo Site** &gt;&gt; **English**.  

1. Switch to a different emulator. To do so, you can either:

    * Click the device icon at the top of the page.
    * Click the **Edit** button in the **Sidekick** and select the device in the drop-down menu.

1. Drag and drop the **Text & Image** component from the Mobile tab of the Sidekick to the page.
1. Edit the component and add some text. Click **OK** to save the changes.

The page looks the same as the following:

![](assets/mobileipademu.png)

>[!NOTE]
>
>The emulators are disabled when a page on the author instance is requested from a mobile device. Authoring can then be done by using the touch-optimized UI.

