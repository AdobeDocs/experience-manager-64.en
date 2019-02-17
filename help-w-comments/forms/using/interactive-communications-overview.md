---
title: Interactive Communications Overview
seo-title: Interactive Communications Overview
description: This article includes overview, sample use cases, creation workflow, and differences between Interactive Communication and letter.
seo-description: Interactive Communication key capabilities, sample use cases, creation workflow, and differences between Interactive Communication and Correspondence Management
uuid: 5809102b-c051-4e0e-9670-1c2b3aed5bd0
contentOwner: gtalwar
topic-tags: interactive-communications
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: introduction
discoiquuid: e0697485-7661-47ca-b37c-d84e7762df63
index: y
internal: n
snippet: y
---

# Interactive Communications Overview{#interactive-communications-overview}

This article includes overview, sample use cases, creation workflow, and differences between Interactive Communication and letter.

 ![](assets/correspondence-management-1.png)

Interactive Communications centralizes and manages the creation, assembly, and delivery of secure, personalized, and interactive correspondences such as business correspondence, documents, statements, benefit notices, marketing mails, bills, and welcome kits.

## Key capabilities {#key-capabilities}

Following are the key capabilities of Interactive Communications:

* Out-of-the-box integration with form data model to enable easy and streamlined access to back end databases and other CRM systems, such as MS® Dynamics
* Integrated authoring interface for print and web channels with ability to auto generate web channel from the print channel
* Charts to present information in easily understandable visual formats in print and web
* Document fragments support rule editor and form data model
* Agent user interface displays print and web preview of the Interactive Communication
* Drag-and-drop components to quickly construct print and web channels

## Sample use case {#sample-use-case}

The [Welcome kit for a credit card customer](../../forms/using/finance-reference-site-walkthrough.md#creditcardapplicationwalkthrough) sample use case showcases the capabilities of an Interactive Communication. 

<!--
Comment Type: annotation
Last Modified By: alvawb
Last Modified Date: 2018-05-07T16:17:19.146-0400
Broken link.
-->

## Interactive Communication creation  {#interactive-communication-creation}

![](assets/interactive_communication-01.jpg)

### Workflow {#workflow}

To create an Interactive Communication, have the [building blocks](#buildingblocks) for Interactive Communication ready and then complete the following steps:

1. Choose to [create an Interactive Communication](../../forms/using/create-interactive-communication.md).   

1. Specify the [form data model](../../forms/using/data-integration.md), prefill service, and [print and web channel templates](../../forms/using/web-channel-print-channel.md). You can choose to generate web channel from the print channel. 

1. Using the [drag-and-drop interface](../../forms/using/introduction-interactive-communication-authoring.md), add document fragments, images, components to print and web channel of the Interactive Communication as required. 
1. Configure the properties for the components inserted, such as the following:

    1. Images
    1. [Tables](../../forms/using/create-interactive-communication.md#tables) (Including Layout Fragments)
    1. [Charts](../../forms/using/chart-component-interactive-communications.md)
    1. [Document fragments](../../forms/using/create-interactive-communication.md#documentfragmentproperties)

1. Preview print and web channels and, if required, edit the Interactive Communication. 
1. The agent uses the Agent UI to [prepare the Interactive Communication](../../forms/using/prepare-send-interactive-communication.md) for sending it to the recipient/post process.

### Building blocks {#buildingblocks}

Following are the building blocks required for creating an Interactive Communication:

* [Form data model](../../forms/using/data-integration.md)
* [Print and web channel templates](../../forms/using/web-channel-print-channel.md)
* [Document fragments](../../forms/using/document-fragments.md)
* Images
* [Themes](../../forms/using/themes.md) for the Web channel

## Interactive Communications Vs Correspondence Management {#interactive-communications-vs-correspondence-management}

Interactive Communication is the default and recommended approach to create customer communications. To continue using the letters creating in AEM 6.3 Forms and AEM 6.2 Forms, you need to [install a compatibility package](../../forms/using/compatibility-package.md). Following is a comparison between capabilities of Interactive Communication and letter. 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Capability</strong></td> 
   <td><strong>Interactive Communication</strong></td> 
   <td><strong>Letter</strong></td> 
  </tr>
  <tr>
   <td>Output</td> 
   <td>Print and Web</td> 
   <td>Print</td> 
  </tr>
  <tr>
   <td>Schema</td> 
   <td>Form data model </td> 
   <td>Data dictionary </td> 
  </tr>
  <tr>
   <td>Localization</td> 
   <td>Not supported in form data model</td> 
   <td>Supported in data dictionary</td> 
  </tr>
  <tr>
   <td>Rule editor</td> 
   <td>
    <ul> 
     <li>Text and condition support rule editor for creating inline conditions</li> 
     <li>Interactive Communication editor supports application of rules on components of the web channel</li> 
    </ul> </td> 
   <td>No UI for creation of conditional expression</td> 
  </tr>
  <tr>
   <td>Authoring</td> 
   <td>Drag-and-drop interface for constructing print and web channel</td> 
   <td>No drag-and-drop mechanism </td> 
  </tr>
  <tr>
   <td>Charts</td> 
   <td>Charts supported in print as well as web channel</td> 
   <td>Not supported</td> 
  </tr>
  <tr>
   <td>Themes</td> 
   <td>Uses themes to style web channel</td> 
   <td>Does not support themes</td> 
  </tr>
  <tr>
   <td>Auditing and Versioning</td> 
   <td>Not supported</td> 
   <td>Supported</td> 
  </tr>
  <tr>
   <td>Drafts and manage instance</td> 
   <td>Not supported</td> 
   <td>Supported</td> 
  </tr>
  <tr>
   <td>Batch processing</td> 
   <td>Supported </td> 
   <td>Supported</td> 
  </tr>
  <tr>
   <td>Agent signature</td> 
   <td>Not supported</td> 
   <td>Supported</td> 
  </tr>
  <tr>
   <td>Remote functions</td> 
   <td>Not supported</td> 
   <td>Supported</td> 
  </tr>
 </tbody>
</table>

