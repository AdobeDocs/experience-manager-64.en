---
title: Interactive Communications configuration properties
seo-title: Interactive Communication configuration properties
description: Edit default configuration properties for Interactive Communications
seo-description: Edit default configuration properties for Interactive Communications
uuid: 8c04004c-8b0c-43f7-bedf-f586148603cc
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: interactive-communications
discoiquuid: fe89c1d6-ea18-4137-94ab-c65f95339d37
index: y
internal: n
snippet: y
---

# Interactive Communications configuration properties{#interactive-communications-configuration-properties}

Edit default configuration properties for Interactive Communications

Interactive Communications includes properties that are configured automatically after installing the [AEM Forms add-on](../../forms/using/installing-configuring-aem-forms-osgi.md) package. Interactive Communication authors can edit these default configuration properties using the **Adobe Experience Manager Web Console Configuration **page.

Open the **Adobe Experience Manager Web Console Configuration** page using the following URL:

http://&lt;server&gt;:&lt;port&gt;/&lt;contextPath&gt;/system/console/configMgr

The configuration properties include:

* [Document Fragments Configuration](#main-pars-header)
* [Create Correspondence Configuration](#main-pars-header-669055494)
* [Adaptive Form and Interactive Communication Web Channel Configuration](#main-pars-header-315118855)
* [Adaptive Form and Interactive Communication Web Channel Theme Configuration](#main-pars-header-1499644829)

## Document Fragments Configuration {#document-fragments-configuration}

Tap **Document Fragments** **Configuration** on the **Adobe Experience Manager Web Console Configuration** page to view the configuration properties for document fragments.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Property</td> 
   <td>Description</td> 
   <td>Default</td> 
   <td>Acceptable values</td> 
  </tr> 
  <tr> 
   <td>Data Display Formats</td> 
   <td>Locale-specific display format for fields, variables, and form data model elements available while creating an Interactive Communication for Print and Web channels.</td> 
   <td> 
    <ul> 
     <li>locale = en_US, de_DE, fr_FR, and ja_JP</li> 
     <li>dateFormat = dd-MM-yyyy</li> 
     <li>numberDecimalSeparator = .</li> 
     <li>numberGroupSeparator = ,</li> 
     <li>numberUseGroupSeparator = true</li> 
    </ul> </td> 
   <td><p>--</p> </td> 
  </tr> 
  <tr> 
   <td>Indentation</td> 
   <td>The width of single unit of indentation applied to text in list document fragments.</td> 
   <td>12.7mm</td> 
   <td>Number</td> 
  </tr> 
  <tr> 
   <td>Roman Numbers Minimum Width</td> 
   <td>Minimum width to be applied to the bullet or number field, when using roman numbers in list document fragments. </td> 
   <td>12.7mm</td> 
   <td>Number</td> 
  </tr> 
  <tr> 
   <td>Number Minimum Width</td> 
   <td>Minimum width to be applied to the bullet or number field, when using numbered lists apart from roman numbers in list document fragments.</td> 
   <td>8.0mm</td> 
   <td>Number</td> 
  </tr> 
 </tbody> 
</table>

## Create Correspondence Configuration {#create-correspondence-configuration}

Tap **Create Correspondence** **Configuration** on the **Adobe Experience Manager Web Console Configuration** page to view the configuration properties for Agent UI.

| Property |Description |Default |Acceptable values |
|---|---|---|---|
| Show Resolved Content for editing |Select the checkbox to show resolved content (actual values instead of placeholders) while editing text module on the Agent UI. |Not selected |Not applicable |
| Apply Watermark during preview |Select the checkbox to apply watermark to Print channel of Interactive Communication in Preview mode. |Not selected |Not applicable |

## Adaptive Form and Interactive Communication Web Channel Configuration {#adaptive-form-and-interactive-communication-web-channel-configuration}

Tap **Adaptive Form and Interactive Communication Web Channel Configuration** on the **Adobe Experience Manager Web Console Configuration** page to view the configuration properties for Adaptive Forms and Interactive Communications Web channel. The following table describes the properties related to Interactive Communications:

| Property |Description |Default |Acceptable values |
|---|---|---|---|
| Show placeholder |Select the checkbox to enable the display of placeholders for fields included in adaptive forms and Interactive Communications. |Selected |Not applicable |
| Maximum cache entries |Set the maximum number of adaptive forms and Interactive Communications that can be retrieved using the cache memory.  |100 |Number |
| Make file name unique |Select the checkbox to have unique names for files included as attachments in Adaptive Forms and Interactive Communications. |Not selected |Not applicable |

## Adaptive Form and Interactive Communication Web Channel Theme Configuration {#adaptive-form-and-interactive-communication-web-channel-theme-configuration}

Tap **Adaptive Form and Interactive Communication Web Channel Theme Configuration** on the **Adobe Experience Manager Web Console Configuration** page to view the configuration properties for Adaptive Forms and Interactive Communications Web channel themes.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Property</td> 
   <td>Description</td> 
   <td>Default</td> 
   <td>Acceptable values</td> 
  </tr> 
  <tr> 
   <td>Font List Name</td> 
   <td>List of fonts that are available to use while creating Adaptive Forms and Interactive Communications.</td> 
   <td><p>Georgia</p> <p>Book Antiqua</p> <p>Times New Roman</p> <p>Arial</p> <p>Arial Black</p> <p>Impact</p> <p>Palatino Linotype</p> </td> 
   <td>All valid Adobe server fonts</td> 
  </tr> 
 </tbody> 
</table>

