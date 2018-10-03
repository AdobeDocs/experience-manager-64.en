---
title: OSGi Configuration Settings
seo-title: OSGi Configuration Settings
description: null
seo-description: This article details the OSGi configuration settings (listed according to bundle) that are relevant to project implementation. The list acts as a guideline and it is not exhaustive. 
uuid: 9db983a7-515c-48d6-9c0d-9b3350e4c818
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
discoiquuid: 45baed16-6524-4236-9714-96aefd24f726
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
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 43 11.096-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/osgi-configuration-settings.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/osgi-configuration-settings
sha1: 1b16d0b98c34e2129385f4d12249e06d9ccd9911
topicBrowsingSortDate: 2018-04-03T08:43:11.096-0400
index: y
internal: n
snippet: y
translate: y
---

# OSGi Configuration Settings

[OSGi](http://www.osgi.org/) is a fundamental element in the technology stack of AEM. It is used to control the composite bundles of AEM and their configuration.

OSGi "*provides the standardized primitives that allow applications to be constructed from small, reusable and collaborative components. These components can be composed into an application and deployed*".

This allows easy management of bundles as they can be stopped, installed, started individually. The interdependencies are handled automatically. Each OSGi Component (see the [OSGi Specification](http://www.osgi.org/Specifications/HomePage)) is contained in one of the various bundles. When working with AEM there are several methods of managing the configuration settings for such bundles; see [Configuring OSGi](configuring-osgi.md) for more details and the recommended practices.

The following OSGi configuration settings (listed according to bundle) are relevant to project implementation. Not all the listed settings need adjusting, some are mentioned to help you understand how AEM operates. 

>[!CAUTION]
>
><p>The list is intended to act as a guideline and is not exhaustive. Not all bundles are listed, nor all parameters for some of the bundles that are.</p> <p>The configuration necessary will vary from project to project.</p> <p>Please see the Web console for values used and detailed information about parameters.</p> 

>[!NOTE]
>
><p>The <a href="http://www.aemstuff.com/osgi.html">AEM OSGi Config Details</a> tool can be used to list the default OSGi configurations.<br> </p> 

>[!NOTE]
>
><p>Further bundles may be required for specific areas of functionality within AEM. In these cases, configuration details can be found on the page related to the appropriate functionality. &nbsp;</p> 

>[!NOTE]
>
><p>This configuration should be made using the Felix Console as it is needed at startup - before the repository is available.<br> </p> 

>[!CAUTION]
>
><p>Be sure to configure the following:</p> <p><b>User Name</b> and <b>Password</b>, the credentials for accessing the Apache Felix Web Management Console itself.<br> The password must be changed after the initial installation to ensure the <a href="/content/docs/en/aem/6-3/deploy/security_checklist.html">security</a> of your instance.</p> 

>[!NOTE]
>
><p>This configuration should be made using the Felix Console as it is needed at startup - before the repository is available.<br> </p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html">Production Ready Mode</a>.</p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html" >Production Ready Mode</a>.<br> </p> 

>[!NOTE]
>
><p>The Apache Sling Referrer Filter is dependent on the installation of a quick fix package.<br> </p> 

>[!CAUTION]
>
><p>In particular these options must be configured in the repository.</p> <p>Otherwise changes made to <b>URL Mappings</b> using the Felix console might be overwritten by AEM upon the next startup.</p> 

>[!NOTE]
>
><p>In AEM 6.0 and earlier releases proxy was configured in Day Commons HTTP Client. As of AEM 6.1 and later releases the proxy configuration has moved to the &quot;Apache HTTP Components Proxy Configuration&quot; instead of the 'Day Commons HTTP Client' config.</p> 

>[!CAUTION]
>
><p>When changing the setting for either <b>Minify</b> or <b>Gzip</b> you will also need to delete the contents of <span class="code">/var/clientlibs</span>. This is a cached version of the clientlibs and will be rebuilt when next requested.</p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html">Production Ready Mode</a>.</p> 

>[!NOTE]
>
><p>Upon a standard installation the touch-optimized UI is the default UI.</p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html">Production Ready Mode</a>.</p> 

>[!CAUTION]
>
><p>This configuration will allow anonymous requests to the tracking service.</p> 

>[!NOTE]
>
><p>See <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/configuring.html#EnablingPageImpressions">Page Impressions</a> for more information.</p> 

>[!NOTE]
>
><p>See <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/configuring.html#EnablingPageImpressions">Page Impressions</a> for more information.</p>

**CQ Rewriter HTML Parser Factory**

Controls the HTML Parser for the CQ rewriter.

* **Additional Tags to Process** - You can add or remove HTML tags to be processed by the parser. By default, the following tags are processed: A,IMG,AREA,FORM,BASE,LINK,SCRIPT,BODY,HEAD.
* **Preserve Camel Case** - By default, the HTML parser converts attributes in camel case (e.g. eBay) to lower case (e.g. ebay). You can turn this off to preserve the camel case attributes. This is useful when using frontend frameworks such as Angular 2.

![](assets/chlimage_1.png) 
>[!NOTE]
>
><p>This feature is currently only enabled for AEM author instances.</p> 
