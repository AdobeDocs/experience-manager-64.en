---
title: Technical Requirements
seo-title: Technical Requirements
description: null
seo-description: A list of the supported client and server platforms for AEM.
uuid: 6e38ddef-fc84-4fc3-b0dd-1c1ae0c4ad27
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/technical-requirements
contentOwner: msm-service
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-07-06T06 30 46.052-0400
cq-lastmodifiedby: khsingh
cq-lastreplicated: 2018-07-06T06 30 46.081-0400
cq-lastreplicatedby: khsingh
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: platform
cq-template: /apps/help/templates/article-3
discoiquuid: e175b0a1-7ff6-4a0f-9ecb-bc641362e6de
firstPublishExternalDate: 2017-10-31T16:17:33.841-0400
isreadyforlocalization: false
jcr-created: 2018-03-06T08 01 43.081-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-07-06T06:30:46.047-0400
lochandoffdate: 2018-04-30T03 29 13.934-0400
lr-lastreplicatedby: khsingh@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/platform;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/platform
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Technical Requirements
publishexternaldate: 2018-07-06T06 30 46.047-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/technical-requirements.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/technical-requirements
sha1: 87318123bc4fef8ab47077d7fbdcf9a4e13d0de2
topicBrowsingSortDate: 2018-07-06T06:30:46.047-0400
index: y
internal: n
snippet: y
---

# Technical Requirements

Adobe supports Adobe Experience Manager (AEM) on the platforms as detailed in the following information in this document.

For any issues that are specifically related to the platform itself, please contact the platform vendor directly.

>[!NOTE]
>
>Depending upon the platform on which you install AEM, there could be different sets of requirements for user management.

## Prerequisites
Minimum requirements for installing Adobe Experience Manager:

* Installed Java Platform, Standard Edition JDK, or other supported [Java Virtual Machines](#JavaVirtualMachines)
* Experience Manager Quickstart file (Standalone JAR or web-application deployment WAR)

### Minimum Sizing Requirements
Minimum requirements for running Adobe Experience Manager:

* 5 GB free disk space in the installation directory
* 2 GB memory

>[!NOTE]
>
>* Digital asset use cases need more base memory. See [Deploying and Maintaining](deploy.md#main-pars_title_1) for details.
>* [AEM Forms add-on package](/content/help/en/experience-manager/6-4/forms/using/installing-configuring-aem-forms-osgi) requires 15 GB of temporary space.  
>

Please see the [Hardware Sizing Guidelines](/content/help/en/experience-manager/6-4/managing/using/hardware-sizing-guidelines) for further information.

### Support Levels
This document lists the supported client and server platforms for Adobe Experience Manager. Adobe provides several levels of support, both for recommended configurations and other configurations.

### Supported Configurations
Adobe recommends these configurations and provides full support as part of the standard software maintenance agreement.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Support Level</td> 
   <td>Description<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>A: Supported</strong></td> 
   <td>Adobe provides full support and maintenance for this configuration. This configuration is covered by Adobe's quality assurance process.</td> 
  </tr> 
  <tr> 
   <td><strong>R: Restricted Support</strong></td> 
   <td>To ensure our customers project success, Adobe provides full support within a restricted support program, which requires that specific conditions are met. R-level support requires a formal customer request and confirmation by Adobe. For more informations, please contact Adobe Customer Care.</td> 
  </tr> 
 </tbody> 
</table>

### Unsupported Configurations

| Support Level |Description |
|---|---|
| **Z: Not supported** |The configuration is not supported. Adobe does not make any statements about whether the configuration works, and does not support it. |

## Supported Platforms

### Java Virtual Machines
The application requires a Java Virtual Machine to run, which is provided by the Java Development Kit (JDK) distribution.

Adobe Experience Manager operates with the following versions of the Java Virtual Machines:

>[!CAUTION]
>
>It is recommended to track the Security Bulletins from the Java vendor to ensure the safety and security of production environments and install the latest Java Updates.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td>Platform</td> 
   <td>Support Level<br /> </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 10 JDK [1]</td> 
   <td>Z: Not supported </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 9 JDK [1]</td> 
   <td>Z: Not supported</td> 
  </tr> 
  <tr> 
   <td><strong>Oracle Java SE 8 JDK - 64bit</strong></td> 
   <td>A: Supported<br /> </td> 
  </tr> 
  <tr> 
   <td>IBM J9 VM - build 2.9, JRE 1.8.0 [2]</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>IBM J9 VM - build 2.8, JRE 1.8.0 [2]</td> 
   <td>A: Supported</td> 
  </tr> 
 </tbody> 
</table>

1. Oracle has moved to a "Long Term Support" (LTS) model for Oracle Java SE products. Java 9 and 10 are non-LTS releases by Oracle (see [Oracle Java SE support roadmap](http://www.oracle.com/technetwork/java/eol-135779.html)). Adobe will only provide support for LTS releases of Java to run AEM in production.   

1. The IBM JRE is only supported in conjunction with WebSphere Application Server.

### Storage & Persistence
Various options exist to deploy the repository of Adobe Experience Manager. See the following list for supported technologies and storage options.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Platform</strong></td> 
   <td><strong>Description</strong></td> 
   <td><strong>Support Level</strong></td> 
  </tr> 
  <tr> 
   <td><strong>File system with TAR files [1]</strong></td> 
   <td>Repository</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td><strong>File system with Datastore [1]</strong></td> 
   <td>Binaries</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Store binaries in TAR files on file system [1]</td> 
   <td>Binaries</td> 
   <td>Z: Not supported for production</td> 
  </tr> 
  <tr> 
   <td>Amazon S3</td> 
   <td>Binaries</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Microsoft Azure Blob Storage</td> 
   <td>Binaries</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>MongoDB Enterprise 3.6</td> 
   <td>Repository</td> 
   <td>Z: Not supported</td> 
  </tr> 
  <tr> 
   <td>MongoDB Enterprise 3.4 [2, 3]</td> 
   <td>Repository</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>MySQL 5.7</td> 
   <td>Forms Database</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>IBM DB2 11.1<br /> </td> 
   <td>Forms Database</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>IBM DB2 10.5</td> 
   <td>Repository &amp; Forms Database</td> 
   <td>R: Restricted Support (4)</td> 
  </tr> 
  <tr> 
   <td>Oracle Database 12c (12.1.x)</td> 
   <td>Repository &amp; Forms Database</td> 
   <td>R: Restricted Support</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2017</td> 
   <td>Forms Database</td> 
   <td>Z: Not supported (4)</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2016</td> 
   <td>Forms Database</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2014</td> 
   <td>Forms Database</td> 
   <td>R: Restricted Support (4)</td> 
  </tr> 
  <tr> 
   <td><strong>Apache Lucene (Quickstart built-in)</strong></td> 
   <td>Search Service</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Apache Solr</td> 
   <td>Search Service</td> 
   <td>A: Supported</td> 
  </tr> 
 </tbody> 
</table>

1. 'File System' includes block storage that is POSIX compliant. This includes network storage technology. Mind that file system performance might vary and influences the overall performance. It is recommended to load test AEM in combination with the network/remote file system.
1. MongoDB Sharding is not supported in AEM.
1. MongoDB Storage Engine WiredTiger is supported only.
1. Not supported for AEM Forms.

>[!NOTE]
>
>See [Deploying Communities](/content/help/en/experience-manager/6-4/communities/using/deploy-communities) for additional information regarding the AEM Communities capability.

>[!NOTE]
>
>MongoDB is third-party software and is not included in the AEM licensing package. For more information see the [MongoDB licensing policy](http://www.mongodb.org/about/licensing/) page.
>
>In order to get the most of your AEM deployment with MongoDB, Adobe recommends licensing the MongoDB Enterprise version in order to benefit from professional support. See [Recommended Deployments](recommended-deploys.md#main-pars_title_1707113207) for more information.
>
>The license includes a standard replica set, which is composed of one primary and two secondary instances that can be used for either the author or the publish deployments.
>
>In case you wish to run both author and publish on MongoDB, two separate licenses need to be purchased.
>
>Adobe Customer Care will assist qualifying issues related to the usage of MongoDB with AEM.
>
>For more information, see the [MongoDB for Adobe Experience Manager page](https://www.mongodb.com/lp/contact/mongodb-adobe-experience-manager).

>[!NOTE]
>
>Supported relational databases as listed above are third-party software and are not included in the AEM licensing package. 
>
>In order to run AEM 6.4 with a supported relational database, a separate support contract with a database vendor is required. Adobe Customer Care will assist qualifying issues related to the usage of relational databases with AEM 6.4.
>
>**Please note, that most relational databases are currently supported within Level-R on AEM 6.4, which comes with support criteria and a support program as stated in the Level-R description above.**

### Servlet Engines / Application Servers
Adobe Experience Manager can run either as a standalone server (the quickstart JAR file) or as web application within a third party application server (the WAR file).

Minimum Servlet API Version required: 3.1

| Platform |Support Level |
|---|---|
| **Quickstart built-in Servlet Engine (Jetty 9.3)** |A: Supported |
| Oracle WebLogic Server 12.2 (12cR2) |A: Supported |
| IBM WebSphere Application Server Continuous Delivery (LibertyProfile) with IBM JRE 1.8 |A: Supported |
| IBM WebSphere Application Server 9.0 |A: Supported |
| Apache Tomcat 8.5.x |A: Supported |
| JBoss EAP 7.1.0 with JBoss Application Server |A: Supported (1) |
| JBoss EAP 7.0.0 with JBoss Application Server |A: Supported |

1. Not supported for AEM Forms.

### Server Operating Systems
Adobe Experience Manager works with the following server platforms:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Platform</strong></td> 
   <td><strong>Support Level</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Linux, based on Red Hat distribution</strong></td> 
   <td>A: Supported (1)</td> 
  </tr> 
  <tr> 
   <td>Linux, based on Debian distribution incl. Ubuntu</td> 
   <td>A: Supported (4)</td> 
  </tr> 
  <tr> 
   <td>Linux, based on SUSE distribution</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Microsoft Windows Server 2016</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Microsoft Windows Server 2012 R2</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Oracle Solaris 11</td> 
   <td>A: Supported with limitations (3,5,7)<br /> R: Restricted Support for new contracts</td> 
  </tr> 
  <tr> 
   <td>IBM AIX 7.2</td> 
   <td>A: Supported with limitations (2,5,7)<br /> R: Restricted Support for new contracts</td> 
  </tr> 
 </tbody> 
</table>

1. Linux Kernel 2.6 and 3.x includes derivatives from Red Hat distribution, including Red Hat Enterprise Linux, CentOS, Oracle Linux and Amazon Linux. AEM form add-on features are only supported on CentOS 7 and Red Hat Enterprise Linux 6.5 and 7.
1. AEM Assets: Please see the section [Support for XMP metadata write-back](#SupportforXMPmetadatawriteback)
1. AEM Assets: No support for Dynamic Media Imaging. Dynamic Media Video is supported.  
1. AEM Forms is supported only on Ubuntu 16.04 LTS.
1. AEM Assets: No support for [Raw file transformation](/content/help/en/experience-manager/6-4/assets/using/camera-raw)
1. AEM Forms: No support for production environment
1. AEM Assets: No support for [enhanced PDF Rasterizer](/content/help/en/experience-manager/6-4/assets/using/aem-pdf-rasterizer)
1. AEM Forms: Not supported

<!-- 

Comment Type: annotation
Last Modified By: chuesler
Last Modified Date: 2018-04-03T15:53:20.011-0400

Ubuntu and Forms - what version is supported with AEM 6.4?

 -->

### Virtual & Cloud Computing Environments
Adobe Experience Manager is supported running in a virtual machine on cloud computing environments, such as Microsoft Azure and Amazon Web Services (AWS), in compliance with the technical requirements listed on this page, and according to Adobe’s standard support terms.

Adobe recommends using Adobe Managed Services to deploy AEM on Azure or AWS. Adobe Managed Services provides experts with experience and skills of deploying and operating AEM in these cloud computing environments. Please check out our [additional documentation on Adobe Managed Services](http://www.adobe.com/marketing-cloud/enterprise-content-management/managed-services-cloud-platform.html?aemClk=t).

In all other cases of deploying AEM on Azure or AWS, or any other cloud computing environment, support from Adobe will be contained to the virtual compute environment in compliance with the technical specifications listed on this page. Any reported issue relative to AEM running in any of these cloud environments will need to be reproducible independently from any cloud service specific to the cloud computing environment, unless the cloud service is specifically supported as part of the technical requirements listed on this page, for example Azure Blob storage or AWS S3.

For recommendations on how to deploy AEM on Azure or AWS, outside of Adobe Managed Services, we strongly recommend working directly with the cloud provider or Adobe partners supporting the deployment of AEM in the cloud environment of your choice. The selected cloud provider or partner will be responsible for the sizing specifications, design and implementation of the architecture., to meet your specific performance, load, scalability, and security requirements.

### Dispatcher Platforms (Web Servers)
The Dispatcher is the caching and load balancing component of AEM. Download the latest Dispatcher version from [Adobe PackageShare](https://www.adobeaemcloud.com/content/companies/public/adobe/dispatcher/dispatcher.html). Adobe Experience Manager 6.4 requires Dispatcher version 4.2.3 or higher.

The following web servers are supported for use with Dispatcher version 4.2.3:

| Platform |Support Level |
|---|---|
| **Apache httpd 2.4.x** [1,2] |A: Supported |
| Microsoft IIS 10 (Internet Information Server) |A: Supported |
| Microsoft IIS 8.5 (Internet Information Server) |A: Supported |

1. Web servers built on the basis of Apache httpd source code will have the same level of support as the version of httpd on which it is based. If in doubt, please ask Adobe for confirmation of the support level related to the respective server product. Following cases:

    1. The HTTP server was built using only official Apache source distributions, or
    1. The HTTP server was delivered as part of the operating system on which it is running. Examples: IBM HTTP Server, Oracle HTTP Server

1. Dispatcher is not available for Apache 2.4.x for Windows operating systems.

## Supported Client Platforms

### Supported Browsers for Authoring User Interface
The Adobe Experience Manager user interface works with the following client platforms. All browsers are tested with the default set of plug-ins and add-ons.

The AEM user interface is optimized for larger screens (typically notebooks and desktop computers) and tablet form factor (such as Apple iPad or Microsoft Surface). The phone form factor is not supported.

>[!NOTE]
>
>**Support for browsers with rapid release cycles:**
>
>Mozilla Firefox, Google Chrome and Microsoft Edge release updates every few months. Adobe is committed to provide updates for Adobe Experience Manager to maintain the support level as stated below with upcoming versions of these browsers.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Browser</strong></td> 
   <td><strong>Support for UI<br /> </strong></td> 
   <td><strong>Support for Classic UI</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Google Chrome (Evergreen)</strong></td> 
   <td>A: Supported</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Microsoft Edge (Evergreen)</td> 
   <td>A: Supported</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Microsoft Internet Explorer 11</td> 
   <td>A: Supported</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Mozilla Firefox (Evergreen)</td> 
   <td>A: Supported</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Mozilla Firefox last ESR [1]</td> 
   <td>A: Supported</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 11.x on macOS</td> 
   <td>A: Supported</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 10.x on macOS</td> 
   <td>A: Supported</td> 
   <td>A: Supported</td> 
  </tr> 
  <tr> 
   <td>Apple Safari on iOS 11.x</td> 
   <td>A: Supported [2]</td> 
   <td>Z: Not supported</td> 
  </tr> 
  <tr> 
   <td>Apple Safari on iOS 10.3</td> 
   <td>A: Supported [2]</td> 
   <td>Z: Not supported</td> 
  </tr> 
 </tbody> 
</table>

1. Extended Support Release of Firefox [Learn more about this on mozilla.org](https://www.mozilla.org/en-US/firefox/organizations/faq/)
1. support for Apple iPad

### Supported Browsers for Websites
Generally, browser support for websites rendered by AEM Sites depends on the implementation of AEM page templates, design and component output, and is therefore in control of the party implementing these parts.

>[!NOTE]
>
>Some browser-related exceptions for mobile clients are as listed below. These exceptions are only for AEM Forms:
>
>* Forms Portal is supported on Safari on iPad only.
>* Blackberry browser supports only adaptive forms.
>

### WebDAV Clients
**Microsoft Windows 7+  
**

To successfully connect with Microsoft Windows 7+ to an AEM instance that is not secured with SSL, basic authentication over unsecured network must be enabled in Windows. This requires a change in the Windows Registry of the WebClient:

1. Locate the registry subkey:

    * HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WebClient\Parameters

1. Add the BasicAuthLevel registry entry to this subkey using a value of 2 or more.

See [Microsoft Support KB 841215](http://support.microsoft.com/default.aspx/kb/841215).

To improve responsivness of the WebDav Client under Windows - see [Microsoft Support KB 2445570](http://support.microsoft.com/kb/2445570)

## Additional Platform Notes
This section provides special notes and more detailed information about running Adobe Experience Manager and its add-ons.

### IPv4 and IPv6
All elements of Adobe Experience Manager (Instance, Dispatcher) can be installed in both IPv4 and IPv6 networks.

Operation is seamless as no special configuration is required. You can simply specify an IP address using the format that is appropriate to your network type, if neccessary.

This means that when an IP address needs to be specified you can select (as required) from:

* an IPv6 address  
  for example `http://[ab12::34c5:6d7:8e90:1234]:4502`  

* an IPv4 address  
  for example `http://123.1.1.4:4502`  

* a server name  
  for example, `http://www.yourserver.com:4502`

* the default case of `localhost` will be interpreted for both IPv4 and IPv6 network installations  
  for example, `http://localhost:4502`

### Requirements for AEM Dynamic Media Add-on
AEM Dynamic Media is disabled by default. See here to [enable Dynamic Media](/content/help/en/experience-manager/6-4/assets/using/config-dynamic#EnablingDynamicMedia).

With Dynamic Media enabled, the following additional technical requirements apply.

>[!NOTE]
>
>These system requirements **only** apply if you use Dynamic Media - Hybrid mode; Dynamic Media - Hybrid mode has an embedded image server, which is only certified on certain operating systems. 
>
>For Dynamic Media customers who run Dynamic Media - Scene7 mode (that is, **dynamicmedia_scene7** runmode), there are no additional system requirements; only the same system requirements as AEM. Dynamic Media - Scene7 mode architecture uses the cloud-based image service, not the service embedded in AEM.

#### Hardware
The following hardware requirements are applicable for both Linux and Windows:

* Intel Xeon or AMD Opteron CPU with at least 4 cores  
* 16GB of RAM minimum

#### Linux
If you are using Dynamic Media on Linux, the following prerequisites need to be met:

* RedHat Enterprise 7 or CentOS 7 and later with latest fix patches
* 64-bit Operating System
* Swapping disabled (recommended)
* SELinux disabled (See note that follows)

>[!NOTE]
>
>If the locale is set such that LC_CTYPE is not equal to en_US.UTF-8, it will prevent dynamic media from working. To see what its value is type "locale" at the command prompt. If it not set to that, then set the LC_CTYPE environment variable to the empty string by typing "export LC_CTYPE=" before running AEM.

>[!NOTE]
>
>**Disabling SELinux:** Image Serving does not work with SELinux turned on. This option is enabled by default. To remedy this issue, edit the **/etc/selinux/config** file and change the SELinux value from:
>
>`SELINUX=enforcing`** **to** ** `SELINUX=disabled`

>[!NOTE]
>
>**NUMA Architecture:** Systems with processors featuring AMD64 and Intel EM64T are typically configured as non-uniform memory architecture (NUMA) platforms, which means that the kernel constructs multiple memory nodes at boot-time rather than constructing a single memory node.
>
>The multiple node construct can result in memory exhaustion on one or more of the nodes before other nodes become exhausted. When memory exhaustion happens the kernel can decide to kill processes (for example, the Image Server or Platform Server) even though there is available memory.
>
>Therefore, Adobe recommends that if you are running such a system that you turn off NUMA using the **numa=off** boot option to avoid the kernel killing these processes.

>[!NOTE]
>
>**Hostname of server must be resolvable:** Make sure that the hostname of the server is resolvable to an IP address. If that is not possible, please add the fully qualified hostname and the IP address to **/etc/hosts**:
>
>`<ip address> <fully qualified hostname>`

#### Windows

* Microsoft Windows Server 2016
* Swap space equal to at least twice the amount of physical memory (RAM)

To use Dynamic Media on Windows, Microsoft Visual Studio 2010, 2013, and 2015 redistributables for x64 and x86 must be installed.

x64

* The Microsoft Visual Studio 2010 redistributable can be found at [http://www.microsoft.com/en-us/download/details.aspx?id=13523](http://www.microsoft.com/en-us/download/details.aspx?id=13523)
* The Microsoft Visual Studio 2013 redistributable can be found at [https://www.microsoft.com/en-us/download/details.aspx?id=40784](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
* The Microsoft Visual Studio 2015 redistributable can be found at [https://www.microsoft.com/en-us/download/details.aspx?id=48145](https://www.microsoft.com/en-us/download/details.aspx?id=48145)

x86

* The Microsoft Visual Studio 2010 redistributable can be found at [https://www.microsoft.com/en-in/download/details.aspx?id=5555](https://www.microsoft.com/en-in/download/details.aspx?id=5555)
* The Microsoft Visual Studio 2013 redistributable can be found at [https://www.microsoft.com/en-in/download/details.aspx?id=40769](https://www.microsoft.com/en-in/download/details.aspx?id=40769)
* The Microsoft Visual Studio 2015 redistributable can be found at [https://www.microsoft.com/en-us/download/details.aspx?id=52685](https://www.microsoft.com/en-us/download/details.aspx?id=52685)

#### MacOS

* 10.9.x and later
* Only supported for trial and demo purposes

### Requirements for AEM Forms PDF Generator
AEM Forms PDF Generator supports only English, French, German, and Japanese versions ofsupported operating systems and applications.

In addition:

* PDF Generator requires Acrobat DC to perform the conversion.  
* AEM Forms supports only 32-bit editions of supported software.
* The OCR PDF (Searchable PDF), Optimize PDF, and Export PDF features are supported only on Microsoft Windows.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th valign="middle" width="35%"><p><strong>Product</strong></p> </th> 
   <th valign="middle" width="64%"><p><strong>Supported Formats for Conversion to PDF</strong></p> </th> 
  </tr> 
  <tr> 
   <td valign="top" width="35%"><p>Adobe® Acrobat® DC Pro</p> </td> 
   <td valign="top" width="64%"><p>XPS, image formats (BMP, GIF, JPEG, JPG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, DWG, DXF, and DWF</p> </td> 
  </tr> 
  <tr> 
   <td>Microsoft® Project 2016</td> 
   <td>MPP</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Publisher 2016</td> 
   <td>PUB</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office Visio 2016</td> 
   <td>VSD</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office 2016</td> 
   <td>DOC, DOCX, XLS, XLSX, PPT, PPTX, RTF, and TXT</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office 2013</td> 
   <td>DOC, DOCX, XLS, XLSX, PPT, PPTX, RTF, and TXT</td> 
  </tr> 
  <tr> 
   <td>Corel WordPerfect X7</td> 
   <td>WP, WPD<br /> </td> 
  </tr> 
  <tr> 
   <td>OpenOffice 4.1.2</td> 
   <td>ODT, ODP, ODS, ODG, ODF, SXW, SXI, SXC, SXD, XLS, XLSX, DOC, DOCX, PPT, PPTX, image formats (BMP, GIF, JPEG, JPG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, RTF, and TXT</td> 
  </tr> 
  <tr> 
   <td valign="top" width="35%"><p>OpenOffice 3.4</p> </td> 
   <td valign="top" width="64%"><p>ODT, ODP, ODS, ODG, ODF, SXW, SXI, SXC, SXD, XLS, XLSX, DOC, DOCX, PPT, PPTX, image formats (BMP, GIF, JPEG, JPG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, RTF, and TXT</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>PDF Generator supports only English, French, German, and Japanese versions of the supported operating systems and applications.
>
>In addition:
>
>* PDF Generator requires Acrobat DC to perform the conversion.
>* The HTML2PDF service is deprecated on AIX.
>* PDF Generator conversions for OpenOffice are supported only on Windows, Linux, and Solaris.
>* The OCR PDF, Optimize PDF, and Export PDF features are supported only on Windows.
>* Acrobat DC Pro installer is bundled with AEM Forms to enable PDF Generator functionality. Acrobat DC Pro should only be accessed programmatically by AEM Forms, during the term of the AEM Forms license, for use with AEM Forms PDF Generator. For more information, refer to AEM Forms product description as per your deployment ( [On-Premise](/content/help/en/legal/product-descriptions/adobe-experience-manager-on-premise) or [Managed Services](/content/help/en/legal/product-descriptions/adobe-experience-manager-managed-services))”
>

### Requirements for AEM Assets XMP metadata write-back
XMP write-back is supported and enabled for the following platforms and file formats:

**Operating Systems**

* Linux (32-bit, needs 32-bit application support on 64-bit systems). For steps to install 32-bit client libraries, see [How to enable XMP extraction and write-back on 64-bit RedHat Linux](/content/help/en/experience-manager/kb/enable-xmp-write-back-64-bit-redhat).  

* Windows Server
* Oracle Solaris  
* Mac OS X (64-bit)

**File Formats**

* JPEG
* PNG
* TIFF
* PDF
* INDD
* AI
* EPS

<!-- 

Comment Type: annotation
Last Modified By: chuesler
Last Modified Date: 2018-04-03T16:02:22.526-0400

is XMP write-back still only 32bit?

 -->

### Requirements for AEM Screens Player
The AEM Screens Player Version 3.3.x supports following operating systems:

* Microsoft Windows 10 Enterprise LTSB  
* Google Chome OS 62+
* Google Android 5.1.1 with updated Android System WebView Version 52+  
* Apple iOS 10.3+
* Apple macOS 10.12+

### Copyright, Licenses and Disclaimers
[Copyright, Licenses and Disclaimers](/content/help/en/experience-manager/6-4/release-notes/licenses)
