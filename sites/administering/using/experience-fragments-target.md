---
title: Target Integration with Experience Fragments
seo-title: Target Integration with Experience Fragments
description: null
seo-description: Target Integration with Experience Fragments
uuid: b89655bb-fc3d-4036-999f-c3468ac1b80b
contentOwner: carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 6e1172bf-2530-4976-9fea-53a0b650500c
index: y
internal: n
snippet: y
---

# Target Integration with Experience Fragments{#target-integration-with-experience-fragments}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-11T03:00:22.446-0500

<p>Remove for 6.5</p>

 -->

>[!NOTE]
>
>This functionality requires the application of [AEM 6.4 Service Pack 2 (6.4.2.0)](/content/help/en/experience-manager/6-4/release-notes/sp-release-notes) or later.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-07T04:24:53.668-0500

<p><a href="https://experiencecloud.adobe.com/resources/help/en_US/target/target/aem-experience-fragments.html">https://experiencecloud.adobe.com/resources/help/en_US/target/target/aem-experience-fragments.html</a></p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-10T02:24:45.662-0500

<p><a href="https://wiki.corp.adobe.com/display/DMSArchitecture/%5BM3%5D+%5BExperience+Fragments%5D+Support+JSON+offers+for+Target">https://wiki.corp.adobe.com/display/DMSArchitecture/%5BM3%5D+%5BExperience+Fragments%5D+Support+JSON+offers+for+Target</a></p> 
<h2>How to Document</h2> 
<p>Documentation should be added in, or below, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html">https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html</a></p> 
<p>Here is a summary of the most important things that we need to mention:</p> 
<ul> 
 <li>The feature allows to export Experience Fragments to Adobe Target so that they can be used as offers in Target activities</li> 
 <li>As a requirement for this to work, the Target Cloud Service needs to be configured in AEM, and then the configuration needs to be attached to the Experience Fragments (either folder or Experience Fragment level)</li> 
 <li>By default, Experience Fragments would be delivered in HTML format but this can be configured (either at the folder or Experience Fragment level)</li> 
 <li>Experience Fragments are exported from the author instance and the user can trigger the export from either the admin or page editor UI</li> 
 <li>Users can also delete offers that were exported in Target, and see the "sync status" of the offer in case it has been modified (= is the offer in sync or not in sync anymore)</li> 
 <li>Because the Experience Fragments are exported from the author instance, the Link Externalizer must be properly configured on the author instance to have links rewritten to point towards the publish instance</li> 
 <li>Media assets such as images are not being sent to Target, just their reference. The asset itself remains stored in AEM and is delivered from AEM publish, hence there is a need to publish the Experience Fragment before exporting to Target.</li> 
 <li>The JSON export leverages the Sling Model Exporter and thus can be easily customized by extending the OOTB Experience Fragment Sling Model</li> 
</ul>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-11T08:51:15.052-0500

<p>there might be a Core Component for XFs coming....</p> 
<p>https://wiki.corp.adobe.com/display/DMSArchitecture/%5BM3%5D+%5BExperience+Fragments%5D+Export+Experience+Fragments+in+JSON+to+Adobe+Target</p> 
<p>This means that the Experience Fragment offer JSON can be customized if needed. The way to do so is to define a custom Experience Fragment component and then annotate how its properties should be exported in the component Sling Model. <br /> </p>

 -->

You can export [Experience Fragments](../../authoring/using/experience-fragments.md), created in Adobe Experience Manager (AEM), to Adobe Target. They can then be used as offers in Target activities, to test and personalize experiences at scale. This lets you combine the ease-of-use and power of AEM, with the powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in Target.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-10T04:23:56.043-0500

<p>6.5</p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-10T05:38:03.992-0500

<p>see https://adobe-my.sharepoint.com/:p:/r/personal/msiegel_adobe_com/_layouts/15/Doc.aspx?sourcedoc=%7B2290ae5e-c330-4c67-aeef-644938110028%7D&action=default</p>

 -->

<!-- 

Comment Type: draft

<p>There are three format options available for exporting an Experience Fragment to Adobe Target:</p> 
<ul> 
 <li>HTML (the default): Support for hybrid scenarios<br /> </li> 
 <li>JSON: Support for headless scenarios<br /> </li> 
 <li>HTML & JSON</li> 
</ul>

 -->

## Prerequisites {#prerequisites}

Various actions are required:

1. You have to integrate AEM with Target. See [Integrating with Adobe Target](../../administering/using/target.md) for more information.

   <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-10T03:37:44.571-0500

<p>for how much longer - Cloud Services config being deprecated - need to use Adobe Launch<br /> </p> 
<p><a href="https://jira.corp.adobe.com/browse/CQ-4248189">https://jira.corp.adobe.com/browse/CQ-4248189</a></p>

 -->

1. Experience Fragments are exported from the author instance, so you need to [Configure the Link Externalizer](../../developing/using/externalizer.md) on the author instance to ensure that any links are externalized for the publish instance.

## Add the Cloud Configuration {#add-the-cloud-configuration}

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-10T04:09:34.657-0500

<p>6.5</p>

 -->

<!-- 

Comment Type: draft

<h2>Add the Cloud Configuration and Select the Export Format</h2>

 -->

Before exporting a fragment you need to add the **Cloud Configuration** for **Adobe Target** to the fragment, or folder:

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-10T02:51:23.571-0500

<p>6.5</p>

 -->

<!-- 

Comment Type: draft

<p>Before exporting a fragment you need to add the <strong>Cloud Configuration</strong> for <strong>Adobe Target</strong> to the fragment, or folder. At the same time, you can also specify the format option(s) to be used for the export.</p>

 -->

<!-- 

Comment Type: draft

<p>The required options can be selected in <strong>Page Properties</strong> of the required folder and/or fragment; the specification will be inherited as necessary.<br /> </p>

 -->

1. Navigate to the **Experience Fragments** console.
1. Open **Page Properties** for the appropriate folder or fragment.

   >[!NOTE]
   >
   >If you add the cloud configuration to the Experience Fragment parent folder, the configuration is inherited by all the children.
   >
   >
   >If you add the cloud configuration to the Experience Fragment itself, the configuration is inherited by all varations.

1. Select the **Cloud Services** tab.  

1. Under **Cloud Service Configuration**, select **Adobe Target** from the drop down list.
1. Under **Adobe Target**, select the appropriate configuration.

   <!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2019-01-10T04:09:45.308-0500

<p>6.5</p>

 -->

   <!-- 

Comment Type: draft

<p>Under <strong>Adobe Target</strong>, select the appropriate configuration, together with the required format option:<br /> </p>

 -->

   <!-- 

Comment Type: draft

<img imageRotate="0" src="assets/XF-Target-01.png" />

 -->

1. **Save & Close**.

## Exporting an Experience Fragment to Target {#exporting-an-experience-fragment-to-target}

>[!NOTE]
>
>For media assets, such as images, only a reference is exported to Target. The asset itself remains stored in AEM Assets and is delivered from the AEM publish instance.
>
>Due to this the Experience Fragment, with all related assets, needs to be published before exporting to Target.

To export an experience fragment from AEM to Target (after specifying the Cloud Configuration):

1. Navigate to the Experience Fragment console.
1. Select the Experience Fragment you would like to export to target.

   >[!NOTE]
   >
   >It has to be an Experience Fragment Web variation.

1. Tap/click **Export to Adobe Target**.

   >[!NOTE]
   >
   >If the Experience Fragment has already been exported, select **Update in Adobe Target**.

1. Tap/click **Export without publishing** or **Publish** as required.

   >[!NOTE]
   >
   >Selecting** Publish** will publish the experience fragment right away and send it to Target.

1. Tap/click **OK** in the confirmation dialog.

   Your experience fragment should now be in Target.

>[!NOTE]
>
>Alternatively, you can perform the export from the page editor, using comparable commands in the [Page Information](../../authoring/using/author-environment-tools.md#main-pars-title-21) menu.

## Using your Experience Fragments in Target {#using-your-experience-fragments-in-target}

After performing the preceding tasks, the experience fragment displays on the Offers page in Target. Please have a look at the [specific Target documentation](https://experiencecloud.adobe.com/resources/help/en_US/target/target/aem-experience-fragments.html) to learn about what you can achieve there.

## Deleting an Experience Fragment already exported to Target {#deleting-an-experience-fragment-already-exported-to-target}

Deleting an Experience Fragment that has already been exported to Target may cause problems if the fragment is already being used in an offer in Target. Deleting the fragment would render the offer unusable as the fragment content is being delivered by AEM.

To avoid such situations:

* If the Experience Fragment is not being currently used in an activity, AEM allows the user to delete the fragment without a warning message.
* If the Experience Fragment is currently in use by an activity in Target, an error message warns the AEM user about possible consequences that deleting the fragment will have on the activity.

  The error message in AEM does not prohibit the user from (force-)deleting the Experience Fragment. If the Experience Fragment is deleted:

    * The Target offer with AEM Experience Fragment may show undesired behavior

        * The offer will likely still render, as the Experience Fragment HTML was pushed to Target
        * Any references in the Experience Fragment may not work correctly if referenced assets were deleted in AEM as well.

    * Of course, any further modifications to the Experience Fragment are impossible as the Experience Fragment does not exist anymore in AEM.

