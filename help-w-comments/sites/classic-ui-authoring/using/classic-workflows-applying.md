---
title: Applying Workflows to Pages
seo-title: Applying Workflows to Pages
description: Workflows can be started from either the Websites console or, when editing a page, from Sidekick.
seo-description: Workflows can be started from either the Websites console or, when editing a page, from Sidekick.
uuid: 2a132266-49c4-48dd-8687-d1894ea1d6b6
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 27044de1-32c8-41fc-83a1-8b76649ecfdb
index: y
internal: n
snippet: y
---

# Applying Workflows to Pages{#applying-workflows-to-pages}

When you apply the workflow, you specify the following information:

* The workflow to apply.  
  You can apply any workflow (that you have access to, as assigned by your AEM administrator).
* Optionally:

    * A comment that provides information about why you started the workflow. 
    * A title that helps identify the workflow instance in a user's Inbox.

>[!NOTE]
>
>AEM administrators can start workflows using [several other methods](../../../sites/administering/using/workflows-starting.md).

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-57F1056A4CD116590A746C15@AdobeID)
Last Modified Date: 2017-11-30T05:07:15.642-0500
<ol>
<li>is the following complete?</li>
<li>are there any restrictions if a workflow is started from the Workflow/s Model tab/console? </li>
</ol>
-->

<!--
Comment Type: draft

<note type="caution">
<p>There are slight differences according to the UI:</p>
<ul>
<li>Touch-enabled UI<br /> You can assign multiple workflows to a specific payload at the same time.</li>
<li>Classic UI<br /> You can only assign one workflow at a time to a specific payload. </li>
</ul>
</note>
-->

## Applying Workflows {#applying-workflows}

Workflows can be started from either the Websites console or, when editing a page, from Sidekick.

The **Status** column in the **Websites** console indicates whether a workflow has been applied to a page:

![](assets/workflowstatus.png)

### Starting a Workflow from the Websites Console {#starting-a-workflow-from-the-websites-console}

1. Open the Websites console. ([http://localhost:4502/siteadmin](http://localhost:4502/siteadmin))
1. In the Websites tree, select the parent of the page to which you want to apply the workflow.
1. In the page list, select the page and then click Workflow.
1. In the Start Workflow dialog, select the workflow to apply. Optinally, enter a comment and a title. Then, click Start.

### Starting a Workflow using Sidekick {#starting-a-workflow-using-sidekick}

1. Open the Websites console.
1. Open the required page.
1. Select the Workflow tab from the Sidekick.
1. Expand the **Workflow** dialog, allowing you to select the **Workflow** and optionally enter **Workflow Title** and **Comment**.

   ![](assets/workflowstartsidekick.png)

1. Click **Start Workflow** to start a new workflow instance with the properties you configured and the current page as the payload. Now the workflow is running.

