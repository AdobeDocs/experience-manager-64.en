---
title: Repository Restructuring in AEM v2
seo-title: Repository Restructuring in AEM v2
description: null
seo-description: null
uuid: dd3e84d0-cfa3-4f42-8765-862d0b5d85d9
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/repository-restructuring-in-aem-v2
contentOwner: chaikels
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-07-26T03 44 03.605-0400
cq-lastmodifiedby: chaikels
cq-template: /apps/help/templates/article-3
discoiquuid: f424767d-f932-446e-b18d-c7d257c53120
jcr-created: 2018-05-24T07 29 10.826-0400
jcr-createdby: admin
jcr-language: en_us
pagecreatedat: en
preview: true
sha1: 9b177f6c95afb32f4ebf9e47d4724b2dd9e58ce8
index: y
internal: n
snippet: y
---

# Repository Restructuring in AEM v2



## Introduction
Prior to AEM 6.4, customer code was deployed in unpredictable areas of the JCR that were subject to change on upgrades. Because of this, it was common for formal AEM releases to overwrite custom code, configuration or content. In addition, customer changes sometimes overwrote AEM product code or content, breaking product functionality.

By clearly delineating hierarchies for AEM product code and customer code, these conflicts can be avoided.

To that end, beginning in AEM 6.4 and to be continued in future releases, content is being restructured out of /etc to other folders in the repository, along with guidelines on what content goes where, adhering to the following high-level rules:

* AEM product code will always be placed in /libs, which must not be overwritten by custom code
* Custom code should be placed in /apps, /content, and /conf

## <p>Impact on 6.4 Upgrades</p>
When upgrading to AEM 6.4, a large subset of the content under /etc will be duplicated in other folders in the repository. These new locations are the preferred locations in which the content is referenced. However, every attempt has been made for the AEM 6.4 upgrade to be backwards compatible with the previous locations in the /etc folder and so in most cases the old locations will continue to be referenced by AEM code until changes are actively -- and in many cases manually -- made in a customer's application. From a timeline perspective, there are two categories of changes:

* With 6.4 Upgrade - a handful of the /etc restructuring changes are not backwards compatible and thus modifications should be planned and implemented as part of the AEM 6.4 upgrade.
* Prior to 6.5 Upgrade - the vast majority of the /etc restructuring changes can be deferred until some time in the future post-upgrade. As previosuly mentioned, AEM 6.4 code will continue to reference the old locations until the modifications are implemented as part of a customer release. While there is no forced timeline for which the changes should be made, it is recommended that they are made before the 6.5 upgrade since future features may rely on the new locations being referenced. Also, documentation for a given feature will by convention reference the new locations and it could thus be confusing if the old locations are still being used.

<!-- 

Comment Type: annotation
Last Modified By: dgonzale
Last Modified Date: 2018-05-24T14:16:39.210-0400

Not sure if in this or the next section, it might be worth calling out that not all changes will be required for all customers; but only if the customer is using this functionality (even within a section). Each row must be evaluated if it will affect the customer AEM installation/deployment.

 -->

### Restructuring Guidance
While planning for an upgrade to AEM 6.4, the following per-solution pages should be referenced in order to assess the work effort:

* [Repository restructuring common to all AEM solutions](all-repository-restructuring-in-aem-6-4.md)
* [AEM Sites repository restructuring](sites-repository-restructuring-in-aem-6-4.md)
* [AEM Assets repository restructuring](assets-repository-restructuring-in-aem-6-4.md)
* [AEM Assets Dynamic Media repository restructuring](dynamicmedia-repository-restructuring-in-aem-6-4.md)
* [AEM Forms repository restructuring](forms-repository-restructuring-in-aem-6-4.md)
* [AEM Communities repository restructuring](communities-repository-restructuring-in-aem-6-4.md)
* [AEM Commerce repository restructuring](ecommerce-repository-restructuring-in-aem-6-4.md)

Each page contains two sections corresponding to the urgency of the necessary changes. Anything under the "With 6.4 Upgrade" section should be tackled as part of the AEM 6.4 upgrade project. Anything under the "Prior to 6.5 Upgrade" can be optionally deferred until post-upgrade.

Each entry on the page includes a "Restructuring guidance" field, which details the recommended technical strategy for aligning with the new 6.4  respository  model so that the new locations are referenced for content previously located under the /etc folder. An additional "Notes" field provides any additional useful context.
