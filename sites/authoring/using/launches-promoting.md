---
title: Promoting Launches
seo-title: Promoting Launches
description: null
seo-description: You need to promote launch pages to move the content back into the source (production) before publishing. 
uuid: d06edf4b-36d1-424a-9d93-43542bfeb7b3
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: b51be5e8-d732-4af4-8ff3-d49064fedb68
isreadyforlocalization: false
legacypath: /content/docs/en/aem/6-0/author/site-page-features/launches
index: y
internal: n
snippet: y
---

# Promoting Launches{#promoting-launches}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T00:22:21.197-0500
<p>6.5</p>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-11-27T00:22:37.342-0500
<p>6.5 changes included</p>
-->

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-57F1056A4CD116590A746C15@AdobeID)
Last Modified Date: 2017-11-30T04:52:41.248-0500
<p>6.2 </p>
<ul>
<li>smart launches; only promote pages that have changed<br /> </li>
</ul>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-14T08:08:52.173-0500
<p>6.5</p>
<ul>
<li>delete launch after promote</li>
<li>see<br />
<ul>
<li>[Launches] Issues with Timeline after deleting a Launch after promotion</li>
<li>URL: <a href="https://jira.corp.adobe.com/browse/CQ-4257973">https://jira.corp.adobe.com/browse/CQ-4257973</a></li>
</ul> </li>
</ul>
-->

You need to promote launch pages to move the content back into the source (production) before publishing. When a launch page is promoted, the corresponding page of the source pages is replaced with the content of the promoted page. The following options are available when promoting a launch page:

* Whether to promote only the current page or the entire launch.
* Whether to promote the child pages of the current page.
* Whether to promote the full launch or only pages that have changed.

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-14T08:09:00.352-0500
<p>6.5</p>
-->

<!--
Comment Type: draft

<p>You need to promote launch pages to move the content back into the source (production) before publishing. When a launch page is promoted, the corresponding page of the source pages is replaced with the content of the promoted page. The following options are available when promoting a launch page:</p>
<ul>
<li>Whether to promote only the current page or the entire launch.</li>
<li>Whether to promote the child pages of the current page.</li>
<li>Whether to promote the full launch or only pages that have changed.</li>
<li>Whether to delete the launch after being promoted.</li>
</ul>
-->

>[!NOTE]
>
>After you promote the launch pages to the target (**Production**), you can activate the **Production** pages as an entity (to make the process quicker). Add the pages to a workflow package and use it as the payload for a workflow that activates a package of pages. You need to create the workflow package before promoting the launch. See [Processing Promoted Pages Using AEM Workflow](#processingpromotedpagesusingaemworkflow).

>[!CAUTION]
>
>A single launch cannot be promoted concurrently. This means that two promote actions on the same launch at the same time can result in an error - `Launch could not be promoted` (together with conflict errors in the log).

>[!CAUTION]
>
>When promoting launches for *modified* pages, modifications in both the source and launch branches are considered.

## Promoting Launch Pages {#promoting-launch-pages}

>[!NOTE]
>
>This covers the manual action of promoting launch pages when there is only one launch level. See:
>
>* [Promoting a Nested Launch](#promotinganestedlaunch) when there is more than one launch in the structure.
>* [Launches - the Order of Events](../../authoring/using/launches.md#launchestheorderofevents) for further details about automatic promotion and publication.
>

You can promote launches from either the **Sites** console or the **Launches** console:

1. Open:

    * the **Sites** console:

        1. Open the [references rail](../../authoring/using/author-environment-tools.md#showingpagereferences) and select the required source page using [selection mode](../../authoring/using/basic-handling.md) (or select and open the references rail, the order is not important). All references will be shown.
        
        1. Select **Launches** (e.g. Launches (1)) to show a list of the specific launches.
        1. Select the specific launch to show the actions available.
        1. Select **Promote launch** to open the wizard.

    * the **Launches** console:

        1. Select your launch (tap/click on the thumbnail).
        1. Select **Promote**.

1. In the first step you can specify:

    * **Promote full launch**
    * **Promote modified pages**
    * **Promote current page**
    * **Promote current page and sub pages**

   For example, when selecting to only promote modified pages:

   ![](assets/chlimage_1-183.png) 

   <!--
   Comment Type: remark
   Last Modified By: Alison Heimoz (aheimoz)
   Last Modified Date: 2019-01-14T08:01:58.223-0500
   <p>6.5</p>
   -->

   <!--
   Comment Type: draft

   <p>In the first step you can specify:</p>
   <ul>
   <li><strong>Target</strong><br />
   <ul>
   <li><strong>Delete launch after promotion</strong></li>
   </ul> </li>
   <li><strong>Scope</strong>
   <ul>
   <li><strong>Promote full launch</strong></li>
   <li><strong>Promote modified pages</strong></li>
   <li><strong>Promote current page</strong></li>
   <li><strong>Promote current page and sub pages</strong></li>
   </ul> </li>
   </ul>
   <p>For example, when selecting to only promote modified pages:<br /> </p>
   -->

   <!--
   Comment Type: draft

   <img imageRotate="0" src="assets/Launches-PD-06.png" />
   -->

   <!--
   Comment Type: remark
   Last Modified By: Alison Heimoz (aheimoz)
   Last Modified Date: 2018-11-26T01:44:22.397-0500
   <p>6.5</p>
   <ul>
   <li>delete launch after promotion
   <ul>
   <li>any special/considerations for nested launches?</li>
   </ul> </li>
   </ul>
   -->

   >[!NOTE]
   >
   >This covers a single launch, if you have nested launches see [Promoting a Nested Launch](#promotinganestedlaunch).

1. Select **Next** to proceed.
1. You can review the pages to be promoted, these will depend on the range of pages you have chosen:

   ![](assets/chlimage_1-184.png)

1. Select **Promote**.

## Promoting Launch Pages when Editing {#promoting-launch-pages-when-editing}

When you are editing a launch page, the **Promote Launch** action is also available from **Page Information**. This will open the wizard to collect the information needed.

![](assets/chlimage_1-185.png)

>[!NOTE]
>
>This is available for single and [nested launches](#promotinganestedlaunch).

## Promoting a Nested Launch {#promoting-a-nested-launch}

After creating a nested launch you can promote it back to any of the sources, including the root source (production).

![](assets/chlimage_1-186.png)

1. As with [Creating a Nested Launch](#creatinganestedlaunchlaunchwithinalaunch), navigate to and select the required launch in either the **Launches** console or the **References** rail.
1. Select **Promote launch** to open the wizard.  

1. Enter the required details:

    * **Promotion target** 
      You can promote to any of the sources.  
    
    * **Scope** 
      Here you can select whether to promote the entire launch, or only pages that have actually been edited. If the latter, you can then select to include/exclude sub-pages. The default configuration is to only promote page changes for the current page:

        * **Promote full launch**
        * **Promote modified pages**
        * **Promote current page**
        * **Promote current page and sub pages**

   <!--
   Comment Type: remark
   Last Modified By: Alison Heimoz (aheimoz)
   Last Modified Date: 2019-01-14T08:09:19.142-0500
   <p>6.5</p>
   -->

   <!--
   Comment Type: remark
   Last Modified By: Alison Heimoz (aheimoz)
   Last Modified Date: 2018-11-26T01:45:03.981-0500
   <p>see also <a href="https://jira.corp.adobe.com/browse/CQ-4257988">https://jira.corp.adobe.com/browse/CQ-4257988</a></p>
   -->

   <!--
   Comment Type: remark
   Last Modified By: Alison Heimoz (aheimoz)
   Last Modified Date: 2018-11-26T01:45:19.527-0500
   <p>confirm what d-l-a-p will do for a nested launch?</p>
   -->

   <!--
   Comment Type: draft

   <p>Enter the required details:</p>
   <ul>
   <li><strong>Target</strong>
   <ul>
   <li><strong>Promotion target</strong><br /> You can promote to any of the sources.</li>
   <li><strong>Delete launch after promotion</strong><br /> After promotion the selected launch, and any launches nested within it, will be deleted.<strong><br /> </strong></li>
   </ul> </li>
   <li><strong>Scope</strong><br /> Here you can select whether to promote the entire launch, or only pages that have actually been edited. If the latter, you can then select to include/exclude sub-pages. The default configuration is to only promote page changes for the current page:
   <ul>
   <li><strong>Promote full launch</strong></li>
   <li><strong>Promote modified pages</strong></li>
   <li><strong>Promote current page</strong></li>
   <li><strong>Promote current page and sub pages</strong></li>
   </ul> </li>
   </ul>
   -->

   ![](assets/chlimage_1-187.png)

1. Select **Next**.
1. Review the promotion details before selecting **Promote**:

   <!--
   Comment Type: remark
   Last Modified By: unknown unknown (ims-author-57F1056A4CD116590A746C15@AdobeID)
   Last Modified Date: 2017-11-30T04:52:42.152-0500
   <p>seems to show -1 when it's all pages - isn't that a bit confusing for the users?</p>
   -->

   ![](assets/chlimage_1-188.png)

   >[!NOTE]
   >
   >The pages listed will depend on the **Scope** defined and possibly the pages that have actually been edited.

1. Your changes will be promoted and reflected in the **Launches** console:

   ![](assets/chlimage_1-189.png)

## Processing Promoted Pages Using AEM Workflow {#processing-promoted-pages-using-aem-workflow}

Use workflow models to perform bulk processing of promoted Launches pages:

1. Create a workflow package. 
1. When authors promote Launch pages, they store them in the workflow package.
1. Start a workflow model using the package as the payload.

To start a workflow automatically when pages are promoted, [configure a workflow launcher](../../administering/using/workflows-starting.md#main-pars-par12-evwuge-refd) for the package node.

For example, you can automatically generate page activation requests when authors promote Launches pages. Configure a workflow launcher to start the Request Activation workflow when the package node is modified. 

![](assets/chlimage_1-190.png) 

<!--
Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-191.png" />
-->

