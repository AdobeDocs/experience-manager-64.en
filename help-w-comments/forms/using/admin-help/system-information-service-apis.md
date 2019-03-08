---
title: System information Service APIs
seo-title: System information Service APIs
description: This document provides detailed information about the APIs provided by the the system information service.
seo-description: This document provides detailed information about the APIs provided by the the system information service.
uuid: 3c679399-495a-4c5a-8b9a-14700716fc83
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/system_information_service
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: c615b3b1-4a22-49de-9e01-d8707395bf3a
index: y
internal: n
snippet: y
---

# System information Service APIs{#system-information-service-apis}

The system information service provides a set of REST APIs to retrieve information. The following table provides detailed information about the APIs:

<table cellpadding="4" cellspacing="0">
 <thead align="left">
  <tr>
   <th class="row-nocellborder" id="d19e32321" valign="top" width="NaN%"><p>Name</p></th> 
   <th class="row-nocellborder" id="d19e32324" valign="top" width="NaN%"><p>URL</p></th> 
   <th class="cellrowborder" id="d19e32327" valign="top" width="NaN%"><p>Descrption</p></th> 
  </tr> 
 </thead> 
 <tbody>
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.properties</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/SystemInfo.properties</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>This API is a wrapper for <a href="http://docs.oracle.com/javase/6/docs/api/java/lang/System.html#getProperties()">system.getProperties</a> Java API. It retrieves configuration of the current working environment. </p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.envVar</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.envVar</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves all the environment variables of the host operating system. </p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.logs</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.logs</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Downloads a zip file that contains application server logs. </p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.config</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.config</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves all the content of the config.xml file. </p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.services</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.services</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves status and configuration parameters of AEM forms services.</p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.vitalDetails</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.vitalDetails</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves server uptime, JVM arguments, system memory, heap size, operating system name, number of active threads, and thread count. </p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.coreSettings</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.coreSettings</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves values of following properties:</p>
    <ul>
     <li><p>AdobeTempDir</p></li>
     <li><p>AdobeServerFontDir</p></li>
     <li><p>CustomerFontDir</p></li>
     <li><p>GlobalDocumentStorageRootDir</p></li>
     <li><p>DefaultDocumentMaxInlineSize</p></li>
     <li><p>DefaultDocumentDisposalTimeout</p></li>
     <li><p>EnableDocumentDBStorage</p></li>
     <li><p>GlobalDocumentStorageUseNetworkShare</p></li>
     <li><p>EnableFIPS</p></li>
     <li><p>EnableWSDL</p></li>
     <li><p>DataServicesConfigFile </p></li>
     <li><p>EnableRDS</p></li>
    </ul><p></p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.database</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.database</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves detailed information about the database.</p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.licenseInfo</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.licenseInfo</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves version and license information of installed AEM forms components. </p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfNo.serverConfig</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.serverConfig</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Downloads configuration files of the host application server. </p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.threads?delay=[n]&amp;iterations=[n]</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.threads?delay=[n]&amp;iterations=[n]</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>Retrieves count and stack trace of active threads. It accepts following parameters:</p>
    <ul>
     <li><p>iterations= [n]: Specifies the count of iterations. Replace n with a number. </p></li>
     <li><p>Delay= [n]: Specifies the number of milliseconds to wait before starting the next iteration. </p></li>
    </ul><p></p></td> 
  </tr> 
  <tr>
   <td class="row-nocellborder" headers="d19e32321 " valign="top" width="NaN%"><p>SystemInfo.info</p></td> 
   <td class="row-nocellborder" headers="d19e32324 " valign="top" width="NaN%"><p>http://[server]:[port]/rest/services/ SystemInfo.info</p></td> 
   <td class="cellrowborder" headers="d19e32327 " valign="top" width="NaN%"><p>This API is a wrapper for all of the system information service APIs. Internally, it runs all system information APIs and downloads information in zip format. </p><p><i><strong>note</strong>: The SystemInfo.info does not provide count and stack trace of active threads. </i></p></td> 
  </tr> 
 </tbody> 
</table>

