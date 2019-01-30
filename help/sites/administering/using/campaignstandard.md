---
title: Integrating with Adobe Campaign Standard
seo-title: Integrating with Adobe Campaign Standard
description: null
seo-description: Integrating with Adobe Campaign Standard.
uuid: 48f64dc1-f761-4f61-a7ce-3e569421886f
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: b8c2ff33-3086-423a-9cbb-5352359aef09
index: y
internal: n
snippet: y
---

# Integrating with Adobe Campaign Standard{#integrating-with-adobe-campaign-standard}

>[!NOTE]
>
>This documentation describes how to integrate AEM with Adobe Campaign Standard, the subscription-based solution. If you are using Adobe Campaign 6.1, see [Integrating with Adobe Campaign 6.1](../../../sites/administering/using/campaignonpremise.md) for those instructions.

Adobe Campaign lets you manage email delivery content and forms directly in Adobe Experience Manager.

To use both solutions together at the same, you must first configure them to connect to one another. This involves configuration steps in both Adobe Campaign and Adobe Experience Manager. These steps are described in detail in this document.

Working with Adobe Campaign in AEM includes the ability to send email and forms via Adobe Campaign and is described at [Working with Adobe Campaign](../../../sites/authoring/using/campaign.md).

In addition, the following topics may be of interest when integrating AEM with [Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/en/home.html):

* [Best practices for email templates](../../../sites/administering/using/best-practices-for-email-templates.md)
* [Troubleshooting your Adobe Campaign integration](../../../sites/administering/using/troubleshooting-campaignintegration.md)

If you are extending your integration with Adobe Campaign, you may want to see the following pages:

* [Creating Custom Extensions](../../../sites/developing/using/extending-campaign-extensions.md)
* [Creating Custom Form Mappings](../../../sites/developing/using/extending-campaign-form-mapping.md)

## Configuring Adobe Campaign {#configuring-adobe-campaign}

Configuring Adobe Campaign involves the following:

1. Configuring the **aemserver** user.
1. Creating a dedicated external account.
1. Verifying the AEMResourceTypeFilter option.
1. Creating a dedicated delivery template.

>[!NOTE]
>
>To perform these operations, you must have the **administration** role in Adobe Campaign.

### Prerequisites {#prerequisites}

Make sure you have the following elements beforehand:

* [An AEM authoring instance](../../../sites/deploying/using/deploy.md#gettingstarted)
* [An AEM publishing instance](../../../sites/deploying/using/deploy.md#authorandpublishinstalls)
* [An Adobe Campaign instance](https://docs.adobe.com/content/docs/en/campaign/ACS.html)

<!--
Comment Type: remark
Last Modified By: (sarchiz)
Last Modified Date: 2017-11-30T04:59:27.621-0500
<p>The Campaign link should remain unchanged for now, as there's no helpx <br /> alternative. We'll have another look after the Campaign docs are <br /> migrated over.</p>
-->

>[!CAUTION]
>
>Operations detailed in the [Configuring Adobe Campaign](#configuringadobecampaign) and [Configuring Adobe Experience Manager](#configuringadobeexperiencemanager) sections are necessary for the integration functionalities between AEM and Adobe Campaign to work correctly.

### Configuring the aemserver user {#configuring-the-aemserver-user}

The **aemserver** user must be configured in Adobe Campaign. The **aemserver** is a technical user that will be used to connect the AEM server to Adobe Campaign.

Go to **Administration **&gt; **Users & Security **&gt; **Users**, and select the **aemserver** user. Click it to open the user settings.

* You have to set a password for this user. This cannot be done through the UI. This configuration must be done in REST by a technical administrator.
* You can assign specific roles to this user, such as **deliveryPrepare**, which allows the user to create and edit deliveries.

### Configuring an Adobe Experience Manager external account {#configuring-an-adobe-experience-manager-external-account}

You must configure an external account that allows you to connect Adobe Campaign to your AEM instance.

>[!NOTE]
>
>In AEM, be sure that you set the password for the campaign-remote user. You need to set this password to connect Adobe Campaign with AEM. Log in as administrator and in the user administration console, search for the campaign-remote user and click **Set Password**.

To configure an AEM external account:

1. Go to **Administration** &gt; **Application settings** &gt; **External accounts**.

   ![](assets/chlimage_1-276.png)

1. Select the default **aemInstance** external account or create a new one by clicking the **Create **button.
1. Select **Adobe Experience Manager **in the **Type **field and enter the access parameters used for your AEM authoring instance: server address, account name and password.

   >[!NOTE]
   >
   >Be sure that you do not add an ending **/** slash at the end of the URL or the connection will not work.

1. Make sure that the **Enabled** checkbox is selected, then click **Save** to save your modifications.

### Verifying the AEMResourceTypeFilter option {#verifying-the-aemresourcetypefilter-option}

The **AEMResourceTypeFilter **option is used to filter types of AEM resources that can be used in Adobe Campaign. This allows Adobe Campaign to retrieve AEM contents that are specifically designed to be used in Adobe Campaign only.

This option comes pre-configured; however, if you change this option, it may lead to a non-functioning integration.

To verify the **AEMResourceTypeFilter **option is configured:

1. Go to **Administration** &gt; **Application settings** &gt; **Options**.
1. In the list, you can ensure that the **AEMResourceTypeFilter** option is listed and that the paths are correct.

### Creating an AEM-specific email delivery template {#creating-an-aem-specific-email-delivery-template}

By default, the AEM feature is not enabled in Adobe Campaign's email templates. You can configure a new email delivery template that will be used to create emails with AEM content.

To create an AEM-specific email delivery template:

1. Go to **Resources** &gt; **Templates** &gt; **Delivery templates**.
1. **Enable selection** by clicking the checkmark in the action bar and selecting the existing **Standard email (mail)** default template, then duplicate** **it by clicking the **Copy** icon and clicking **Confirm**.****
1. Disable the selection mode by clicking the **x **and open the newly created **Copy of Standard email** **(mail)** template, then select **Edit properties** from the action bar of the template dashboard.

   You can modify the** **template's** Label**.****

1. In the properties **Content** section, change the **Content source** to **Adobe Experience Manager**. Then select the external account that was previously created and click **Confirm**.

   Save your modifications by clicking **Confirm **and clicking **Save.**

   Email deliveries created from this template will have the AEM content feature enabled.

   ![](assets/chlimage_1-277.png)

## Configuring Adobe Experience Manager {#configuring-adobe-experience-manager}

To configure AEM, you must do the following:

* Configure replication between instances.
* Connect AEM to Adobe Campaign.
* Configure the externalizer.

### Configuring replication between AEM instances {#configuring-replication-between-aem-instances}

Content created from the AEM authoring instance is first sent to the publishing instance. This publishing instance then transfers the content to Adobe Campaign. The replication agent must therefore be configured to replicate from the AEM authoring instance to the AEM publishing instance.

>[!NOTE]
>
>If you do not want to use the replication URL but instead use the public-facing URL, you can set the **Public URL** in the following configuration setting in the OSGi (**Tools** &gt; **Web Console** &gt; **OSGi Configuration &gt; AEM Campaign Integration - Configuration**):
>
>**Public URL:** com.day.cq.mcm.campaign.impl.IntegrationConfigImpl#aem.mcm.campaign.publicUrl

This step is also necessary to replicate certain authoring instance configurations into the publishing instance.

To configure replication between AEM instances:

1. From the authoring instance, select **AEM logo**&gt; **Tools **icon &gt; **Deployment** &gt; **Replication** &gt; **Agents on author**, then click **Default Agent**.

   ![](assets/chlimage_1-278.png)

   >[!NOTE]
   >
   >Avoid using localhost (that is a local copy of AEM) when configuring your integration with Adobe Campaign unless the publish and author instance are both on the same computer.

1.

   Click **Edit** then select the **Transport** tab.

1. Configure the URI by replacing **localhost** with the IP address or the address of the AEM publishing instance.

   ![](assets/chlimage_1-279.png)

### Connecting AEM to Adobe Campaign {#connecting-aem-to-adobe-campaign}

Before you can use AEM and Adobe Campaign together, you must establish the link between both solutions so that they can communicate.

1.

   Connect to your AEM authoring instance.

1. Select **Tools** &gt; **Operations** &gt; **Cloud** &gt; **Cloud Services**, then **Configure now** in the Adobe Campaign section.

   ![](assets/chlimage_1-280.png)

1. Create a new configuration by entering a **Title** and click **Create**, or choose the existing configuration that you want to link with your Adobe Campaign instance.
1. Edit the configuration so that it matches the parameters of your Adobe Campaign instance.

    * **Username**: **aemserver**, the Adobe Campaign AEM Integration package operator used to establish the link between the two solutions.
    
    * **Password**: Adobe Campaign aemserver operator password. You may have to re-specify the password for this operator directly in Adobe Campaign.
    * **API End Point**: Adobe Campaign instance URL.

1. Select **Connect to Adobe Campaign **and click **OK**.

   ![](assets/chlimage_1-281.png)

   >[!NOTE]
   >
   >After you [create your email and publish it](../../../sites/authoring/using/campaign.md), you need to re-publish the configuration onto your publish instance.

   ![](assets/chlimage_1-282.png)

>[!NOTE]
>
>If the connection fails, make sure you check the following:
>
>* You may encounter a certificate problem when using a secure connection to an Adobe Campaign instance (https). You will have to add the Adobe Campaign instance certificate to the **cacerts **file of your JDK.
>* In addition, see [Troubleshooting your AEM/Adobe Campaign Integration](../../../sites/administering/using/troubleshooting-campaignintegration.md).
>

### Configuring the externalizer {#configuring-the-externalizer}

You need to [configure the externalizer](../../../sites/developing/using/externalizer.md) in AEM on your author instance. The Externalizer is an OSGi service that lets you transform a resource path into an external and absolute URL. This service provides a central place to configure those external URLs and build them.

See [Configure the externalizer](../../../sites/developing/using/externalizer.md) for general instructions. For the Adobe Campaign integration, make sure you configure the publish server at `http://*<host>:<port>*/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl` not point to `localhost:4503` but to a server that is reachable by the Adobe Campaign console.

If it points to `localhost:4503` or another server that Adobe Campaign cannot reach, your images will not appear on the Adobe Campaign console.

![](assets/chlimage_1-283.png) 

<!--
Comment Type: draft

<h2>Advanced Configurations</h2>
-->

<!--
Comment Type: draft

<p>You can also perform some advanced configurations, namely:</p>
<ul>
<li>Manage personalization fields and blocks.</li>
<li>Deactivate a personalization block.</li>
<li>Manage target extension data.</li>
</ul>
-->

<!--
Comment Type: draft

<h3>Managing personalization fields and blocks</h3>
-->

<!--
Comment Type: draft

<p>The fields and blocks available to add personalization to your email content in AEM are managed by Adobe Campaign.</p>
<p>A default list is provided but can be modified. You can also add or hide personalization fields and blocks.</p>
-->

<!--
Comment Type: draft

<h4>Adding a personalization field</h4>
-->

<!--
Comment Type: draft

<p>To add a new personalization field to those that are already available, you have to extend the Adobe Campaign <strong>nms:seedMember</strong> schema as follows:</p>
-->

<!--
Comment Type: draft

<note type="caution">
<p>The field that you need to add must have already been added via a recipient schema extension (<strong>nms:recipient</strong>). For more information, see the <a href="https://docs.campaign.adobe.com/doc/AC6.1/en/CFG_Editing_schemas_Editing_schemas.html">Configuration</a> guide.</p>
</note>
-->

<!--
Comment Type: draft

<ol>
<li><p></p><p>Go to the <strong>Administration</strong> &gt; <strong>Configuration</strong> &gt; <strong>Data schemas</strong> node in the Adobe Campaign navigation.</p> <p></p> </li>
<li><p>Select <strong>New</strong>.</p> <img imageRotate="0" src="assets/chlimage_1-284.png" /></li>
<li><p>In the pop-up window, select <strong>Extend the data in the table using an extension schema</strong> and click <strong>Next</strong>.</p> <img imageRotate="0" src="assets/chlimage_1-285.png" /></li>
<li><p>Enter the different parameters of the extended schema:</p> <p></p>
<ul>
<li><strong>Schema</strong>: select the <strong>nms:seedMember</strong> schema. The other fields in the window are automatically completed.</li>
<li><strong>Namespace</strong>: personalize the namespace of the extended schema.</li>
</ul> <p></p> </li>
<li><p>Edit the XML code of the schema to specify the field that you want to add there. For more information on extending schemas in Adobe Campaign, refer to the <a href="https://docs.campaign.adobe.com/doc/AC6.1/en/CFG_Editing_schemas_Extending_a_schema.html">Configuration guide</a>.</p> </li>
<li><p></p><p>Save your schema then update the Adobe Campaign database structure via the <strong>Tools</strong> &gt; <strong>Advanced</strong> &gt; <strong>Update database structure</strong> menu in the console.</p> <p></p> </li>
<li><p>Disconnect then reconnect to the Adobe Campaign console to save your changes. The new field now appears in the list of personalization fields available in AEM.</p> </li>
</ol>
-->

<!--
Comment Type: draft

<h4>Example</h4>
-->

<!--
Comment Type: draft

<p>To add a <strong>Registration Number</strong> field, you must have the following elements:</p>
<ul>
<li>The <strong>nms:recipient</strong> schema extension named <strong>cus:recipient</strong> contains:</li>
</ul>
-->

<!--
Comment Type: draft

<codeblock class="syntax xml">
<element&nbsp;desc="Recipient&nbsp;table&nbsp;(profiles)"&nbsp;img="nms:recipient.png"&nbsp;label="Recipients"&nbsp;labelSingular="Recipient"&nbsp;name="recipient">!!discoiqbr!!!!discoiqbr!!&nbsp;&nbsp;<attribute&nbsp;dataPolicy="smartCase"&nbsp;desc="Recipient&nbsp;registration&nbsp;number"&nbsp;!!discoiqbr!!&nbsp;&nbsp;label="Registration&nbsp;Number"!!discoiqbr!!&nbsp;&nbsp;length="50"&nbsp;name="registrationNumber"&nbsp;type="string"/>!!discoiqbr!!!!discoiqbr!!</element>
</codeblock>
-->

<!--
Comment Type: draft

<p>The <strong>nms:seedMember</strong> schema extension named <strong>cus:seedMember</strong> contains:</p>
-->

<!--
Comment Type: draft

<codeblock class="syntax xml">
<element&nbsp;desc="Seed&nbsp;to&nbsp;insert&nbsp;in&nbsp;the&nbsp;export&nbsp;files"&nbsp;img="nms:unknownad.png"&nbsp;label="Seed&nbsp;addresses"&nbsp;labelSingular="Seed"&nbsp;name="seedMember">!!discoiqbr!!!!discoiqbr!!&nbsp;&nbsp;<element&nbsp;name="custom_nms_recipient">!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;<attribute&nbsp;name="registrationNumber"&nbsp;!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;template="cus:recipient:recipient/@registrationNumber"/>!!discoiqbr!!&nbsp;&nbsp;</element>!!discoiqbr!!!!discoiqbr!!</element>
</codeblock>
-->

<!--
Comment Type: draft

<p>The <strong>Registration Number</strong> field is now part of the available personalization fields:</p>
-->

<!--
Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-286.png" />
-->

<!--
Comment Type: draft

<h4>Hiding a personalization field</h4>
-->

<!--
Comment Type: draft

<p>To hide a personalization field among those that are already available, you must extend the Adobe Campaign <strong>nms:seedMember </strong>schema as detailed in the <a href="#addingapersonalizationfield">Adding a personalization field</a> section. Apply the following steps:</p>
-->

<!--
Comment Type: draft

<ol>
<li><p> </p> <p>Copy the field that you want to take from the <strong>nms:seedMember</strong> schema in the extended schema (<strong>cus:seedMember</strong> for example).</p> <p> </p> </li>
<li><p></p><p>Add the <strong>advanced="true"</strong> XML attribute to the field. It no longer appears in the list of personalization fields available in AEM.</p> <p></p> <p>For example, to hide the <strong>Middle Name</strong> field, the <strong>cud:seedMember</strong> schema must contain the following element:</p>
<codeblock class="syntax xml">
<element&nbsp;desc="Seed&nbsp;to&nbsp;insert&nbsp;in&nbsp;the&nbsp;export&nbsp;files"&nbsp;img="nms:unknownad.png"&nbsp;label="Seed&nbsp;addresses"&nbsp;labelSingular="Seed"&nbsp;name="seedMember">!!discoiqbr!!!!discoiqbr!!&nbsp;&nbsp;<element&nbsp;name="custom_nms_recipient">!!discoiqbr!!&nbsp;&nbsp;&nbsp;&nbsp;<attribute&nbsp;advanced="true"&nbsp;name="middleName"/>!!discoiqbr!!&nbsp;&nbsp;</element>!!discoiqbr!!!!discoiqbr!!</element>
</codeblock></li>
</ol>
-->

<!--
Comment Type: draft

<h3>Deactivating a personalization block</h3>
-->

<!--
Comment Type: draft

<p>To deactivate a personalization block among those available:</p>
-->

<!--
Comment Type: draft

<ol>
<li><p></p><p>Go to the <strong>Resources</strong> &gt; <strong>Campaign Management</strong> &gt; <strong>Personalization blocks</strong> node in the Adobe Campaign navigation.</p> <p></p> </li>
<li><p></p><p>Select the personalization block that you want to deactivate in AEM.</p> <p></p> </li>
<li><p>Clear the <strong>Visible in the customization menus</strong> checkbox and save your changes. The block no longer appears in the list of personalization blocks available in Adobe Campaign.</p> <img imageRotate="0" src="assets/chlimage_1-287.png" /></li>
</ol>
-->

<!--
Comment Type: draft

<h3>Managing target extension data</h3>
-->

<!--
Comment Type: draft

<p>You can also insert target extension data for personalization. Target extension data (also called 'Target Data'), comes from enriching or adding data in a query in a campaign workflow for example. For more information, refer to the <a href="https://docs.campaign.adobe.com/doc/AC6.1/en/WKF_Quick_start_Creating_queries.html">Creating queries</a> and <a href="https://docs.campaign.adobe.com/doc/AC6.1/en/WKF_Quick_start_Enriching_and_modifying_data.html">Enriching data</a> sections in the <strong>Workflow</strong> guide.</p>
-->

<!--
Comment Type: draft

<note type="note">
<p>The data in the target is only available if the AEM content is synchronized with an Adobe Campaign delivery. Refer to the <a href="../../../sites/authoring/using/campaign.md#synchronizingcontentcreatedinaemwithadeliveryfromadobecampaign">Synchronizing content created in AEM with a delivery from Adobe Campaign</a> section.</p>
</note>
-->

<!--
Comment Type: draft

<img imageRotate="0" src="assets/chlimage_1-288.png" />
-->

