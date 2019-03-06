---
title: Cloud Services
seo-title: Cloud Services
description: null
seo-description: null
page-status-flag: never-activated
uuid: 395c35be-3d20-4637-a763-fd43509ec842
contentOwner: raiman
discoiquuid: db8d5a75-a568-42bb-b257-977cdda3f392
noindex: true
index: y
internal: n
snippet: y
---

# Cloud Services{#cloud-services}

## Introduction {#introduction}

In previous versions of AEM, cloud services were located under Tools &gt; Deployment. With AEM 6.4, there is a new menu tab called Cloud Services, at the same level as Tools. The tab allows customers to create and configure out-of-the-box integrations, both internal and external. There is also a new location structure that allows for a layered approach, providing more flexibility for defining cloud services configurations.

## Structure {#structure}

The configuration wizard will force customers to create cloud configurations under /conf, and we advise that customers create them under &lt;my-app&gt;, which should be listed in the browser. Upon creating a cloud service config, the system will place it under /conf/&lt;my-app&gt;/settings/cloudconfigs/&lt;cloud_service&gt;.

The following screenshot exemplifies how the structure looks for we-retail cloud configurations:

![](assets/cloud_services_structure.png)

>[!NOTE]
>
>Customers occasionally create custom cloud services and the guidance for 6.4 is to use the legacy approach from 6.3. Creating custom cloud services in 6.3 is [documented here](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/extending-cloud-config-custom-cloud.html).

>[!NOTE]
>
>Any pre-existing cloud service already configured under /etc will continue to exist and work without any change.

## Cloud Services {#cloud-services}

With AEM 6.4, we have a new menu tab called Cloud Services, at the same level as Tools. It includes the following cards:

* **Legacy Cloud Services** - this is the card that was in Legacy versions under Tools > Deployment. Customers will need to access it for any cloud service that hasn't been provided as an independent card under the same menu tab. Any cloud services created using this card will appear under `/etc/cloudservices`. Note that as of 6.4, some cloud services under this card will no longer be editable, instead assuming that new cloud services will be created with the new paradigm. 

* **An assortment of independent cloud services cards - **Context aware configurations allow for a layered approach where customers can include configurations in /libs/settings, /apps/settings, /conf/global/settings, and /conf/<tenant>/settings. For example, /libs/settings is overridden by new properties in /apps/settings, which is overridden by /conf/global/settings and so on. Note that run-mode specific settings are supported with this layered approach as well (for example `/apps/settings.author`).

### Creating Cloud Service Configurations {#creating-cloud-service-configurations}

We advise customers to create (new 6.4, non-legacy) cloud configurations under /conf/&lt;my-app&gt;/settings/cloudconfigs/.

In order to create the the &lt;my-app&gt; folder under /conf, the Configuration browser (Tools &gt; Configuration browser) must be used to create sibling folders to the pre-existing global folder, as illustrated below.

(Note that in the picture below, 6.4 will no longer have the author/publish aware configurations checkbox)

Creating the my-app folder:

![]()

>[!NOTE]
>
>The configuration browser manages the configuration containers below /conf, as by default only /conf/global would be there. It is agnostic of the contents though, so the configurations themselves are managed below /conf/&lt;container&gt;/settings/cloudconfigs by each console as required.

In order to create cloud service configurations, do the following:

1. Go to Tools &gt; Cloud Services and click the desired card (for example the Recaptcha card). Clicking it brings up an interface similar to the config browser.
1. Click **Create** to configure it.
1. After the configuration is created check the location/settings.

### Assigning cloud service configurations to pages {#assigning-cloud-service-configurations-to-pages}

To assign cloud service configurations to pages, follow these steps:

1. Step text
1. Step text
1. Step text
1. Step text
1. Step text

