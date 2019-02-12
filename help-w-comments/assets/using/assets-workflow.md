---
title: Applying Workflows to Assets
seo-title: Applying Workflows to Assets
description: Learn how to apply workflows to assets, folders, and collections in AEM Assets.
seo-description: Learn how to apply workflows to assets, folders, and collections in AEM Assets.
uuid: 8150a1e6-338d-4d5d-aca4-003c09eecfa0
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
topic-tags: authoring
discoiquuid: a25faac9-63a8-4148-ba65-78adc01c94d3
index: y
internal: n
snippet: y
---

# Applying Workflows to Assets{#applying-workflows-to-assets}

<!--
Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2017-11-30T05:28:25.607-0500
<p>Move it to authoring and Chiradeep to edit/update</p>
-->

Applying workflows to digital assets is the same as for website pages. For a complete guide on how to create and use workflows in AEM, see [Starting Workflows](../../sites/authoring/using/workflows-participating.md).

Use workflows in digital assets to activate the asset or create watermarks. Many of the workflows for assets are automatically turned on. For example, the workflow that automatically creates a rendition after an image is edited is automatically turned on.

<!--
Comment Type: remark
Last Modified By: unknown unknown (ltrielof)
Last Modified Date: 2017-11-30T05:28:25.628-0500
<p>We also need to explain that DAM uses workflows for asset processing, which workflows there are out of the box, which workflow launcher configurations and how to add new auto-processing workflows.</p>
<p><br /> </p>
<p>Create a new workflow, Create a new workflow launcher configuration for /content/dam and dam:Asset - connect launcher config to new workflow. Add the steps you need to the workflow.</p>
-->

<!--
Comment Type: draft

<p>To add new auto-processing workflows:<br /> </p>
<ol>
<li>Create a new workflow.</li>
<li>Create a new workflow launcher configuration for /content/dam and dam:Asset.</li>
<li>Connect the launcher configuration to the new workflow.</li>
<li>Add the steps you need to the workflow.</li>
</ol>
<p> </p>
-->

## Applying a workflow to an AEM asset {#applying-a-workflow-to-an-aem-asset}

For details of applying a workflow to an AEM asset, see [Starting a Workflow on an Asset](../../assets/using/managing-assets-touch-ui.md#startingaworkflowonanasset).

## Applying a workflow to multiple assets {#applying-a-workflow-to-multiple-assets}

1. From the Assets console, navigate to the location of the assets for which you want to start a workflow, and select the assets.
1. Click the GlobalNav icon, and the choose **Timeline** from the menu to display the timeline.

   ![](assets/chlimage_1-84.png)

1. Click the **Actions** (arrow) icon at the bottom.

   ![](assets/chlimage_1-85.png)

1. Click **Start Workflow**.
1. In the **Start Workflow** dialog, select a workflow model from the list.

   ![](assets/chlimage_1-86.png)

1. (Optional) Specify a title for the workflow, which can be used to reference the workflow instance.
1. Click **Start **and then click **Confirm** in the dialog. The workflow runs on all the assets you selected.

## Applying a workflow to multiple folders {#applying-a-workflow-to-multiple-folders}

The procedure to apply a workflow to multiple folders is similar to the procedure to apply a workflow to multiple assets. Select the folders in the Assets console, and perform steps 2-7 of the procedure [Applying a workflow to multiple assets](../../assets/using/assets-workflow.md#main-pars-title-322337838).

## Applying a workflow to a collection {#applying-a-workflow-to-a-collection}

For details of applying a workflow to a collection, see [Running a workflow on a collection](../../assets/using/managing-collections-touch-ui.md#runningaworkflowonacollection).
