---
title: Certificate types used by Acrobat Reader DC extensions 
seo-title: Certificate types used by Acrobat Reader DC extensions 
description: Learn about the certificate types used by Acrobat Reader DC extensions.
seo-description: Learn about the certificate types used by Acrobat Reader DC extensions.
uuid: 8286de5b-e0d2-499a-b54e-a57b0fb5f8f6
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 8b2f9293-d632-4b8f-ad9e-c6899c4ef01b
index: y
internal: n
snippet: y
---

# Certificate types used by Acrobat Reader DC extensions {#certificate-types-used-by-acrobat-reader-dc-extensions}

The Certificate Viewer provides the following information about the certificate:

* Certificate "friendly" name
* Certificate profiles
* Validity period
* Acrobat Reader DC extensions usage rights

## Certificate “friendly” name {#certificate-friendly-name}

The "friendly" name of a Acrobat Reader DC extensions certificate is a string that describes the properties of the certificate, as in the following example:

ARE 2D Barcode Full Production V6.1 P8 0002054

The string contains the following elements:

**Certificate type:** Describes the AEM forms modules that the certificate activates, and the level of activation, such as ARE 2D Barcode Full. For a list of the certificate types available, see the Type column in the table in the Certificate profiles section.

**Deployment type:** Indicates the intended use of the certificate, such as Production. The value can be Evaluation or Production. For a list of deployment types associated with each certificate type, see the Deployment type column in the table in the Certificate profiles section.

**Usage rights version:** Describes the version of the usage rights algorithm that the certificate can be used for, such as V6.1. This version does not signify the version of Acrobat or Acrobat Reader DC extensions.

**Profile code:** The profile code is a shorthand description of complete certificate properties, such as example, P8. For a list of the profile codes associated with each file type, see the Profile code column in the table in the Certificate Profiles section.

**Serial number:** A serial number is assigned to each certificate issued by Adobe, such as 0002054. Adobe Enterprise Support or an Adobe Enterprise account representative can use this serial number to trace the certificate to a specific product order or to an OEM relationship.

## Certificate profiles {#certificate-profiles}

The following table lists the certificate profiles that you may encounter when analyzing Acrobat Reader DC extensions certificates.

<table cellpadding="4" cellspacing="0"> 
 <thead align="left"> 
  <tr> 
   <th class="cellrowborder" id="d19e12660" valign="top" width="NaN%"><p>Profile code</p></th> 
   <th class="cellrowborder" id="d19e12663" valign="top" width="NaN%"><p>Type</p></th> 
   <th class="cellrowborder" id="d19e12666" valign="top" width="NaN%"><p>Validity period</p></th> 
   <th class="cellrowborder" id="d19e12669" valign="top" width="NaN%"><p>Deployment type</p></th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P1</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>SAP Production</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P2</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>SAP Internal Test</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>2 years</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Evaluation and test</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P3</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Acrobat Reader DC extensions, Production</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P4</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Acrobat Reader DC extensions, Internal Adobe Use</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>2 years</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P5</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Acrobat Reader DC extensions, Partner Integration</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>2 years</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Evaluation and test</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P6</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Acrobat Reader DC extensions, Evaluation</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>60 days</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Evaluation</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P8</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Forms, Production</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>P9</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Adobe Acrobat 7.x, Production</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>I10</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Forms; may be used by OEMs</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production and evaluation</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>I11</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Forms; may be used by OEMs</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production and evaluation</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>I12</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Signature only; may be used by OEMs</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production and evaluation</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>I13</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Offline Commenting only; may be used by OEMs</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production and evaluation</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>I14</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Commenting only; may be used by OEMs</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production and evaluation</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12660 " valign="top" width="NaN%"><p>I15</p></td> 
   <td class="cellrowborder" headers="d19e12663 " valign="top" width="NaN%"><p>Full permissions; may be used by OEMs</p></td> 
   <td class="cellrowborder" headers="d19e12666 " valign="top" width="NaN%"><p>Max</p></td> 
   <td class="cellrowborder" headers="d19e12669 " valign="top" width="NaN%"><p>Production and evaluation</p></td> 
  </tr> 
 </tbody> 
</table>

## Validity period {#validity-period}

Evaluation certificates are issued to customers and developers so that they can evaluate and develop sample applications for products. The validity period of these certificates is between 60 and 90 days. They expire at the end of the second month following the data of issue.

Partner Integration certificates are issued to Adobe business partners to support software development, integration, prototyping, and demonstration. These certificates are valid for two years from the date of issue.

Adobe Internal Use certificates are used within Adobe to support software development, integration, prototyping and demonstration. These certificates are valid for two years from the date of issue.

Production certificates are issued to customers who purchased Acrobat Reader DC extensions. These certificates are valid for the maximum period permitted by the certificate authority (CA), shown as *Max* in the Certificate Profiles table.

## Acrobat Reader DC extensions usage rights {#acrobat-reader-dc-extensions-usage-rights}

When you examine the Acrobat Reader DC extensions certificate in the Certificate Viewer, you can select the usage rights item from the Details tab (if configured) to see an itemized list of the Adobe Reader usage rights that the certificate can enable. The usage rights enabled on a particular document may be a subset of those enabled by the certificate.

If online commenting is required in a non-collaborative environment, contact Adobe Support for more information. The Mode property matches the deployment type and is either *production* or *evaluation*.

The permitted Acrobat Reader DC extensions usage rights consist of one or more specific elements. These elements are used in different combinations to achieve varieties of licensed product functionality. 

<table cellpadding="4" cellspacing="0"> 
 <thead align="left"> 
  <tr> 
   <th class="cellrowborder" id="d19e12897" valign="top" width="NaN%"><p>Usage rights element</p></th> 
   <th class="cellrowborder" id="d19e12900" valign="top" width="NaN%"><p>Capability enabled in Adobe Reader when viewing a rights-enabled PDF document</p></th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>FormFillInAndSave</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Fill in form fields and save files locally.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>FormImportExport</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Import and export form data as FDF, XFDF, XML, and XDP files.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>FormAddDelete</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Add, change, or delete fields and field properties on the PDF form.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>SubmitStandalone</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Submit data, by email or offline, to a server when it is not running in a browser session.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>SpawnTemplate</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Create pages from template pages within the same PDF form.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>Signing</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Digitally sign and save PDF documents, and clear digital signatures.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>AnnotModify</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Create and modify document annotations such as comments.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>AnnotImportExport</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Save annotations such as comments in a separate data file and load comments from a file.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>BarcodePlaintext</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Print a document with form data barcoded in an unencrypted form that does not require licensed server software to decode.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>AnnotOnline</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Upload and download annotations such as comments to and from an online document review and comment server.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>FormOnline</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Connect to web services or databases that are defined within a PDF form.</p></td> 
  </tr> 
  <tr> 
   <td class="cellrowborder" headers="d19e12897 " valign="top" width="NaN%"><p>EFModif</p></td> 
   <td class="cellrowborder" headers="d19e12900 " valign="top" width="NaN%"><p>Modify embedded file objects associated with the PDF document.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Acrobat Reader DC extensions usage rights can be licensed from Adobe only in certain combinations that work together. It is not possible to license these capabilities independently. For information about the available combinations of usage rights, contact an AEM forms account representative.

