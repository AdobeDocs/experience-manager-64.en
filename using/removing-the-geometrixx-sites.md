---
title: Removing the Geometrixx Sites
seo-title: Removing the Geometrixx Sites
description: null
seo-description: Learn how to remove the sample Geometrixx content.
uuid: 08939fee-6a26-4c70-9fe7-2c950ad62f4f
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/removing-the-geometrixx-sites
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 28 01.045-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 50 33.237-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: dc96d92b-b5d2-408e-a904-13de3b8c7140
firstPublishExternalDate: 2018-04-03T08:50:33.212-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 04 01.747-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:50:33.212-0400
lochandoffdate: 2018-04-30T03 28 01.044-0400
lr-lastreplicatedby: carlino@adobe.com
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Removing the Geometrixx Sites
publishexternaldate: 2018-04-03T08 50 33.212-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/removing-the-geometrixx-sites.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/upgrade/removing-the-geometrixx-sites
sha1: 7e5a54b03512008c8212ef5f5cc4b665d6a05a0e
topicBrowsingSortDate: 2018-04-03T08:50:33.212-0400
index: y
internal: n
snippet: y
translate: y
---

# Removing the Geometrixx Sites

AEM comes with a set of sample Geometrixx websites. You can remove this sample content through the **Package Manager**.

The individual geometrixx-related packages are:

* `cq-geometrixx-outdoors-ugc-pkg-*<version>*.zip`
* `cq-geometrixx-pkg-*<version>*.zip`
* `cq-content-mac-*<version>*.zip`
* `cq-geometrixx-login-pkg-*<version>*.zip`
* `cq-geometrixx-users-pkg-*<version>*.zip`
* `cq-geometrixx-workflow-pkg-*<version>*.zip`
* `cq-geometrixx-outdoors-pkg-*<version>*.zip`
* `cq-geometrixx-commons-pkg-*<version>*.zip`
* `cq-geometrixx-media-pkg-*<version>*.zip`

To remove an individual package, simple click **Uninstall** on that package.

There is also a super-package:

* `cq-geometrixx-all-pkg-5.6.12.zip`

This package includes all the above individual packages. To remove all the geometrixx-related content at once, click **Uninstall** on this package. The super-package will go into the uninstalled state, and all the individual packages will disappear from the package manager view.

You have now an "empty" AEM instance without any demonstration sites.

>[!NOTE]
>
>When upgrading, geometrixx sites are automatically re-installed. You may need to remove geometrixx web sites after upgrading if you do not want these samples.

