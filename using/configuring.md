---
title: Basic Configuration Concepts
seo-title: Basic Configuration Concepts
description: null
seo-description: Learn how to configure AEM.
uuid: a7232966-4d46-4c76-8371-7740199edad2
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/configuring
contentOwner: msm-service
converted: true
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 38.979-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 40 00.924-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: d795db98-27d5-4f01-8d6a-ba7868252737
firstPublishExternalDate: 2017-10-31T16:18:13.076-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 01 37.055-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:40:00.014-0400
lochandoffdate: 2018-04-30T03 26 38.979-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Configuring
publishexternaldate: 2018-04-03T08 40 00.014-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configuring.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring
sha1: ecec3cf0dfdb2f2770fa5682e085f202775d8446
topicBrowsingSortDate: 2018-04-03T08:40:00.014-0400
index: y
internal: n
snippet: y
---

# Basic Configuration Concepts

Adobe Experience Manager (AEM) is installed with default settings for all parameters which allows it to run "out of the box." However, you can configure AEM for your own specific requirements.

There are many aspects of AEM that can be configured:

* Some are [commonly configured for every project installation](#PrimaryConfigurationConsiderations) and must be reviewed to confirm whether or not they are applicable to your project.
* [Further configurations](#FurtherConfigurationConsiderations) may be common though not imperative; related to features, or system performance and stability.
* Others are only required for certain optional features of AEM (these are documented together with the appropriate feature).

Depending on the specific configuration these changes can be made by using either the:

* **Adobe CQ Web Console** 
  This is a standard location for configuring OSGi bundles and services.   
  See [Configuring OSGi](configuring-osgi.md) for further details and recommended practices.

* **Repository** 
  A sub-set of OSGi configurations are available in the repository. This ensures that copying, or replicating, repository contents recreates identical configurations. You can also add your own configurations, dependent on run-mode, to the repository.  
  See [OSGi Configuration in the Repository](configuring-osgi.md#OSGiConfigurationintheRepository) and in particular [Adding a New Configuration to the Repository](configuring-osgi.md#AddingaNewConfigurationtotheRepository) for further details.

* **File system** 
  A few configuration files reside within the file system.

* **AEM WCM** 
  Various aspects can be configured within AEM WCM itself, many using the [Tools](/content/help/en/experience-manager/6-4/sites/administering/using/tools-consoles) console; for example, replication agents.

>[!NOTE]
>
>When working with Adobe Experience Manager, there are several methods of managing the configuration settings for OSGi services (console or repository nodes).
>
>See [Configuring OSGi](configuring-osgi.md) for full details.

>[!NOTE]
>
>Configuring AEM is straightforward, but you must be aware that:
>
>Certain changes can have a major impact on the application(s). For this reason, ensure you have the necessary experience and knowledge before you start to configure AEM, and make only the changes which you know are required. Any changes made via the OSGi console are **immediately** applied to the running system (no restart is required).

## Primary Configuration Considerations
This list details the primary areas that are commonly configured for every new project. Not all are needed, but the list must be read and reviewed to see what is applicable to your project.

The list gives a short overview of each configuration aspect, together with links to the pages that provide full details.

### Security Checklist
Several key configuration issues are listed in the [Security Checklist](/content/help/en/experience-manager/6-4/sites/administering/using/security-checklist). Please ensure that you read this and take any action necessary for your installation.

### Configuring the Default UI - Touch-Optimized or Classic
There are two UIs available for use in AEM:

* The Touch-optimized UI   
* The Classic UI

You can configure the UI you require using [Root Mapping](osgi-configuration-settings.md#DayCQRootMapping).

>[!NOTE]
>
>Further information about selecting the UI is available under [Selecting your UI](/content/help/en/experience-manager/6-4/sites/authoring/using/select-ui).

### IPv4 and IPv6
All elements of AEM (e.g. the repository, the Dispatcher, etc) can be installed in both IPv4 and IPv6 networks.

Operation is seamless as no special configuration is required, when needed you can simply specify an IP address using the format that is appropriate to your network type.

This means that when an IP address needs to be specified you can select (as required) from:

* an IPv6 address  
  for example `http://[ab12::34c5:6d7:8e90:1234]:4502`  

* an IPv4 address  
  for example `http://123.1.1.4:4502`  

* a server name  
  for example, `http://www.yourserver.com:4502`

* the default case of `localhost` will be interpreted for both IPv4 and IPv6 network installations  
  for example, `http://localhost:4502`

### Version Purging
In a standard installation AEM creates a new version of a page or node whenever you activate a page (after updating the content).You can also create additional versions on request using the **Versioning** tab of the sidekick. All these versions are stored in the repository and can be restored if required.

These versions are never purged, so the repository size will grow over time and therefore need to be managed.

See [Version Purging](version-purging.md) for full details, in particular [Version Manager](version-purging.md#VersionManager) for details of how to configure AEM to purge older versions when a new version is created.

### Logging
AEM offers you the possibility to configure:

* global parameters for the central logging service
* request data logging; a specialized logging configuration for request information
* specific settings for the individual services; for example, an individual log file and format for the log messages

See [Logging](configure-logging.md) for full details.

### Run Modes
Run modes allow you to tune your AEM instance for a specific purpose; for example author or publish, test, development or intranet, etc.

This is done by defining collections of configuration parameters for each run mode. A basic set of configuration parameters is applied for all run modes, you can then tune additional sets to the purpose of your specific environment. These are then applied as required.

All configuration settings are stored in the one repository and activated by setting the **Run Mode**.

See [Run Modes](configure-runmodes.md) for full details.

### Single Sign On
Single Sign On (SSO) allows a user to access multiple systems after providing authentication credentials (such as a user name and password) once. A separate system (known as the trusted authenticator) performs the authentication and provides Experience Manager with the user credentials. Experience Manager checks and enforces the access permissions for the user (i.e. determines which resources the user is allowed to access).

See [Single Sign On](single-sign-on.md) for further details.

### Resource Mapping
Resource mapping is used to define redirects, vanity URLs and virtual hosts for AEM.

For example, you can use these mappings to:

* Prefix all requests with `/content` so that the internal structure is hidden from the visitors to your website.
* Define a redirect so that all requests to the `/content/en/gateway` page of your website are redirected to `http://gbiv.com/`.

See [Resource Mapping](resource-mapping.md) for further details.

### Replication, Reverse Replication and Replication Agents
Replication agents are central to AEM as the mechanism used to:

* [Publish (activate)](/content/help/en/experience-manager/6-4/sites/authoring/using/publishing-pages) content from an author to a publish environment.
* Explicitly flush content from the Dispatcher cache.
* Return user input (for example, form input) from the publish environment to the author environment (under control of the author environment).

For further details see [Replication](replication.md).

### OSGi Configuration Settings
[OSGi](http://www.osgi.org/) is a fundamental element in the technology stack of AEM. It is used to control the composite bundles of AEM and their configuration.

See [OSGi configuration settings](osgi-configuration-settings.md) for a list of the various bundles that are relevant to project implementation (listed according to bundle). Not all the listed settings need adjusting, some are mentioned to help you understand how AEM operates.

When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](configuring-osgi.md) for more details and the recommended practices.

### Configuring LDAP
LDAP authentication is required to authenticate users stored in a (central) LDAP directory such as Active Directory. This helps reduce the effort required to manage user accounts.

LDAP authentication occurs at the repository level, so it is handled directly by the repository. For further details, see [Configuring LDAP with AEM](/content/help/en/experience-manager/6-4/sites/administering/using/ldap-config).

For user management within AEM (including assignment of access rights) see [User Administration and Security](/content/help/en/experience-manager/6-4/sites/administering/using/security).

### Configuring the Dispatcher
Dispatcher is Adobe's caching and/or load balancing tool. Using the Dispatcher also helps to protect your AEM server from attack. Therefore, you can increase the security of your AEM instance by using the Dispatcher in conjunction with an enterprise-class web server.

See [Dispatcher](/content/help/en/experience-manager/dispatcher/using/dispatcher) for full details, in particular [Configuring the Dispatcher](/content/help/en/experience-manager/dispatcher/using/dispatcher-configuration) [](config-ssl.md) for further configuration details.

### Configuring AEM LiveCycle Connector
With the release of the AEM Doc Services and AEM Doc Security, we now have the capability to invoke the LiveCycle doc services to render an XFA form, convert a document to PDF and policy protect a document. Please read [AEM LiveCycle Connector](/content/help/en/livecycle/help/aem/aem-livecycle-connector) for more details.

### Configuring an AEM Cluster
A cluster is formed of two, or more, live servers linked together to ensure that, if one node fails, the other nodes are active and accessible for your applications with no system interruption. This allows you to recover and re-start failed nodes easily. New nodes can also be added to an existing cluster, allowing for simple extensibility.

As all clustering setup is performed in the CRX repository, see the CRX clustering documentation for detailed information.

The CRX clustering documentation describes different clustering scenarios and how to set up clustering with a file journal using the GUI, manually with a file journal, and with a database journal.

A simple overview of configuration in AEM is also given under creating a cluster in AEM.

When optimizing a CQ installation you may wish to quickly add an additional cluster node without starting from scratch with an empty instance. This can be especially useful when you have existing system already holding substantial content.

In such a case, the most efficient way of adding a node is to clone the master node, creating one or more new slave nodes. This technique is discussed under Manual Slave Cloning.

### Job Offloading and Topology Administration
[Offloading](offloading.md) distributes processing tasks amoung Experience Manager instances in a topology. With offloading, you can use specific Experience Manager instances for performing specific types of processing. Specialized processing enables you to maximize the usage of available server resources.

Topologies are loosely-coupled Experience Manager clusters that are participating in offloading. A cluster consists of one or more Experience Manager server instances (a single instance is considered as a cluster).

For more information on how to view or modify topology membership, consult the [Administering Topologies](offloading.md#main-pars_title_0) section.

### Configuring the Welcome Console
The Welcome console of the classic UI provides a list of links to the various consoles and functionality within AEM.

It is possible to configure the links that are visible, see [Configuring the Welcome Console](/content/help/en/experience-manager/6-4/sites/developing/using/customizing-the-welcome-console) for further details.

### Configuring for Performance
[Performance](configuring-performance.md) is key to your project. Certain aspects of AEM (and/or the underlying repository) can be configured to optimize performance.

See [Configuring for Performance](configuring-performance.md#ConfiguringforPerformance) for further details.

### Scaling
Scaling a CQ installation correctly depends greatly on the details of your particular use case. A detailed discussion of solution patterns for various situations can be found in [Scaling CQ](scaling.md).

### Shared Data Store
The repository data store is used to offload the storage of large binaries from the repository proper to a separate area, so that multiple instances of the same binary (an image, for example) within the repository tree are stored only once.

This "store-once, reference-many-times" feature can be extended to serve not just a single repository tree but entirely separate repositories, by configuring the data store of each to refer to the same shared file system location.

Such a data store can be shared between different nodes in the same cluster, different publish and/or author instances in the same installation, or even entirely separate instances in different installations.

For more information, see [Configuring Data Stores and Node Stores](data-store-config.md).

## Further Configuration Considerations

### Enabling HTTP over SSL
You can enable HTTP over SSL to employ more secure connections to your servers.

See [Enabling HTTP over SSL](config-ssl.md) for further details.

### AEM Portals and Portlets
A portal is a web application that provides personalization, single sign on, content integration from different sources, and hosts the presentation layer of information systems. The portlet component also lets you embed a portlet on the page. To access content provided by CQ5 WCM, the portal server can to be fitted with the CQ5 Portal Director Portlet. You can do this by installing, configuring, and adding the portlet to the portal page.

See [Portal and Portlets](/content/help/en/experience-manager/6-4/sites/administering/using/aem-as-portal) for further details, in particular [Using CQ as a Portal](/content/help/en/experience-manager/6-4/sites/administering/using/aem-as-portal#UsingCQasaPortal) and [Installing, Configuring, and Using CQ in a Portlet](/content/help/en/experience-manager/6-4/sites/administering/using/aem-as-portal#InstallingConfiguringandUsingCQinaPortlet).

### Expiration of Static Objects
Static objects (for example, icons) do not change. Therefore the system should be configured so that they do not expire (for a reasonable period of time) and so reduce unnecessary traffic.

See [Expiration of Static Objects](expiration-static-objects.md) for further details.

### Open FIles in the Java Process
Each java process may access files - this requires system resources. For this reason an upper limit is defined as to how many files each process is allowed to access concurrently. If this is exceeded an exception error can occur.

If the AEM process exceeds this maximum, then the message " `too many open files`" will be seen in `error.log`.

To avoid such exceptions you need to:

1. Check how many open files your AEM process is using.  
   How you make this check will depend on the platform your instance is running on. Utilities such as lsof (Unix) or Process Explorer (Windows) can be used.  
   This value should be monitored during development and testing to:

    * confirm that files are being closed as required  
    * to determine the maximum value needed (under various circumstances)

1. Set the maximum allowed.  
   The new value should cater for both the current needs and any future peaks, so it is advisable to to double the current needs.  
   By default, `serverctl` configures `CQ_MAX_OPEN_FILES` to `8192`; this should be sufficient for most scenarios.

### Configuring the Rich Text Editor
The **Rich Text Editor** (**RTE**) provides authors with a wide range of [functionality](/content/help/en/experience-manager/6-4/sites/authoring/using/rich-text-editor) for editing their textual content; providing them with icons, selection boxes and menus for a WYSIWYG experience.

See [Configuring the Rich Text Editor](/content/help/en/experience-manager/6-4/sites/administering/using/rich-text-editor) for further details.

### Configuring Undo for Page Editing
There are several properties that control the behavior of the undo and redo commands for editing pages. These can be configured, see [Configuring Undo for Page Editing](/content/help/en/experience-manager/6-4/sites/administering/using/config-undo) for further details.

### Configuring the Video Component
The [Video component](/content/help/en/experience-manager/6-4/sites/authoring/using/default-components-foundation#Video) allows you to place a predefined, out-of-the-box video element on your page.

For proper transcoding to occur, your adminstrator must [Install FFmpeg](/content/help/en/experience-manager/6-4/sites/administering/using/config-video#InstallingFFmpeg) separately. They can also [Configure your Video Profiles](/content/help/en/experience-manager/6-4/sites/administering/using/config-video#ConfiguringVideoProfiles) for use with html5 elements.

### Configuring and Customizing Reports
To help you monitor and analyze the state of your instance, CQ provides a selection of default reports, which can be configured for your individual requirements:

See the [Basics of Report Customization](/content/help/en/experience-manager/6-4/sites/administering/using/reporting#TheBasicsofReportCustomization) for further details.

### Configuring Email Notification
CQ sends email notifications to users who:

* Have subscribed to page events, for example modification or replication.   
* Have subscribed to forum events.
* Have to perform a step in a workflow.

See [Configuring Email Notification](/content/help/en/experience-manager/6-4/sites/administering/using/notification) for further details.

### Configuring Automatic Emails for Account Activities
The Account Manager lets you configure the emails that users automatically receive when they create an account or reset a password and to confirm a password that has been reset.

See [Configuring Automatic Emails for Account Activities](/content/docs/en/aem/6-3/administer/security/configure-account-services) for further details.

<!-- 

Comment Type: remark
Last Modified By: (raiman)
Last Modified Date: 2017-11-30T05:41:42.432-0500

<p>This section needs to be reviewed for accuracy. Setting it in draft mode.</p>

 -->

### Enabling Page Impressions
Page impressions are displayed in the **Impressions** column of the classic UI siteadmin console. To enable the capture of page impressions you need to configure:

* On the publish instance:

    * [Day CQ WCM Page Statistics](osgi-configuration-settings.md#DayCQWCMPageStatistics)

* On the author instance:

    * [Adobe Page Impressions Tracke](osgi-configuration-settings.md#AdobePageImpressionsTracker)r

>[!CAUTION]
>
>The configuration of Adobe Page Impressions Tracker on the author environment will allow anonymous requests to the tracking service.

## Architectural Best Practices
**Possibly this belongs on its own page...how to distinguish architectural best practices from "configuration"**

* To keep partners up to date on architectural best practices it would make sense to add a page for this. It should cover information on:

* The proper way to share a datastore (e.g. do not share over NFS, see [CRX-4424](https://issues.adobe.com/browse/CRX-4424)).
* Best ways to set up a CRX cluster (use master cloning) and max recommended cluster size (e.g. 4 is max before it gets sluggish / unstable)
* Link to documentation on sizing for number of publish instances for optimal performance.
* Recommendations on when to use reverse replication vs normal replication.
* Recommendation of why it is important to set up dispatcher flushing on publish, not author. How to properly configure replication on a publish instance. How to set up dispatcher flush pre-fetch feature (see [DISP-237](https://issues.adobe.com/browse/DISP-237))
* Information regarding ACLs, setting EntryCollector cache size and how to structure them to reduce total number of permission checks. This could just point to a link if this documentation already exists.
* Performance tuning [http://helpx.adobe.com/cq/kb/performancetuningtips.html](http://helpx.adobe.com/cq/kb/performancetuningtips.html) . Especially including how to properly size various caches in CQ and CRX.
* Proper installation procedures, how to properly size heap and permgen space for CQ apps.
* Recommendation of using official Hotspot JDK instead of OpenJDK.

