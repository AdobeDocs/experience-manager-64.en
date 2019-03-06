---
title: Correspondence Management Configuration Properties
seo-title: Correspondence Management Configuration Properties
description: This topic explains how you can modify Asset Composer with solution-specific configurations. This topic details the properties you can edit, with their description, default values, and acceptable values.
seo-description: This topic explains how you can modify Asset Composer with solution-specific configurations. This topic details the properties you can edit, with their description, default values, and acceptable values.
uuid: b649c854-cab4-440a-b881-2c9e9e5b0e2a
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: 5ebf5cfb-f20f-4e25-a2b1-21556451e2ad
index: y
internal: n
snippet: y
---

# Correspondence Management Configuration Properties{#correspondence-management-configuration-properties}

To configure these properties, open the following URL in a browser: `http://<server>:<port>/<contextPath>/system/console/configMgr` and select **Correspondence Management Configurations**.

Correspondence Management has the following configuration properties:

<table border="1" cellpadding="4" cellspacing="0"> 
 <tbody> 
  <tr> 
   <th><p><strong>Property</strong></p> </th> 
   <th><p><strong>Description</strong></p> </th> 
   <th><p><strong>Default</strong></p> </th> 
   <th><p><strong>Acceptable values</strong></p> </th> 
  </tr> 
 </tbody> 
 <tbody> 
  <tr> 
   <td valign="top" width="NaN%"><p>Indentation</p> </td> 
   <td valign="top" width="NaN%">Indentation on modules<p> </p> </td> 
   <td valign="top" width="NaN%"><p>12.7mm</p> </td> 
   <td valign="top" width="NaN%"><p>Any number</p> </td> 
  </tr> 
  <tr> 
   <td>Number Minimum Width</td> 
   <td>Minimum width to be applied on the bullet/number field, when using numbered Lists apart from Roman numbers</td> 
   <td>8.0mm</td> 
   <td>Any number</td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Roman Numbers Minimum Width</p> </td> 
   <td valign="top" width="NaN%"><p>Minimum width to be applied on the bullet/number field, when using Roman numbers</p> </td> 
   <td valign="top" width="NaN%"><p>12.7mm</p> </td> 
   <td valign="top" width="NaN%"><p>Any number</p> </td> 
  </tr> 
  <tr> 
   <td>Rendition Type</td> 
   <td>The type of rendition the Create Correspondence application uses to render the letter preview. </td> 
   <td>HTML Rendition</td> 
   <td>HTML Rendition / PDF Rendition</td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable CCR PDF highlight</p> </td> 
   <td valign="top" width="NaN%"><p>Enables highlighting on PDF in Create Correspondence application</p> </td> 
   <td valign="top" width="NaN%"><p>true</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Target Highlight Type</p> </td> 
   <td valign="top" width="NaN%"><p>Target Highlight Type in the Create Correspondence application</p> </td> 
   <td valign="top" width="NaN%"><p>border</p> </td> 
   <td valign="top" width="NaN%"><p>border / fill / none</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Target Highlight Color</p> </td> 
   <td valign="top" width="NaN%"><p>Target Highlight Color in the Create Correspondence application</p> </td> 
   <td valign="top" width="NaN%"><p>90;155;245</p> </td> 
   <td valign="top" width="NaN%"><p>Any RGB color in format R;G;B</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Content Highlight Type</p> </td> 
   <td valign="top" width="NaN%"><p>Content Highlight Type in the Create Correspondence application</p> </td> 
   <td valign="top" width="NaN%"><p>Fill</p> </td> 
   <td valign="top" width="NaN%"><p>border / fill / none</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Content Highlight Color</p> </td> 
   <td valign="top" width="NaN%"><p>Content Highlight Color in the Create Correspondence application</p> </td> 
   <td valign="top" width="NaN%"><p>210;225;245</p> </td> 
   <td valign="top" width="NaN%"><p>Any RGB color in format R;G;B</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Field Highlight Type</p> </td> 
   <td valign="top" width="NaN%"><p>Field Highlight Type in the Create Correspondence application</p> </td> 
   <td valign="top" width="NaN%"><p>fill</p> </td> 
   <td valign="top" width="NaN%"><p>border / fill / none</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Field Highlight Color</p> </td> 
   <td valign="top" width="NaN%"><p>Field Highlight Color in the Create Correspondence application</p> </td> 
   <td valign="top" width="NaN%"><p>210;225;245</p> </td> 
   <td valign="top" width="NaN%"><p>Any RGB color in format R;G;B</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Application Time Out</p> </td> 
   <td valign="top" width="NaN%"><p>Application Time Out in seconds</p> </td> 
   <td valign="top" width="NaN%"><p>1200</p> </td> 
   <td valign="top" width="NaN%"><p>Any number</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>PDF document parameter name</p> </td> 
   <td valign="top" width="NaN%"><p>Parameter name for PDF document in post process</p> </td> 
   <td valign="top" width="NaN%"><p>inPDFDoc</p> </td> 
   <td valign="top" width="NaN%"><p>Any string variable name</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>XML data parameter name</p> </td> 
   <td valign="top" width="NaN%"><p>Parameter name for XML document (data) in post process</p> </td> 
   <td valign="top" width="NaN%"><p>inXMLDoc</p> </td> 
   <td valign="top" width="NaN%"><p>Any string variable name</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>XDP document parameter name</p> </td> 
   <td valign="top" width="NaN%"><p>Parameter name for XDP document sent to the post process</p> </td> 
   <td valign="top" width="NaN%"><p>inXDPDoc</p> </td> 
   <td valign="top" width="NaN%"><p>Any string variable name</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Redirect URL parameter name</p> </td> 
   <td valign="top" width="NaN%"><p>Parameter name for the redirect URL sent from the post process This value can be any string variable name</p> </td> 
   <td valign="top" width="NaN%"><p>redirectURL</p> </td> 
   <td valign="top" width="NaN%"><p>Any string variable name</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>PDF Submit Type</p> </td> 
   <td valign="top" width="NaN%"><p>PDF Submit Type (type of PDF generated on submitting from the Create Correspondence application)</p> </td> 
   <td valign="top" width="NaN%"><p>nonInteractive</p> </td> 
   <td valign="top" width="NaN%"><p>interactive / non-interactive</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Optimize Data Dictionary Instance</p> </td> 
   <td valign="top" width="NaN%"><p>Enables optimized transfer of Data Dictionary Instance b/w server and client</p> </td> 
   <td valign="top" width="NaN%"><p>true</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Auto Correct Inconsistencies </p> </td> 
   <td valign="top" width="NaN%"><p>When enabled, it automatically handles the possible inconsistencies in Letter Assignments</p> </td> 
   <td valign="top" width="NaN%"><p>true</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Use Configured Data Formats</p> </td> 
   <td valign="top" width="NaN%"><p>Controls whether to Use Configured Data Edit Formats and Data Display Format</p> </td> 
   <td valign="top" width="NaN%"><p>true</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Data Display Formats</p> </td> 
   <td valign="top" width="NaN%"><p>Specifies locale specific display format for data</p> </td> 
   <td valign="top" width="NaN%"><p>locale=en_US; dateFormat=dd-MM-yyyy; numberDecimalSeparator=.; numberGroupSeparator=,; numberUseGroupSeparator=truelocale=de_DE; dateFormat=dd-MM-yyyy; numberDecimalSeparator=,; numberGroupSeparator=.; numberUseGroupSeparator=truelocale=fr_FR; dateFormat=dd-MM-yyyy; numberDecimalSeparator=,; numberGroupSeparator= ; numberUseGroupSeparator=truelocale=ja_JP; dateFormat=dd-MM-yyyy; numberDecimalSeparator=.; numberGroupSeparator=,; numberUseGroupSeparator=true</p> </td> 
   <td valign="top" width="NaN%"><p>--</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Data Edit Format</p> </td> 
   <td valign="top" width="NaN%"><p>Edit format for data. This is used when writing data as String or parsing data from String</p> </td> 
   <td valign="top" width="NaN%"><p>locale=en_US; dateFormat=dd-MM-yyyy; numberDecimalSeparator=.; numberGroupSeparator=,; numberUseGroupSeparator=true</p> </td> 
   <td valign="top" width="NaN%">--<p> </p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Manage Letter Instances on Publish</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable the Manage Letter functionality (applicable only for Publish Server)</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality. When false, audit logs for all actions will be disabled</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Read Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for asset reads</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Create Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for asset create</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Update Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for asset update</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Revert Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for asset revert</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Publish Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for asset publish</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable SaveAsDraft Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for saving letter drafts</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Submit Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for letter submit</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Email Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for emailing letters</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Print Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for printing letters</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Custom Delivery Audit</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable audit functionality for custom delivery of letters</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Attachment documents parameter name</p> </td> 
   <td valign="top" width="NaN%"><p>Parameter name for Attachment documents sent to the post process</p> </td> 
   <td valign="top" width="NaN%"><p>inAttachmentDocs</p> </td> 
   <td valign="top" width="NaN%"><p>Any string variable name</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>CM User Root</p> </td> 
   <td valign="top" width="NaN%"><p>URL of the folder containing all Correspondence Management user assets</p> </td> 
   <td valign="top" width="NaN%"><p>--</p> </td> 
   <td valign="top" width="NaN%"><p>Valid folder location</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Letter Cache Size</p> </td> 
   <td valign="top" width="NaN%"><p>Specify the Maximum number of letters to be kept in cache.</p> <p>Changing this value will result in clean-up of 
     <g class="gr_ gr_107 gr-alert gr_gramm undefined Grammar only-ins replaceWithoutSep" data-gr-id="107">
       in-memory 
     </g> cache.</p> </td> 
   <td valign="top" width="NaN%"><p>100</p> </td> 
   <td valign="top" width="NaN%"><p>Any numeric value</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Enable Letter Cache</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable the letter cache.</p> <p>Changing this value will result in clean-up of 
     <g class="gr_ gr_110 gr-alert gr_gramm undefined Grammar only-ins replaceWithoutSep" data-gr-id="110">
       in-memory 
     </g> cache.</p> </td> 
   <td valign="top" width="NaN%"><p>true</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Data Elements Ordering</p> </td> 
   <td valign="top" width="NaN%"><p>Keeps data elements ordering in create correspondence interface as per their sequence in Letter</p> </td> 
   <td valign="top" width="NaN%"><p>true</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="NaN%"><p>Support Reload</p> </td> 
   <td valign="top" width="NaN%"><p>Enable/Disable reload support in letters rendered on server-side.</p> <p>Disabling this will improve letter render performance.</p> </td> 
   <td valign="top" width="NaN%"><p>false</p> </td> 
   <td valign="top" width="NaN%"><p>true / false</p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td>Temp Folder</td> 
   <td>Location of the temp folder.</td> 
   <td>acm.tpmFolder</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Remote Save</td> 
   <td>Saves the Letter Instances on the specified processing author.</td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>Compatibility Options</td> 
   <td>Compatibility options of the format configname:configvalue separated by comma.</td> 
   <td>acm.compatibilityOptions</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><p>Debug Directory </p> <p> </p> </td> 
   <td>File system folder location for debugging. If the directory does not 
    <g class="gr_ gr_106 gr-alert gr_gramm undefined Grammar multiReplace" data-gr-id="106">
      exists 
    </g>, no debug dumps will be generated.</td> 
   <td>acm.debugDirectory</td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

