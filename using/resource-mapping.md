---
title: Resource Mapping
seo-title: Resource Mapping
description: null
seo-description: Learn how to define redirects, vanity URLs and virtual hosts for AEM by using resource mapping.
uuid: 43d5a543-440b-4d82-bb1b-5b57852672b4
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/resource-mapping
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 29 07.106-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 45 55.407-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 47945ba1-77b4-41a9-a88e-22cacc9b8628
firstPublishExternalDate: 2017-10-31T16:17:39.350-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 04 33.124-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:45:55.157-0400
lochandoffdate: 2018-04-30T03 29 07.106-0400
lr-lastreplicatedby: carlino@adobe.com
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Resource Mapping
publishexternaldate: 2018-04-03T08 45 55.157-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/resource-mapping.html
qaDate: 2017-10-12T21:46:58.665-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/resource-mapping
sha1: e95e1c6c9c0cdb53e3b9e4282ffc3133f4840c36
topicBrowsingSortDate: 2018-04-03T08:45:55.157-0400
index: y
internal: n
snippet: y
translate: y
---

# Resource Mapping

Resource mapping is used to define redirects, vanity URLs and virtual hosts for AEM.

For example, you can use these mappings to:

* Prefix all requests with `/content` so that the internal structure is hidden from the visitors to your website.
* Define a redirect so that all requests to the `/content/en/gateway` page of your website are redirected to `http://gbiv.com/`.

One possible HTTP mapping [prefixes all requests to `localhost:4503` with `/content`](#Configuringaninternalredirecttocontent). A mapping like this could be used to hide the internal structure from the visitors to the website as it allows:

`localhost:4503/content/geometrixx/en/products.html`

to be accessed using:

`localhost:4503/geometrixx/en/products.html`

as the mapping will automatically add the prefix `/content` to `/geometrixx/en/products.html`.

>[!CAUTION]
>
>Vanity URLs do not support regex patterns.

>[!NOTE]
>
>See the Sling documentation, and [Mappings for Resource Resolution](http://sling.apache.org/site/resources.html) and [Resources](http://sling.apache.org/site/mappings-for-resource-resolution.html) for further information.

### Viewing Mapping Definitions
The mappings form two lists that the JCR Resource Resolver evaluates (top-down) to find a match.

These lists can be viewed (together with configuration information) under the **JCR ResourceResolver** option of the Felix console; for example, `http://<*host*>:<*port*>/system/console/jcrresolver`:

* Configuration  
  Shows the current configuration (as defined for the [Apache Sling Resource Resolver](osgi-configuration-settings.md#ApacheSlingResourceResolver)).

* Configuration Test  
  This allows you to enter a URL or resource path. Click **Resolve** or **Map** to confirm how the system will transform the entry.  

* **Resolver Map Entries** 
  The list of entries used by the ResourceResolver.resolve methods to map URLs to Resources.

* **Mapping Map Entries** 
  The list of entries used by the ResourceResolver.map methods to map Resource Paths to URLs.

The two lists show various entries, including those defined as defaults by the application(s). These often aim to simplify URLs for the user.

The lists pair a **Pattern**, a regular expression matched to the request, with a **Replacement** that defines the redirection to impose.

For example, the:

**Pattern ** `^[^/]+/[^/]+/welcome$`

will trigger the:

**Replacement** `/libs/cq/core/content/welcome.html`.

to redirect a request:

`http://localhost:4503/welcome` ``

to:

`http://localhost:4503/libs/cq/core/content/welcome.html`

New mapping definitions are created within the repository.

>[!NOTE]
>
>There are many resources available that help explain how to define regular expressions; for example [http://www.regular-expressions.info/](http://www.regular-expressions.info/).

### Creating Mapping Definitions in AEM
In a standard installation of AEM you can find the folder:

`/etc/map/http`

This is the structure used when defining mappings for the HTTP protocol. Other folders ( `sling:Folder`) can be created under `/etc/map` for any other protocols that you want to map.

#### Configuring an Internal Redirect to /content
To create the mapping that prefixes any request to http://localhost:4503/ with `/content`:

1. Using CRXDE navigate to `/etc/map/http`.  

1. Create a new node:

    * **Type** `sling:Mapping`  
      This node type is intended for such mappings, though its use is not mandatory.  
    
    * **Name** `localhost_any`

1. Click **Save All**.
1. **Add** the following properties to this node:

    * **Name** `sling:match`

        * **Type** `String` 
        
        * **Value** `localhost.4503/`

    * **Name** `sling:internalRedirect`

        * **Type** `String`  
        
        * **Value** `/content/`

1. Click **Save All**.

This will handle a request such as:  
`localhost:4503/geometrixx/en/products.html`  
as if:  
`localhost:4503/content/geometrixx/en/products.html`  
had been requested.

>[!NOTE]
>
>See [Resources](http://sling.apache.org/site/mappings-for-resource-resolution.html) in the Sling Documentation for further information about the sling properties available and how they can be configured.

>[!NOTE]
>
>You can use `/etc/map.publish` to hold the configurations for the publish environment. These must then be replicated, and the new location ( `/etc/map.publish`) configured for the **Mapping Location** of the [Apache Sling Resource Resolver](osgi-configuration-settings.md#ApacheSlingResourceResolver) of the publish environment.

