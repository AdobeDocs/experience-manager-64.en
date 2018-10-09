---
title: Deploying and Maintaining
seo-title: Deploying and Maintaining
description: null
seo-description: Learn how to get started with the AEM installation.
uuid: 7ecead18-805a-457c-9505-d6b926623c99
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/deploy
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 47.508-0400
cq-lastmodifiedby: mgulati
cq-lastreplicated: 2018-04-05T09 18 14.784-0400
cq-lastreplicatedby: trushton
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: deploying
cq-template: /apps/help/templates/article-3
discoiquuid: 72814db1-6d08-482f-8def-d12d75a5c07b
firstPublishExternalDate: 2017-10-31T16:17:59.261-0400
isreadyforlocalization: false
jcr-created: 2018-01-13T19 01 23.960-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-05T09:18:14.657-0400
lochandoffdate: 2018-04-30T03 26 47.508-0400
lr-lastreplicatedby: trushton@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Deploying and Maintaining
publishexternaldate: 2018-04-05T09 18 14.657-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/deploy.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy
sha1: 12d075e5d3f0ccf0d8a2ff17dac31b0db604b14a
topicBrowsingSortDate: 2018-04-05T09:18:14.657-0400
index: y
internal: n
snippet: y
translate: y
---

# Deploying and Maintaining

In this page you will find:

* [Basic Concepts](#BasicConcepts)

    * [What is AEM?](#WhatisAEM)
    * [Typical Deployment Scenarios](#TypicalDeploymentScenarios)

* [Getting Started](#GettingStarted)

    * [Prerequisites](#Prerequisites)
    * [Getting the Software](#GettingtheSoftware)
    * [Default Local Install](#DefaultLocalInstall)
    * [Author and Publish Installs](#AuthorandPublishInstalls)
    * [Unpacked Install Directory](#UnpackedInstallDirectory)
    * [Starting and Stopping](#StartingandStopping)

Once you have familiarized yourself with these basics, you will find in more advanced and detailed information in the following subpages:

* [Technical Requirements](technical-requirements.md)
* [Recommended Deployments](recommended-deploys.md)
* [Custom Standalone Install](custom-standalone-install.md)
* [Application Server Install](application-server-install.md)
* [Troubleshooting](troubleshooting.md)
* [Command Line Start and Stop](command-line-start-and-stop.md)
* [Configuring](configuring.md)
* [Upgrading to AEM 6.4](upgrade.md)
* [eCommerce](ecommerce.md)
* [Configuration How-To Articles](ht-deploy.md)
* [Web Console](web-console.md)
* [Troubleshooting Replication](troubleshoot-rep.md)
* [Best Practices](best-practices.md)
* [Deploying Communities](/content/help/en/experience-manager/6-4/communities/using/deploy-communities)
* [Introduction to the AEM Platform](platform.md)
* [Performance Guidelines](DO-NOT-DELETE-performance-guidelines-pdf.md)
* [Getting Started with AEM Mobile](/content/help/en/experience-manager/6-4/mobile/using/getting-started-aem-mobile)
* [Maintenance Release Vehicle Definitions](maintenance-release-vehicle-definitions.md)
* [What is AEM Screens?](aem-screens-introduction.md)

## Basic Concepts

### What is AEM?
Adobe Experience Manager is a web-based client-server system for building, managing and deploying commercial websites and related services. It combines a number of infrastructure-level and application-level functions into a single integrated package.

At the infrastructure level AEM provides the following:

* **Web Application Server**: AEM can be deployed in standalone mode (it includes an intergated Jetty web server) or as a web application within a third-party application server (WebLogic, WebSphere, etc).
* **Web Application Framework**: AEM incorporates the Sling Web Application Framework that simplifies the writing of RESTful, content-oriented web applications.
* **Content Repository**: AEM includes a Java Content Repository (JCR), a type of hierarchical database designed specifically for unstructured and semi-structured data. The repository stores not only the user-facing content but also all code, templates and internal data used by the application.

Building on this base, AEM also offers a number of application-level features for the management of:

* **Websites**
* **Mobile Applications**
* **Digital Publications**
* **Forms**
* **Digital Assets**
* **Communities**
* **Online Commerce**

Finally, customers can use these infrastructrue and application-level building blocks to create customized solutions by building applications of their own.

The AEM server is **Java-based** and runs on most operating systems that support that platform. All client interaction with AEM is done through a **web browser**.

### Typical Deployment Scenarios
In AEM terminology an "instance" is a copy of AEM running on a server. AEM installations usually involve at least two instances, typically running on separate machines:

* **Author**: An AEM instance used to create, upload and edit content and to administer the website. Once content is ready to go live, it is replicated to the publish instance.
* **Publish**: An AEM instance that serves the published content to the public.

These instances are identical in terms of installed software. They are differentiated by configuration only. In addition, most installations use a dispatcher:

* **Dispatcher**: A static web server (Apache httpd, Microsoft IIS, etc.) augmented with the AEM dispatcher module. It caches web pages produced by the publish instance to improve performance.

There are many advanced options and elaborations of this setup, but the basic pattern of author, publish and dispatcher is at the core of most deployments. We will begin by focusing on a relatively simple set up. Discussion of advanced deployment options will follow.

## Getting Started

### Prerequisites
While production instances are usually run on dedicated machines running an officially supported OS (see [Technical Requirements](technical-requirements.md)), the Experience Manager server will actually run on any system that supports [**Java Standard Edition 8**](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

For purposes of familiarization and for developing on AEM it is quite common to use an instance installed on your local machine running Apple OS X or desktop versions of Microsoft Windows or Linux.

On the client-side, AEM works with all modern browsers (**Microsoft Edge**, **Internet Explorer** 11, **Chrome **51+** **, **Firefox **47+, **Safari** 8+) on both desktop and tablet operating systems. See [Supported Client Platforms](technical-requirements.md#main-pars_title_17) for details.

### Getting the Software
Customers with a valid maintenance and support contract should have received a mail notification with a code and be able to download AEM from the [**Adobe Licensing Website**](https://licensing.adobe.com/). Business partners can request download access from [**spphelp@adobe.com**](mailto:spphelp@adobe.com).

The AEM software package is available in two foms:

* **cq-quickstart-6.4.0.jar:** A standalone executable *jar* file that includes everything needed to get up and running.

* **cq-quickstart-6.4.0.war: **A *war* file for deployment in a third-party application server.

In the following section we describe the **standalone installation**. For details on installing AEM in an application server see [Application Server Install](application-server-install.md).

### Default Local Install

1. Create an install directory on your local machine. For example:

   UNIX install location: **/opt/aem**

   Windows install location: **`C:\Program Files\aem`**

   Equally, it is common to install sample instances in a folder right on the desktop. In any case we will refer to this location generically as:

   `<aem-install>`

   *Note that path of the file directory must consist of only US ASCII characters.*

1. Place the the **jar** and **license **files in this directory:

   ```shell
   <aem-install>/
       cq-quickstart-6.4.0.jar
       license.properties
   ```

   If you do not provide a `license.properties` file, AEM will redirect your browser to a **Welcome** screen on startup, where you can enter a license key. You will need to request a valid license key from Adobe if you do not yet have one.

1. To start up the instance in a GUI environment, just double-click the **`cq-quickstart-6.4.0.jar`** file.

   Alternative, you can launch AEM from the command line. For a 32-bit Java VM enter the following:

   ```shell
       java -Xmx1024M -jar cq-quickstart-6.4.0.jar
   ```

   For a 64-bit VM, enter:

   ```shell
       java -XX:MaxPermSize=256m -Xmx1024M -jar cq-quickstart-6.4.0.jar
   ```

AEM will take a few minutes to unpack the jar file, install itself, and start up. The above procedure results in:

* an **AEM author** instance 
* running on **localhost** 
* on port **4502**

To access the instance point your browser to:

**`http://localhost:4502`**

The result in author instance will be automatically configured to connect to a **publish instance** on **`localhost:4503`**.

### Author and Publish Installs
The default install (an **author** instance on **`localhost:4502`**) can be changed simply by renaming the `jar` file before launching it for the first time. The naming pattern is:

**`cq-<instance-type>-p<port-number>.jar`**

For example, renaming the file to

**`cq-author-p4502.jar`**

and launching it will result in an author instance running on **`localhost:4502`**.

Similarly, renaming and launching the file

**`cq-publish-p4503.jar`**

will result in a publish instance running on **`localhost:4503`**.

You would install these two instances in, for example

`<aem-install>/author`and

**`<aem-install>/publish`**

For more details on customizing your installation see the following:

* [Custom Standalone Install](custom-standalone-install.md)
* [Run Modes](configure-runmodes.md)

### Unpacked Install Directory
When the quickstart jar is launched for the first time it will unpack itself into the same directory under a new sub-directory called `crx-quickstart`. You should end up with the following:

```xml
<aem-install>/
    license.properties
    cq-quickstart-6.4.0.jar
    crx-quickstart/
        app/
        bin/
        conf/
        launchpad/
        logs/
        metrics/        
        monitoring/
        opt/
        repository/
        threaddumps/
        eula-de_DE.html
        eula-en_US.html
        eula-fr_FR.html
        eula-ja_JP.html
        readme.txt
```

If the instance was installed from the GUI, then a browser window will open auomatically and a desktop application window will also open displaying the host and port of the instance and an on/off switch:

![](assets/screen_shot_2018-04-05at91504am1.png) 

### Starting and Stopping
Once AEM has unpacked itself and started up for the first time, double clicking on the jar file in the install directory simply starts the instance, it does not re-install it.

To stop the instance fom the GUI, simply click the **on/off** switch on the desktop application window.

You can also stop and start AEM from the command line. Assuming you have already installed the instance for the first time, the **command-line scripts** are located here:

**`<aem-install>/crx-quickstart/bin/`**

This folder contains the following Unix bash shell scripts:

* **`start`**: Starts the instance
* `stop`: Stops the instance
* **`status`**: Reports the Status of the instance
* **`quickstart`**: Used to configure start information, if necessary.

There are also equivalent **`bat`** files for Windows. For more detailed information see:

* [Command Line Start and Stop](command-line-start-and-stop.md)

AEM starts and automatically redirects your web browser to the appropriate page, usually the login page; for example:

`http://localhost:4502/`

![](assets/screen_shot_2018-04-03at15317pm1.png)

Once logged in, you have access to AEM. For further information, depending on the your role, see the following:

* [Authoring](/content/help/en/experience-manager/6-4/sites/authoring/user-guide) 
* [Administering](/content/help/en/experience-manager/6-4/sites/administering/user-guide)
* [Developing](/content/help/en/experience-manager/6-4/sites/developing/user-guide)
* [Managing](/content/help/en/experience-manager/6-4/managing/using/manage-reference)

## Advanced Deployment
The above section should give you a good understanding of the basics of AEM installation. However, installing a full production system of AEM can involve considerably more complexity. For full coverage of advanced installation see the following subpages:

* [Technical Requirements](technical-requirements.md)
* [Recommended Deployments](recommended-deploys.md)
* [Custom Standalone Install](custom-standalone-install.md)
* [Application Server Install](application-server-install.md)
* [Troubleshooting](troubleshooting.md)
* [Command Line Start and Stop](command-line-start-and-stop.md)
* [Configuring](configuring.md)
* [Upgrading to AEM 6.4](upgrade.md)
* [eCommerce](ecommerce.md)
* [Configuration How-To Articles](ht-deploy.md)
* [Web Console](web-console.md)
* [Troubleshooting Replication](troubleshoot-rep.md)
* [Best Practices](best-practices.md)
* [Deploying Communities](/content/help/en/experience-manager/6-4/communities/using/deploy-communities)
* [Introduction to the AEM Platform](platform.md)
* [Performance Guidelines](DO-NOT-DELETE-performance-guidelines-pdf.md)
* [Getting Started with AEM Mobile](/content/help/en/experience-manager/6-4/mobile/using/getting-started-aem-mobile)
* [Maintenance Release Vehicle Definitions](maintenance-release-vehicle-definitions.md)
* [What is AEM Screens?](aem-screens-introduction.md)

