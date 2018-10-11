---
title: OSGi Configuration Settings
seo-title: OSGi Configuration Settings
description: null
seo-description: This article details the OSGi configuration settings (listed according to bundle) that are relevant to project implementation. The list acts as a guideline and it is not exhaustive. 
uuid: 48a2642b-c946-46fc-9456-3327a12662b0
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/osgi-configuration-settings
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 37.080-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 43 11.854-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 9b751bbf-8ad1-45f6-ad2c-1f1b3b7832f0
firstPublishExternalDate: 2017-10-31T16:17:50.210-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 05 23.010-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:43:11.096-0400
lochandoffdate: 2018-04-30T03 27 37.079-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: OSGi Configuration Settings
publishexternaldate: 2018-04-03T08 43 11.096-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/osgi-configuration-settings.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/osgi-configuration-settings
sha1: 59957e49ec2495fe564d44189aabb6fed2f9aabb
topicBrowsingSortDate: 2018-04-03T08:43:11.096-0400
index: y
internal: n
snippet: y
---

# OSGi Configuration Settings

<!-- 

Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2017-11-30T05:42:16.104-0500

<p>There are broken links in this doc</p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2017-11-30T05:42:16.116-0500

<p>Lots of new Adobe CQ osgi configuration options in 5.6.1 (and probably 5.6). These are particular to all the new solutions:</p> 
<p>Media, Scene7, Soco, TagManager and damScene7</p> 
<p>We may need to include something at some point about these (or at least some of them).</p>

 -->

[OSGi](http://www.osgi.org/) is a fundamental element in the technology stack of AEM. It is used to control the composite bundles of AEM and their configuration.

OSGi "*provides the standardized primitives that allow applications to be constructed from small, reusable and collaborative components. These components can be composed into an application and deployed*".

This allows easy management of bundles as they can be stopped, installed, started individually. The interdependencies are handled automatically. Each OSGi Component (see the [OSGi Specification](http://www.osgi.org/Specifications/HomePage)) is contained in one of the various bundles. When working with AEM there are several methods of managing the configuration settings for such bundles; see [Configuring OSGi](configuring-osgi.md) for more details and the recommended practices.

The following OSGi configuration settings (listed according to bundle) are relevant to project implementation. Not all the listed settings need adjusting, some are mentioned to help you understand how AEM operates.

>[!CAUTION]
>
>The list is intended to act as a guideline and is not exhaustive. Not all bundles are listed, nor all parameters for some of the bundles that are.
>
>The configuration necessary will vary from project to project.
>
>Please see the Web console for values used and detailed information about parameters.

>[!NOTE]
>
>The [AEM OSGi Config Details](http://www.aemstuff.com/osgi.html) tool can be used to list the default OSGi configurations.

>[!NOTE]
>
>Further bundles may be required for specific areas of functionality within AEM. In these cases, configuration details can be found on the page related to the appropriate functionality.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:42:16.182-0500

<p>This is no longer present - has it been removed or replaced (and if so to what)?<br /> </p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:42:16.206-0500

<p>This is no longer present - has it been removed or replaced (and if so to what)?<br /> </p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:42:16.230-0500

<p>This is no longer present - has it been removed or replaced (and if so to what)?<br /> </p>

 -->

>[!NOTE]
>
>This configuration should be made using the Felix Console as it is needed at startup - before the repository is available.

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:42:16.265-0500

<p>This is no longer present - has it been removed or replaced (and if so to what)?</p> 
<p>I suspect it's been deprecated, but just need to check...<br /> </p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2017-11-30T05:42:16.288-0500

<p>73 Adobe CQ configs</p> 
<p>2 Mac configs</p> 
<p>1 Adobe Octopus config</p> 
<p> </p>

 -->

>[!CAUTION]
>
>Be sure to configure the following:
>
>**User Name** and **Password**, the credentials for accessing the Apache Felix Web Management Console itself.  
>The password must be changed after the initial installation to ensure the [security](/content/docs/en/aem/6-3/deploy/security_checklist) of your instance.

>[!NOTE]
>
>This configuration should be made using the Felix Console as it is needed at startup - before the repository is available.

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2017-11-30T05:42:16.356-0500

<p>Not present with this name in 6.1 - to be verified if this config is handled by Apache Sling Thread Pool Configuration<br /> </p>

 -->

>[!NOTE]
>
>This setting is automatically configured for production instances if you run AEM in [Production Ready Mode](/content/help/en/experience-manager/6-4/sites/administering/using/production-ready).

>[!NOTE]
>
>This setting is automatically configured for production instances if you run AEM in [Production Ready Mode](/content/help/en/experience-manager/6-4/sites/administering/using/production-ready).

>[!NOTE]
>
>The Apache Sling Referrer Filter is dependent on the installation of a quick fix package.

>[!CAUTION]
>
>In particular these options must be configured in the repository.
>
>Otherwise changes made to **URL Mappings** using the Felix console might be overwritten by AEM upon the next startup.

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2017-11-30T05:42:16.576-0500

<p>Not present in 6.1</p>

 -->

>[!NOTE]
>
>In AEM 6.0 and earlier releases proxy was configured in Day Commons HTTP Client. As of AEM 6.1 and later releases the proxy configuration has moved to the "Apache HTTP Components Proxy Configuration" instead of the 'Day Commons HTTP Client' config.

>[!CAUTION]
>
>When changing the setting for either **Minify** or **Gzip** you will also need to delete the contents of `/var/clientlibs`. This is a cached version of the clientlibs and will be rebuilt when next requested.

>[!NOTE]
>
>This setting is automatically configured for production instances if you run AEM in [Production Ready Mode](/content/help/en/experience-manager/6-4/sites/administering/using/production-ready).

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2017-11-30T05:42:16.666-0500

<p>This is present in 6.1. See DOC-5647.</p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:42:16.697-0500

<p>how exactly do the above two (link checker service and task) interact? eg both have a scheduler period.<br /> </p>

 -->

<!-- 

Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2017-11-30T05:42:16.729-0500

<p>Check this paragraph after 5.6 GA (still need to refer version nr and classic UI?)<br /> </p>

 -->

>[!NOTE]
>
>Upon a standard installation the touch-optimized UI is the default UI.

>[!NOTE]
>
>This setting is automatically configured for production instances if you run AEM in [Production Ready Mode](/content/help/en/experience-manager/6-4/sites/administering/using/production-ready).

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2017-11-30T05:42:16.830-0500

<p>Both the Link Checker Configurator and WCM Page Processor are present in 6.1.<br /> </p>

 -->

>[!CAUTION]
>
>This configuration will allow anonymous requests to the tracking service.

>[!NOTE]
>
>See [Page Impressions](configuring.md#EnablingPageImpressions) for more information.

>[!NOTE]
>
>See [Page Impressions](configuring.md#EnablingPageImpressions) for more information.

<!-- 

Comment Type: remark
Last Modified By: unknown unknown (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2017-11-30T05:42:16.936-0500

<p>Not present in 6.1</p>

 -->

**CQ Rewriter HTML Parser Factory**

Controls the HTML Parser for the CQ rewriter.

* **Additional Tags to Process** - You can add or remove HTML tags to be processed by the parser. By default, the following tags are processed: A,IMG,AREA,FORM,BASE,LINK,SCRIPT,BODY,HEAD.
* **Preserve Camel Case** - By default, the HTML parser converts attributes in camel case (e.g. eBay) to lower case (e.g. ebay). You can turn this off to preserve the camel case attributes. This is useful when using frontend frameworks such as Angular 2.

![](assets/osgi-configuration-settings/chlimage_1.png)

>[!NOTE]
>
>This feature is currently only enabled for AEM author instances.

