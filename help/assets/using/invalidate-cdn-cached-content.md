---
title: Invalidating your CDN cached content
seo-title: Invalidating your CDN cached content
description: Invalidating your CDN (Content Delivery Network) cached content lets you quickly update assets that are delivered by Dynamic Media, instead of waiting for the cache to expire.
seo-description: Invalidating your CDN (Content Delivery Network) cached content lets you quickly update assets that are delivered by Dynamic Media, instead of waiting for the cache to expire.
uuid: e34c2e3b-e20d-47f6-adbb-174f8bca97e3
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 7b1b8d21-b4a7-4471-acef-a4057f3ea6aa
index: y
internal: n
snippet: y
---

# Invalidating your CDN cached content{#invalidating-your-cdn-cached-content}

Dynamic Media assets are cached by the CDN for fast delivery. However, when you make updates to an asset, you may want those changes to take effect immediately. Invalidating your CDN (Content Delivery Network) cached content lets you quickly update assets that are delivered by Dynamic Media, instead of waiting for the cache to expire.

See also [Cache overview in Scene7](https://helpx.adobe.com/experience-manager/scene7/kb/base/caching-questions/scene7-caching-overview.html).

**To invalidate your CDN cached content:**

1. Log on to your Dynamic Media Classic (Scene7) account:

   Your credentials and logon were provided by Adobe at the time of provisioning. If you do not have this information, contact Technical Support.

1. Click **Setup** &gt; **Application Setup** &gt; **General Settings**.
1. On the Application General Settings page, under the Servers group heading, locate the **CDN Invalidation Template** text box.   

1. Specify the template that is used for invalidating the CDN (Content Delivery Network) cache.

   For example, suppose you enter an image URL (including image presets or modifiers) referencing `<ID>`, instead of a specific image ID as in the following example:

   If the Template just contains `<ID>`, then Dynamic Media fills in `http://<server>/is/image` where `<server>` is the Publish Server Name that is defined in General Settings and &lt;ID&gt; is the asset(s) selected to be invalidated.

1. In the lower-right corner of the page, click **Close**.
1. In the Dynamic Media Classic (Scene7) UI, select one or more assets, then click **File** &gt; **Invalidate CDN**. You will see a list of one or more URLs generated from the template you created and the asset(s) you selected. It uses the server URL listed under "Published Server Name" under the Application General Settings.

   For example, with the CDN Invalidation Template set in the previous step, suppose you selected a single image asset image named `Backpack_B`. When you click **File** &gt; **Invalidate CDN** it results in the following generated URL in the CDN Invalidation user interface:

1. In the URL list box, click **Continue** to clear the cache for each specific URL. Note that you can edit a URL or you can add a URL by typing or pasting it into the URL list box; you do not need to set CDN Invalidate Template beforehand.

   After you click **Continue**, an indicator is displayed that gives you an estimate of how long it will take to clear the cache.

   If you selected multiple assets, then clicked **File** &gt; **Invalidate CDN**, each asset is referenced in the saved Template URL. Therefore, you can define a CDN Invalidate Template referencing each URL image preset that is referenced on your Web site (such as product detail, search results, and so forth). Then, when you select one or images for invalidation from cache, the URLs automatically populate the interface.

   >[!NOTE]
   >
   >When you select assets, and then click **File** &gt; **Invalidate CDN**, Dynamic Media uses an invalidate CDN template to automatically create URLs to invalidate from the Content Delivery Network (CDN). If there is nothing in the CDN Invalidate Template text box, then you get a blank URL list. Caching at the CDN is not asset-based; it is URL-based. Therefore, it is necessary to be aware of the complete URLs that are on your website. After you determine those URLs, you can add them to the Invalidate CDN Template text box earlier in the steps. Then, you can select those assets, and invalidate the URLs in one step.
   >
   >
   >Another option is to add complete URLs to the Invalidate CDN list. If you follow this approach, it is unnecessary to select assets in Dynamic Media Classic before going to the **File** &gt; **Invalidate CDN** option.

