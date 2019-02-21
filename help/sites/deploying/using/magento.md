---
title: Magento
seo-title: Magento
description: Learn how to deploy eCommerce with Magento.
seo-description: Learn how to deploy eCommerce with Magento.
uuid: 5fada259-bde5-4c82-bfd9-b0d26b410769
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: bb30f0ad-d110-445d-bd2f-917a7c046b4c
pagetitle: Deploying eCommerce with Magento
index: y
internal: n
snippet: y
---

# Magento{#magento}

Deploying the necessary eCommerce packages will provide the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with a Magento Commerce implementation (including a demonstration catalog).

## Packages Needed for eCommerce with Magento {#packages-needed-for-ecommerce-with-magento}

You need to download the following connector:

[Get File](assets/magento2-aem-connector-master.zip)

## Installation of eCommerce with Magento {#installation-of-ecommerce-with-magento}

To install AEM with a Magento Commerce integration configuration, the basic steps are as follows.

First in Magento:

1. Instal the AEM Connector.
1. Import the we.retail sample catalog.

Then in AEM:

1. [Download and Install](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/releases) We.retail.
1. Instal the AEM / Magento 2 Connector package.
1. Install the Demo AEM content package.

## Configuration {#configuration}

### Authentication {#authentication}

The AEM / Magento 2 connector uses standard AEM authentication mechanism (External Login Module) to support both login and registration against Magento. In order to allow authentication you need to configure the Magento 2 Identity Provider in AEM like so.

To configure the Identity Provider:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Click **Magento Identity Provider**.

   ![](assets/chlimage_1-8.jpeg)

1. Enter the following information:

    * **Magento Server**: Full URL of your Magento server 
    * **Admin Username**: Magento admin user to connect to Magento (for non production / demo purposes) 
    * **Admin Password**: Magento admin password

1. Click **Save**.

To configure the Sync Handler:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Click **Apache Jackrabbit Oak Default Sync Handler.**

   ![](assets/chlimage_1-9.jpeg)

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

   ![](assets/chlimage_1-10.jpeg)

1. Enter the following information:

    * **JAAS Ranking**: 50
    * **JAAS Control Flag:** SUFFICIENT
    * **JAAS Realm**: &lt;leave blank&gt;
    * **Identity Provider Name**: magento
    * **Sync Handler Name**: default

1. Click **Save**.

