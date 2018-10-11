---
title: Backward Compatibility in AEM 6.4
seo-title: Backward Compatibility in AEM 6.4
description: null
seo-description: Learn how to keep your apps and configurations compatible with AEM 6.4
uuid: dd354072-8dfe-4cdb-9146-92f3e4949ad3
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/backward-compatibility
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 38.476-0400
cq-lastmodifiedby: taneja
cq-lastreplicated: 2018-04-10T08 44 40.180-0400
cq-lastreplicatedby: trushton
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 6e0695c3-539e-4379-9554-e360d533a27a
firstPublishExternalDate: 2018-04-03T09:27:45.949-0400
isreadyforlocalization: false
jcr-created: 2018-03-23T07 28 51.241-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-10T08:44:39.999-0400
lochandoffdate: 2018-04-30T03 26 38.475-0400
lr-lastreplicatedby: trushton@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
pagecreatedat: en
publishexternaldate: 2018-04-10T08 44 39.999-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/backward-compatibility.html
sha1: afbcb795e0a9fe4e30b22eb3b265e1b89480e20d
topicBrowsingSortDate: 2018-04-10T08:44:39.999-0400
unpublishinternaldate: 2018-03-30T04 56 09.317-0400
index: y
internal: n
snippet: y
---

# Backward Compatibility in AEM 6.4

## Overview

>[!NOTE]
>
>For a list of content and configuration changes that are not under the scope the Compatibility Package, see [Repository Restructuring in AEM 6.4](repository-restructuring-in-aem64.md).

In AEM 6.4, all features have been developed with backwards compatibility in mind.

In most cases, customers running AEM 6.3 should not have to change the code or customizations when doing the upgrade. For AEM 6.1 and 6.2 customers there is no additional breaking changes than would be faced during an upgrade to 6.3.

For exceptions where features could not be kept backward compatible, backward compatibility for bundles and content can be achieved by installing a Compatibility Package for 6.3( please see how to setup below for details on where to download). This compat package will restore compatiblity for applications compliant with AEM 6.3.

The Compatibility Package allows you to run AEM in compatibility mode and defer custom development against new AEM features:

>[!NOTE]
>
>Please note that the compatibility package is only a temporary solution to defer development required for being AEM 6.4 compatible, its recommended only as a last option if you are not able to address compatibility issues through development immediately after the upgrade. It is strongly recommended to switch to native mode and uninstall the compatibility package once you decide to proceed with 6.4 based custom development and avail of full 6.4 functionality.

![](assets/screen_shot_2018-04-05at43339pm.png)

The Compatibility Package has two modes: **Routing Enabled** and **Routing Disabled**.

This allows AEM 6.4 to be run in three modes:

**Native Mode:**

Native mode is for customers who want to use all the new features of AEM 6.4 and are ready to do some development to make their customizations work with all new features.

This means that you may need to make adjustments in your application immediately after upgrade.

**Compatibility Mode: Compatibility Package Installed with Routing Enabled**

Compatibility Mode is for customers who have customizations of interfaces that are not backward compatible. This allows AEM to run in compatibility mode and defer custom development required against new AEM Features that are not compatible with some of your custom code.

**Legacy Mode: Compatiblity Package Installed with Routing Disabled**

Legacy mode is for customers having custom interfaces based on legacy or deprecated code from AEM that has been moved out in the compatibility package.

![](assets/image2018-2-12_23-58-37.png)

## How to Set Up
The AEM 6.3 Compatibility Package will be installable as a package using the Package Manager at this [link](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/compatpack/aem-compat-cq64-to-cq63).

Once the Compatibility Package is installed, the routing can be enabled or disabled using a switch in the OSGI configuration as shown below:

![](assets/screen_shot_2017-11-27at122421pm.png)

Once the Compatibility Package is installed and set up, the features will be used based on the compatibility mode that has been chosen.
