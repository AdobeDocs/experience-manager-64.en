---
title: Enabling CRXDE Lite in AEM
seo-title: Enabling CRXDE Lite in AEM
description: null
seo-description: Learn how to enable CRXDE Lite in AEM.
uuid: 680882f3-cb7b-472d-a779-a71704214752
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: 6bedf365-548c-48b8-a178-933f302d699a
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Enabling CRXDE Lite in AEM{#enabling-crxde-lite-in-aem}

In order to ensure that AEM installations are as secure as possible, the security checklist recommends [disabling WebDAV](../../administering/using/security-checklist.md#main-pars-par8-bqqser-refd) in production environments.

However, CRXDE Lite depends on the `org.apache.sling.jcr.davex` bundle to function properly, so disabling WebDAV will effectively disable CRXDE Lite as well.

When this happens, browsing to `http://serveraddress:4502/crx/de/index.jsp` will display an empty root node, and all HTTP requests to CRXDE Lite resources will fail:

```xml
404 Resource at '/crx/server/crx.default/jcr:root/.1.json' not found: No resource found
```

While this recommendation is intended to reduce attack surfaces as much as possible, system administrators might sometimes need access to CRXDE Lite in order to browse content or debug issues on production instances.

If disabled, you can turn CRXDE Lite on by following the below procedure:

1. Go to the OSGi Components console at `http://localhost:4502/system/console/components`
1. Search for the following component:

    * `org.apache.sling.jcr.davex.impl.servlets.SlingDavExServlet`

1. Click the wrench icon next to it in order to see its configuration options:

   ![](assets/chlimage_1-93.png)

1. Create the following configuration:

    * **Root path:** `/crx/server`
    
    * Tick the box under **Use absolute URIs**.

1. When finished using CRXDE Lite, make sure you disable WebDAV again.

You can also enable CRXDE Lite via cURL, by running this command:

```shell
curl -u admin:admin -F "jcr:primaryType=sling:OsgiConfig" -F "alias=/crx/server" -F "dav.create-absolute-uri=true" -F "dav.create-absolute-uri@TypeHint=Boolean" http://localhost:4502/apps/system/config/org.apache.sling.jcr.davex.impl.servlets.SlingDavExServlet
```

#### Other Resources {#other-resources}

For more information on AEM 6 security features, see the following pages:

* [The AEM Security Checklist](../../administering/using/security-checklist.md)
* [Running AEM in Production Ready Mode](../../administering/using/production-ready.md)

