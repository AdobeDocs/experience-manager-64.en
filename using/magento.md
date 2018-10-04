---
title: Magento
seo-title: Magento
description: null
seo-description: Learn how to deploy eCommerce with Magento.
uuid: 25895cba-805b-449c-a6ec-991a6fd76d00
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/magento
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 26.517-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 43 41.787-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 3f8d9517-e660-4754-a15a-cc2e9061d91e
disttype: dist5
firstPublishExternalDate: 2017-10-31T16:17:55.730-0400
gnavtheme: light
groupsectionnavitems: no
hidemerchandisingbar: inherit
hidepromocomponent: inherit
isreadyforlocalization: false
jcr-created: 2017-12-01T19 06 18.223-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:43:40.956-0400
lochandoffdate: 2018-04-30T03 27 26.516-0400
lr-lastreplicatedby: carlino@adobe.com
modalsize: 426x240
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Magento
pagetitle: Deploying eCommerce with Magento
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 43 40.956-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/magento.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/ecommerce/magento
sha1: 1f81f0479345d4204fd5a7c08caa8c6f7de9847e
topicBrowsingSortDate: 2018-04-03T08:43:40.956-0400
index: y
internal: n
snippet: y
translate: y
---

# Magento

Deploying the necessary eCommerce packages will provide the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with a Demandware Commerce implementation (including a demonstration catalog).

---

## Packages Needed for eCommerce with Magento

You need to download the following connector:

---

## Installation of eCommerce with Magento

To install AEM with a Magento Commerce integration configuration, the basic steps are as follows.

First in Magento:

1. Instal the AEM Connector.

1. Import the we.retail sample catalog.

Then in AEM:

1. [Download and Install](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/releases) We.retail.

1. Instal the AEM / Magento 2 Connector package.

1. Install the Demo AEM content package.

---

## Configuration

### Authentication

The AEM / Magento 2 connector uses standard AEM authentication mechanism (External Login Module) to support both login and registration against Magento. In order to allow authentication you need to configure the Magento 2 Identity Provider in AEM like so.

To configure the Identity Provider:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Click **Magento Identity Provider**.

   ![](assets/chlimage_1.jpeg)

1. Enter the following information:

    * **Magento Server**: Full URL of your Magento server 
    
    * **Admin Username**: Magento admin user to connect to Magento (for non production / demo purposes) 
    
    * **Admin Password**: Magento admin password

1. Click **Save**.

To configure the Sync Handler:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Click **Apache Jackrabbit Oak Default Sync Handler.**

   ![](assets/chlimage_1.jpeg)

1. Enter the following information:

    * **Sync Handler Name**: default    
    * **User Expiration Time**: 1m
    
    * **User auto membership**: everyone    
    * **User property mapping**:

        * rep:fullname=cn        
        * profile/nt:primaryType="nt:unstructured"        
        * profile/givenName=givenname        
        * profile/familyName=familyname        
        * profile/email=email        
        * magento-token=token

    * **User Path Prefix**: /magento    
    * **User Membership Expiration**: 1h    
    * **User membership nesting depth**: 0    
    * **Group Expiration Time**: 1d    
    * **Group auto membership**: &lt;leave blank&gt;    
    * **Group property mapping**: &lt;leave blank&gt;    
    * **Group Path Prefix**: /magento

1. Click **Save**.

The external login module is the bridge between the login, the idp and the sync handler, that's why a new configuration that pairs the new magento idp with the default sync handler is needed. To configure the external login module:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Click **Apache Jackrabbit External Login Module**.

   ![](assets/chlimage_1.jpeg)

1. Enter the following information:

    * **JAAS Ranking**: 50
    
    * **JAAS Control Flag:** SUFFICIENT
    
    * **JAAS Realm**: &lt;leave blank&gt;
    
    * **Identity Provider Name**: magento
    
    * **Sync Handler Name**: default

1. Click **Save**.

