---
title: Multi-tenancy for Collections, Snippets, and Snippet Templates
seo-title: Multi-tenancy for Collections, Snippets, and Snippet Templates
description: null
seo-description: Learn how the Multi-tenancy feature lets you segregate content in the CRX repository based on the customer organization to prevent unauthorized access.
uuid: 5e11a138-697f-4b0a-8929-7d10d237fb16
acrolinxdate: 2019-01-12T17 34 48.387-0500
acrolinxlastcheckedby: asgupta
acrolinxpagestatus: yellow
acrolinxreporturl: http //acrolinx.corp.adobe.com 8031/output/en/multi_tenancy_krs_workflow_f3c2f2ccebf6138e_191_report.xml
acrolinxsentences: 9
acrolinxwords: 258
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 5073ba28-610a-40e1-96db-42aed9afde5a
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Multi-tenancy for Collections, Snippets, and Snippet Templates{#multi-tenancy-for-collections-snippets-and-snippet-templates}

The Multi-tenancy feature lets you segregate content in CRX based on the organization prefix and organization ID to safeguard the content from unauthorized access by users of other organizations.

Adobe Experience Manager (AEM) Assets stores data for each organization in a different path. Each organization-specific path is identified by the organization prefix and organization ID   
that is included in the traditional location where different types of assets are stored in CRX.

For example, if you create a folder named Demo, AEM assets traditionally stores the folder at the following location in CRX:

**..*/content/dam/Demo***

With the Multi-tenancy feature enabled, you can now store the data at the following location:

**..*/content/dam/&lt;organization prefix&gt;/&lt;organization id&gt;Demo* 
**

For example, if for Adobe Marketing Cloud users of AEM Assets (on demand) that are assigned to the aodpremium organization, you can use the Multi-tenancy feature to configure the following path to segregate their content:

**..*/content/dam/&lt;mac&gt;/&lt;aodpremium&gt;Demo***

Where **mac** is the organization prefix and **aodpremium** is the organization ID.

Based on the user's organization and ID, this qualified path is displayed in the AEM Assets interface and various wizards, including the Move and Snippet creation wizards to enforce seggregation.

The Multi-tenancy feature lets you seggregate the following types of assets and components:

* Collections
* Public Collections 
* Catalogs (including the Add/Select Page wizard)
* Templates
* Snippet templates
* Lightbox

