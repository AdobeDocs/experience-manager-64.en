---
title: Backward Compatibility in AEM 6.4
seo-title: Backward Compatibility in AEM 6.4
description: null
seo-description: Learn how to keep your apps and configurations compatible with AEM 6.4
uuid: f54a7104-2359-4ad3-99a9-b93e5ccc962d
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
discoiquuid: 333ce4f2-1b55-4d34-bd23-d33b580dac7e
isreadyforlocalization: false
unpublishinternaldate: 2018-03-30T04 56 09.317-0400
index: y
internal: n
snippet: y
---

# Backward Compatibility in AEM 6.4{#backward-compatibility-in-aem}

## Overview {#overview}

>[!NOTE]
>
>For a list of content and configuration changes that are not under the scope the Compatibility Package, see [Repository Restructuring in AEM 6.4](../../deploying/using/repository-restructuring-in-aem64.md).

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

## How to Set Up {#how-to-set-up}

The AEM 6.3 Compatibility Package will be installable as a package using the Package Manager at this [link](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/compatpack/aem-compat-cq64-to-cq63).

Once the Compatibility Package is installed, the routing can be enabled or disabled using a switch in the OSGI configuration as shown below:

![](assets/screen_shot_2017-11-27at122421pm.png)

Once the Compatibility Package is installed and set up, the features will be used based on the compatibility mode that has been chosen.
