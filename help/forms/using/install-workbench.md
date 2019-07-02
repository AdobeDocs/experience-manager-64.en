---
title: Install workbench
seo-title: Install workbench
description: Install workbench.
uuid: 
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 
---

# Install workbench {#install-workbench}

This document provides instructions for installing and configuring workbench. The installation program also installs Designer.

## About {#about}

This document is intended for administrators or developers who are responsible for installing, configuring, administering, or deploying Workbench. 
Also included is information needed to configure your system to support your upgraded Adobe® AEM forms® Enterprise Suite (ES) Update 1 (8.2.x) and Adobe® AEM forms® Enterprise Suite 2 (ES2) processes. 
The information provided is based on the assumption that anyone reading this document is familiar with Microsoft® Windows® operating system.

## Additional information {#additional-information}

The resources in this table can help you learn more about and get started using AEM Forms.
<table> 
 <tbody> 
  <tr> 
   <td><p><strong>For information about</strong></p> </td> 
   <td><p><strong>See</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>Procedural information for Workbench</p> </td> 
   <td><p>[Workbench Help](http://www.adobe.com/go/learn_aemforms_workbench_61)<br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>General information about AEM Forms and how it integrates with other Adobe products</p> </td> 
   <td><p>[AEM Forms Overview](http://adobe.com/go/learn_aemforms_introduction_65)<br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>A tutorial for creating a AEM Forms application and testing it in workspace</p> </td> 
   <td><p>[Creating your first AEM Forms Application](http://adobe.com/go/learn_aemforms_firstapp_ds_65)<br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>All the documentation available for AEM Forms</p> </td> 
   <td><p>[AEM Forms documentation](http://adobe.com/go/learn_aemforms_introduction_65)<br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Other services and products that integrate with AEM Forms</p> </td> 
   <td><p><a href="http://www.adobe.com/">www.adobe.com</a><br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Patch updates, technical notes, and additional information on this product version</p> </td> 
   <td><p>[Contact Adobe Enterprise Support](https://www.adobe.com/account/sign-in.supportportal.html)<br /> <br /> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The Flex Worksapce is deprecated for AEM Forms. It is available for the AEM Forms release.

## Before You Install {#before-you-install}

### Workbench installation overview {#workbench-installation-overview}

Workbench is an integrated development environment (IDE) that developers and form authors use to create automated business processes and forms. It is also used to manage the resources and services that the processes and forms use.
The following illustration depicts the Workbench installation including:
* Process Design using Workbench
* Form Design using Designer

>[!NOTE]
>
>The AEM Forms server requires a separate installation program. For more information refer to the AEM Forms on JEE installation documentation.

## System prerequisites {#system-prerequisites}

This section outlines the hardware and software requirements and supported platforms.

### Minimum hardware and software requirements {#minimum-hardware-software-requirements}

**Workbench**
The following requirements are recommended as the minimum:
Disk space for installation:
* 680 MB for Workbench only.
* 2.15 GB on a single drive for a full installation of Workbench, Designer, and the samples assembly.
* 400 MB for temporary install directories - 200 MB in the user \temp directory and 200 MB in the Windows temporary directory.

>[!NOTE]
>
>If all these locations reside on a single drive, there must be 1.5 GB of space available during installation. The files copied to the temporary directories are deleted when installation is complete.

* Hardware requirement: Intel® Pentium® 4 or AMD equivalent, 1 GHz processor.
* Download and install the latest version of Adobe AIR (from http://www.adobe.com) required for Community Help Client, integrated with Workbench.
* Java™ Runtime Environment (JRE) 6.0 update 22 or later updates to 6.0 *New for 10*.
* Minimum1024 X 768 pixels or greater monitor resolution with 16-bit color or higher.
* TCP/IPv4 or TCP/IPv6 network connection to the AEM Forms server.
* Install Visual C++ Redistributable runtime Packages 2012 32-bit.
* Install Visual C++ Redistributable runtime Packages 2013 32-bit.

>[!NOTE]
>
>If you have Adobe® Acrobat® X installed on your machine, ensure that you uninstall it before installing Workbench. You can reinstall Acrobat after installing Workbench.

>[!NOTE]
>
>You must have Administrative privileges to install Workbench. If you are installing using a non-administrator account, the installer will prompt you for the credentials for an appropriate account.

### Supported Platforms {#supported-platforms}
See the complete list of supported platforms for Workbench at [AEM Forms Supported Platforms](http://adobe.com/go/learn_aemforms_supportedplatforms_65).

## Designer installation considerations {#designer-installation-considerations}

By default, the Workbench installation includes a corresponding English-only version of Designer. If the Workbench installation application detects an existing version of Designer on your computer, the installation may terminate, and you will be required to remove the current version of Designer before you can continue.
The table below has a complete list of possible Designer installation scenarios that you may encounter, as well as any actions you must take, when installing Workbench.

<table> 
 <tbody> 
  <tr> 
   <td><p><strong>Version of Designer currently installed</strong></p> </td> 
   <td><p><strong>Required actions</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>Acrobat Pro or Acrobat Pro Extended (includes Designer)</p> </td> 
   <td><p>None. The Workbench installation detects an instance of Designer on your computer that was installed with either Acrobat Pro or Acrobat Pro Extended.
Different versions of Designer can coexist on the same system, for example Designer 8.2.x and 9.0.x. It is not necessary to uninstall the version of Designer installed with Acrobat 10 Pro or Acrobat 10 Pro Extended.
<br /> <br /> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Designer (stand-alone)</p> </td> 
   <td><p>None. The version of Designer included with Workbench is English-only. The Workbench installer will not reinstall a new version of Designer. Instead an updated version, bundled with the Workbench installer, will be patched. This also allows you to use your localized version of Designer within Workbench.<br /> <br /> </p> </td> 
  </tr> 
 </tbody> 
</table>

### To uninstall Designer (stand-alone) {#uninstall-designer-standalone}
1. Go to **Control Panel > Programs > Programs and Features**
1. In the Currently installed programs list, select **Adobe Designer**.
1. Click **Uninstall** and then click **Yes**.

### To uninstall Designer (stand-alone) on Windows 10 {#uninstall-designer-standalone-windows10}
1. Go to **Control Panel > Programs > Programs and Features**
1. In the Currently installed programs list, select **Adobe Designer**.
1. Click **Uninstall** and then click **Yes**.

### To uninstall Designer included with Acrobat Pro or Acrobat Pro Extended {#uninstall-designer-included-with-acrobatpro-or-acrobatextended}
1. Go to **Control Panel > Programs > Programs and Features**
1. In the Currently installed programs list, select **Adobe Acrobat Pro** or **Adobe Acrobat Pro Extended**.
1. Click **Change** and then click **Next**.
1. Select **Modify** and then click **Next**.
1. Select **Adobe Designer**, select **This feature will not be available**, and then click **Next**
1. Click **Update** and then click **Finish**

### To uninstall Designer included with Acrobat Pro or Acrobat Pro Extended on Windows 10 {#uninstall-designer-included-with-acrobatpro-or-acrobatextended-windows10}
1. Go to **Control Panel > Programs > Programs and Features**
1. In the Currently installed programs list, select **Adobe Acrobat Pro** or **Adobe Acrobat Pro Extended**.
1. Click **Change** and then click **Next**.
1. Select **Modify** and then click **Next**.
1. Select **Adobe Designer**, select **This feature will not be available**, and then click **Next**
1. Click **Update** and then click **Finish**

## Installing Workbench {#installing-workbench}

This chapter describes how to install Workbench.

### Installing and running Workbench {#installing-and-running-workbench}

Before you install Workbench, you must ensure that your environment includes the software and hardware required to run it (See section: Before You Install).

**To install and run Workbench:**






