---
title: Promoting Launches
seo-title: Promoting Launches
description: You need to promote launch pages to move the content back into the source (production) before publishing. When a launch page is promoted, the corresponding page of the source pages is replaced with the content of the promoted page.
seo-description: You need to promote launch pages to move the content back into the source (production) before publishing. When a launch page is promoted, the corresponding page of the source pages is replaced with the content of the promoted page.
uuid: 3e4e63e5-3727-4001-ba9c-5bddc7e60f65
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: edbb30ba-2927-4a39-a05c-d774c5aaf852
legacypath: /content/docs/en/aem/6-0/author/site-page-features/launches
index: y
internal: n
snippet: y
---

# Promoting Launches{#promoting-launches}

You need to promote launch pages to move the content back into the source (production) before publishing. When a launch page is promoted, the corresponding page of the source pages is replaced with the content of the promoted page. The following options are available when promoting a launch page:

* Whether to promote only the current page or the entire launch.
* Whether to promote the child pages of the current page.
* Whether to promote the full launch or only pages that have changed.

## Promoting Launch Pages {#promoting-launch-pages}

To promote pages, perform the following steps while editing the launch page that you want to promote:

1. On the **Page** tab in Sidekick, click **Promote Launch**.
1. Specify the pages to promote:

    * (Default) To promote only the current page, select **Promote Page Changes To Production Version**.
    * To also promote the child pages of the curent page, select **Include Sub Pages**.
    * To promote all pages in the launch, select **Promote Full Launch To Production Version**.

1. To add the production pages to a workflow package, select **Add To Workflow Package** and then select the workflow package.
1. Click **Promote**.

## Processing Promoted Pages Using AEM Workflow {#processing-promoted-pages-using-aem-workflow}

Use workflow models to perform bulk processing of promoted Launches pages:

1. Create a workflow package. 
1. When authors promote Launch pages, they store them in the workflow package.
1. Start a workflow model using the package as the payload.

To start a workflow automatically when pages are promoted, [configure a workflow launcher](../../../sites/administering/using/workflows-starting.md#main-pars-par12-evwuge-refd) for the package node.

For example, you can automatically generate page activation requests when authors promote Launches pages. Configure a workflow launcher to start the Request Activation workflow when the package node is modified. 

![](assets/chlimage_1-147.png)

