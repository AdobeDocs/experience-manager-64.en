---
title: Multi-tenancy for collections, snippets, and snippet templates
description: Segregate content in the CRX repository based on the customer organization to prevent unauthorized access.
contentOwner: AG
feature: Collections
role: Architect,Administrator,Leader
---

# Multi-tenancy for collections, snippets, and snippet templates {#multi-tenancy-for-collections-snippets-and-snippet-templates}

The Multi-tenancy feature lets you segregate content in CRX based on the organization prefix and organization ID to safeguard the content from unauthorized access by users of other organizations.

Adobe Experience Manager (AEM) Assets stores data for each organization in a different path. Each organization-specific path is identified by the organization prefix and organization ID.
that is included in the traditional location where different types of assets are stored in CRX.

For example, if you create a folder named `Demo`, AEM assets by default stores the folder at `../content/dam/Demo` location in CRX. With the multi-tenancy feature enabled, you can store the data at `../content/dam/<organization prefix>/<organization id>Demo`. 

For example, for Adobe Marketing Cloud users of AEM Assets (on-demand) that are assigned to `aodpremium` organization, you can use the multi-tenancy feature to configure the following path to `../content/dam/mac/aodpremiumDemo`, segregate the content. In this example `mac` is the organization prefix and `aodpremium` is the organization ID.

Based on the user's organization and ID, this qualified path is displayed in the AEM Assets interface and various wizards, including the Move and Snippet creation wizards to enforce seggregation.

The multi-tenancy feature lets you seggregate the following types of assets and components:

* Collections
* Public Collections
* Catalogs (including the Add/Select Page wizard)
* Templates
* Snippet templates
* Lightbox
