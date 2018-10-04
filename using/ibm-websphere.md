---
title: IBM Websphere Commerce
seo-title: IBM Websphere Commerce
description: null
seo-description: Integrating AEM with IBM Websphere Commerce
uuid: 26591287-fac2-4045-85bc-92a5457110b2
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/ibm-websphere
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 59.151-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 43 53.324-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 9e9c7ac1-4a60-4574-8e29-25d231099bd0
disttype: dist5
firstPublishExternalDate: 2017-10-31T16:17:56.330-0400
gnavtheme: light
isreadyforlocalization: false
jcr-created: 2017-12-01T19 01 44.445-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:43:52.415-0400
lochandoffdate: 2018-04-30T03 26 59.150-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: IBM Websphere Commerce
pagetitle: Deploying eCommerce with IBM Websphere Commerce
publishexternaldate: 2018-04-03T08 43 52.415-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/ibm-websphere.html
qaDate: 2017-10-12T21:46:58.665-0400
qaNotes: /content/docs/en/aem/6-3/deploy/ecommerce/ibm-websphere
sha1: df5c8572e63c2bf416edf2945873a754f8b5f82d
topicBrowsingSortDate: 2018-04-03T08:43:52.415-0400
index: y
internal: n
snippet: y
translate: y
---

# IBM Websphere Commerce

Deploying the necessary eCommerce packages will provide the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with a IBM Websphere Commerce implementation (including a demonstration catalog).

This is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site.

>[!NOTE]
>
><p>To run the Geometrixx Outdoors store with WebSphere Commerce,&nbsp;<a href="/content/help/en/experience-manager/6-4/sites/deploying/using/setup.html">the Geometrixx Outdoors products and catalog data must be loaded into WebSphere Commerce</a>.</p>

### Technical Requirements

The IBM Websphere extension of the eCommerce Integration Framework has been made to support Websphere Commerce version 7 Feature Pack 8.

>[!NOTE]
>
><p>You will need Java 7.</p>

### Packages Needed for eCommerce with Websphere Commerce

To install eCommerce functionality you need:

* Your Websphere Commerce server.
* AEM eCommerce framework:

    * this is part of a standard AEM installation      
    
    * CQ Geometrixx Outdoors demo store (needs seperate package, as Geometrixx demos are not part of AEM 6.3 any more)

* AEM Websphere Commerce content packages, available through your [Daycare](http://daycare.day.com/home.html) account: ``

    * `cq-geometrixx-all-pkg-5.10.68      
      `    
    * `cq-6.3.0-featurepack-6709`    
    * a reference implementation to illustrate use of Websphere Commerce ( `geometrixx-outdoors/en_US`)

### Installation of eCommerce with Websphere Commerce

To install AEM with a Websphere Commerce integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](deploy.md).

1. Install the demonstration content packages using the [package manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager):

    1. `cq-geometrixx-all-pkg      
       `    
    1. `cq-6.3.0-featurepack-6709`

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

>[!NOTE]
>
><p>To download the packages, navigate to&nbsp;<a href="/content/help/en/experience-manager/6-4/sites/administering/using/package-manager.html#main-pars_title_3">Package Share</a>.</p>

AEM needs to be configured to connect to the WebSphere Commerce server instance, which is our demo WebSphere Commerce Server running the Geometrixx Outdoors eSite.

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Click **Adobe CQ Commerce - IBM WebSphere Commerce REST API client**.

1. Enter the **Websphere Commerce server host / ip **as required.

1. Click **Save**.

>[!CAUTION]
>
><p>Use of the Websphere Commerce server requires a separate license.</p> 
