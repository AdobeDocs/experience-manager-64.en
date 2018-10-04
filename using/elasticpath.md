---
title: Elastic Path
seo-title: Elastic Path
description: null
seo-description: Learn how to deploy eCommerce with Elastic Path.
uuid: 903a48c5-0d8b-40ad-96ed-7f7ef0cf248a
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/elasticpath
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 51.468-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 40 59.878-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: a9b72e9a-40a5-454f-ac8e-fa7b3eca5731
disttype: dist5
firstPublishExternalDate: 2017-10-31T16:17:58.267-0400
gnavtheme: light
isreadyforlocalization: false
jcr-created: 2017-12-01T19 02 33.319-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:40:58.924-0400
lochandoffdate: 2018-04-30T03 26 51.468-0400
lr-lastreplicatedby: carlino@adobe.com
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Elastic Path
pagetitle: Deploying eCommerce with Elastic Path
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 40 58.924-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/elasticpath.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/ecommerce/elasticpath
sha1: b8aa6880c78122f224a381a43d4bd7a5f1dd9567
topicBrowsingSortDate: 2018-04-03T08:40:58.924-0400
index: y
internal: n
snippet: y
translate: y
---

# Elastic Path

Deploying the necessary eCommerce packages provides the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with Elastic Path implementation (including a demonstration catalog).

This catalog is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site.

>[!NOTE]
>
><p>This page contains links to the&nbsp;<a href="http://www.elasticpath.com/">Elastic Path website</a>. Certain areas need an account for full access.</p>

### Installation of eCommerce with Elastic Path

To install AEM with an Elastic Path integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](deploy.md) and any other pre-requisite packages (see [https://docs.elasticpath.com/display/EP611DEV/System+Requirements](https://docs.elasticpath.com/display/EP611DEV/System+Requirements) for details).

1. Install the latest demonstration content packages using the [Package Manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager#PackageManager) in the following order:

    1. `ep-cortex-java-bindings`    
    1. `ep-aem-integration`    
    1. `cq-geometrixx-ep-content`

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

>[!NOTE]
>
><p>To be able to find and download those packages and the matching Elastic Path Commerce demo server, please&nbsp;<a href="http://www.elasticpath.com/company/contact-us">contact Elastic Path</a>.</p> <p>For additional details on Elastic Path for Adobe Marketing Cloud, please see&nbsp;<a href="http://cms-developers.elasticpath.com">http://cms-developers.elasticpath.com</a>.</p>

If Elastic Path is running on any other machine or server (as recommended for Production):

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Open `com.elasticpath.web.config.EPConfigurationHandler`.

1. Update the `cortex.url` to point to that machine in which Elastic Path is running.

   ![](assets/chlimage_1.png)

>[!CAUTION]
>
><p>Use of the Elastic Path server requires a separate Elastic Path license.</p> 
