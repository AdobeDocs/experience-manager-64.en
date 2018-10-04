---
title: Expiration of Static Objects
seo-title: Expiration of Static Objects
description: null
seo-description: Learn how to configure AEM so that static objects do not expire (for a reasonable period of time).
uuid: c13891ba-3161-46fa-8ddc-5c597d369399
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/expiration-static-objects
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 52.905-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 44 12.576-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 83d568eb-43a1-4b19-bce9-3d48dd0dd8be
firstPublishExternalDate: 2017-10-31T16:17:58.075-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 06 11.568-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:44:09.428-0400
lochandoffdate: 2018-04-30T03 26 52.905-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Expiration of Static Objects
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 44 09.428-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/expiration-static-objects.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/expiration-static-objects
sha1: 8ebcb95eb6e47670f45a90e0aa494b9430741720
topicBrowsingSortDate: 2018-04-03T08:44:09.428-0400
index: y
internal: n
snippet: y
translate: y
---

# Expiration of Static Objects

Static objects (for example, icons) do not change. Therefore the system should be configured so that they do not expire (for a reasonable period of time) and so reduce unnecessary traffic.

This has the following impact:

* Offloads requests from the server infrastructure.
* Increases performance of page loading, as the browser caches objects in the browser cache.

Expirations are specified by the HTTP standard regarding "expiration" of files (see, for example, chapter 14.21 of [RFC 2616](http://www.ietf.org/rfc/rfc2616.txt) " Hypertext Transfer Protocol -- HTTP 1.1"). This standard uses the header to allow clients to cache objects until they are considered stale; such objects are cached for the specified amount of time without any status check being made to the originating server.

>[!NOTE]
>
><p>This configuration is completely separate from (and will not work for) the Dispatcher.</p> <p>The purpose of the Dispatcher is to cache data in front of AEM.<br> </p>

All files, which are not dynamic and which do not change over time, can and should be cached. The configuration for the Apache HTTPD server could look like one of the following - dependent on the environment:

>[!CAUTION]
>
><p>You must be careful when you define the time period during which an object is considered to be up-to-date. As there is <i>no check until the specified time period has expired</i>, the client can end up presenting old content from the cache.</p>

1. **For an Author instance:**

   ```xml
   LoadModule expires_module modules/mod_expires.so
   <Location /libs>
     ExpiresByType text/css "access plus 1 month"
     ExpiresByType text/javascript "access plus 1 month"
     ExpiresByType image/png "access plus 1 month"
     ExpiresByType image/gif "access plus 1 month"
   </Location>
   ```

   This allows the intermediate cache (e.g. the browser cache) to store CSS, Javascript, PNG and GIF files for up to one month, until they expire. This means they do not need to be requested from AEM or the webserver, but can remain in the browser cache.

   Other sections of the site should not be cached on an author instance, as they are subject to change at any time.

1. **For a Publish instance:**

   ```xml
   LoadModule expires_module modules/mod_expires.so
   <Location /content>
     ExpiresByType text/css "access plus 1 day"
     ExpiresByType text/javascript "access plus 1 day"
     ExpiresByType image/png "access plus 1 day"
     ExpiresByType image/gif "access plus 1 day"
   </Location>
   <Location /etc/designs>
     ExpiresByType text/css "access plus 1 day"
     ExpiresByType text/javascript "access plus 1 day"
     ExpiresByType image/png "access plus 1 day"
     ExpiresByType image/gif "access plus 1 day"
   </Location>
   
   ```

   This allows the intermediate cache (e.g. the browser cache) to store CSS, Javascript, PNG and GIF files for up to one day in client caches. Although this example illustrates global settings for everything below `/content` and `/etc/designs`, you should make it more granular.

   Depending on how often your site is updated, you can also consider caching HTML pages. A reasonable time period would be 1 hour:

   ```xml
   <Location /content>
     ExpiresByType text/html "access plus 1 hour"
   </Location>
   ```

After you have configured the static objects, scan `request.log`, while selecting pages that hold such objects, to confirm that no (unnecessary) requests are being made for static objects.
