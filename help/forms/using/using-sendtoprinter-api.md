---
title: Using the sendToPrinter API
seo-title: Using the sendToPrinter API
description: null
seo-description: Using the sendToPrinter service to send a document to printer.
uuid: 187ff739-f492-4f40-8279-7cb44dd03658
acrolinxdate: 2016-05-31T06 44 37.943-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: yellow
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/using_sendtoprinter_api_admin_5e12de0b318c6865_2074_report.xml
acrolinxsentences: 45
acrolinxwords: 612
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: document_services
discoiquuid: 257d4c4d-da8e-4274-89a7-d3d455dacf1e
isreadyforlocalization: false
lastpublishqadate: 2015-06-17T05 31 44.939-0400
index: y
internal: n
snippet: y
---

# Using the sendToPrinter API{#using-the-sendtoprinter-api}

## Overview {#overview}

In AEM Forms, you can use the SendToPrinter service to send a document to printer. The SendToPrinter service supports the following printing access mechanisms:

* **Direct accessible printer** `: A printer that is installed on the same computer is called a direct accessible printer, and the computer is named printer host. This type of printer can be a local printer that is connected to the computer directly.`

* **Indirect accessible printer** `: The printer that is installed on a print server is accessed from other computers. Technologies such as the common UNIX® printing system (CUPS) and the Line Printer Daemon (LPD) protocol are available to connect to a network printer. To access an indirect accessible printer, specify the print server’s IP or host name. Using this mechanism, you can send a document to an LPD URI when the network has an LPD running. The mechanism lets you route the document to any printer that is connected to the network that has an LPD running.`  
  
  When you send a document to a printer, specify one of these printing protocols:

    * **CUPS** `: A printing protocol named common UNIX printing system. This protocol is used for UNIX operating systems and enables a computer to function as a print server. The print server accepts print requests from client applications, processes them, and sends them to configured printers. On the IBM AIX® operating system, usage of CUPS is not recommended.`
    
    * ``**DirectIP** `: A standard protocol for remote printing and managing print jobs. This protocol can be used locally or remotely. Print queues are not required.`
    
    * ``**LPD** `: A printing protocol named Line Printer Daemon protocol or Line Printer Remote (LPR) protocol. This protocol provides network print server functionality for UNIX-based systems.`
    
    * **SharedPrinter** `: A printing protocol that enables a computer to use a printer that is configured for that computer.`
    
    * **CIFS**: The Output service supports the Common Internet File System (CIFS) printing protocol.

## Using SendToPrinter Service {#using-sendtoprinter-service}

The table below lists:

* information about the printerName or printServer to use for various protocols.
* value or exception a printer returns for various combinations of Printer Server URI and Name of the printer

<table> 
 <tbody> 
  <tr> 
   <th><p>Protocol (Access Mechanism)</p> </th> 
   <th><p>Print Server URI (PrinterSpec.printServer)</p> </th> 
   <th>Name of the printer (PrinterSpec.printerName)</th> 
   <th><p>Result</p> </th> 
  </tr> 
 </tbody> 
 <tbody> 
  <tr> 
   <td>SharedPrinter</td> 
   <td>Any</td> 
   <td>Empty<br /> </td> 
   <td>Exception: Required argument sPrinterName cannot be empty.</td> 
  </tr> 
  <tr> 
   <td>SharedPrinter</td> 
   <td>Any</td> 
   <td>Invalid</td> 
   <td>An exception states that the printer cannot be found.</td> 
  </tr> 
  <tr> 
   <td>SharedPrinter</td> 
   <td>Any</td> 
   <td>Valid</td> 
   <td>Successful print job.</td> 
  </tr> 
  <tr> 
   <td>LPD</td> 
   <td>Empty</td> 
   <td>Any</td> 
   <td>an exception stating that the required argument sPrintServerUri cannot be empty.</td> 
  </tr> 
  <tr> 
   <td>LPD</td> 
   <td>Invalid</td> 
   <td>Empty<br /> </td> 
   <td>an exception stating that the required argument sPrinterName cannot be empty.</td> 
  </tr> 
  <tr> 
   <td>LPD</td> 
   <td>Invalid</td> 
   <td>Not empty</td> 
   <td>an exception stating that sPrintServerUri is not found.</td> 
  </tr> 
  <tr> 
   <td>LPD</td> 
   <td>Valid</td> 
   <td>Invalid</td> 
   <td>an exception stating that the printer cannot be found.</td> 
  </tr> 
  <tr> 
   <td>LPD</td> 
   <td>Valid</td> 
   <td>Valid</td> 
   <td>A successful print job.</td> 
  </tr> 
  <tr> 
   <td>CUPS</td> 
   <td>Empty<br /> </td> 
   <td>Any</td> 
   <td>an exception stating that the required argument sPrintServerUri cannot be empty.</td> 
  </tr> 
  <tr> 
   <td>CUPS</td> 
   <td>Invalid</td> 
   <td>Any</td> 
   <td> an exception stating that the printer cannot be found.</td> 
  </tr> 
  <tr> 
   <td>CUPS</td> 
   <td>Valid</td> 
   <td>Any</td> 
   <td>Successful print job.</td> 
  </tr> 
  <tr> 
   <td>DirectIP</td> 
   <td>Empty<br /> </td> 
   <td>Any</td> 
   <td> an exception stating that the required argument sPrintServerUri cannot be empty.</td> 
  </tr> 
  <tr> 
   <td>DirectIP</td> 
   <td>Invalid</td> 
   <td>Any</td> 
   <td>an exception stating that the printer cannot be found.</td> 
  </tr> 
  <tr> 
   <td>DirectIP</td> 
   <td>Valid</td> 
   <td>Any</td> 
   <td>Successful print job.</td> 
  </tr> 
  <tr> 
   <td>CIFS</td> 
   <td>Valid</td> 
   <td>Empty<br /> </td> 
   <td>Successful print job.</td> 
  </tr> 
  <tr> 
   <td>CIFS</td> 
   <td>Invalid</td> 
   <td>Any</td> 
   <td>an unknown error while printing using CIFS.</td> 
  </tr> 
  <tr> 
   <td>CIFS</td> 
   <td>Empty<br /> </td> 
   <td>Any</td> 
   <td>an exception stating that the required argument sPrintServerUri cannot be empty.</td> 
  </tr> 
 </tbody> 
</table>

## Authentication Support {#authentication-support}

Authentication is supported only for CIFS printing. To authenticate, provide the username/password/domain in PrinterSpec. You can encrypt a password using AEM Granite CyprtoSupport Service by performing the following steps:

1. Go to http://&lt;server&gt;:&lt;port&gt;/system/console.  

1. Go to **[!UICONTROL Main]** > **[!UICONTROL Crypto Support]**.  

1. Enter some Plain text, and click **[!UICONTROL Protect]**.

