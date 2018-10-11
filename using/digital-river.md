---
title: Digital River
seo-title: Digital River
description: null
seo-description: Learn how to install eCommenrce with Digital River.
uuid: 89058c2e-ed67-4a8b-97b6-ac2fc5178975
content-encoding: UTF-8
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/digital-river
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 50.750-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 40 51.869-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 6568ad13-be09-41e0-9513-636c4f6bc590
disttype: dist5
firstPublishExternalDate: 2017-10-31T16:17:58.641-0400
gnavtheme: light
groupsectionnavitems: no
hidemerchandisingbar: inherit
hidepromocomponent: inherit
isreadyforlocalization: false
jcr-created: 2017-12-01T19 06 16.236-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:40:50.925-0400
lochandoffdate: 2018-04-30T03 26 50.750-0400
lr-lastreplicatedby: carlino@adobe.com
modalsize: 426x240
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Digital River
pagetitle: Deploying eCommerce with Digital River
publishexternaldate: 2018-04-03T08 40 50.925-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/digital-river.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/ecommerce/digital-river
sha1: 5848a33429c204f714c6a0e0c12d0f34bfaf4557
topicBrowsingSortDate: 2018-04-03T08:40:50.925-0400
index: y
internal: n
snippet: y
translate: y
---

# Digital River

Deploying the necessary eCommerce packages will provide the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with a Digital River implementation (including a demonstration catalog based on We.Retail).

This catalog is available under the Language Masters English branch ( `/content/we-retal/language-masters/en`) of the We.Retail site.

## Prerequisites
You will need to reach out to your Digital River Account Manager to get an API key, Secret, and Endpoint. The connector won’t work without these.

## Installation of eCommerce with Digital River

>[!NOTE]
>
>This section must be performed by a user with package installation permissions.

Once you have your API key, you can install the package from package share on all of your instances:

1. Navigate to package share on your AEM instance: [http://localhost:4502/crx/packageshare/login.html](http://localhost:4502/crx/packageshare/login.html).
1. Enter your Adobe ID credentials or create an account if you do not already have one.
1. Search for Digital River and select the **Digital River Commerce Connector **package.

   ![](assets/digital-river/chlimage_1.jpeg)

1. Click **Download**, then accept the End User License Agreement.
1. Once it's downloaded, click **Downloaded **and it will bring you to the package manager.
1. Click the **Install** button next to the newly downloaded package.

   ![](assets/digital-river/chlimage_1-1.jpeg)

## Configuration

>[!NOTE]
>
>This section must be performed by an administrator.

To Configure Digital River in your AEM instance:

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Click **Digital River Commerce Provider**.

   ![](assets/digital-river/chlimage_1-2.jpeg)

1. Enter the following information:

    * **Digital River Server**: Use the API endpoint provided by your Account or Project Manager.
    * **Digital River API Key**: Use the API Key provided by your Account or Project Manager.
    * **Digital River Secret**: Use the Secret provided by your Account or Project Manager.
    * **Digital River Post Checkout Redirect URL**: Use the URL pointing to the post checkout page for this instance. If this is a publish instance, use the Dispatcher URL.
    * **API Test Mode**: Check this box if this is not a Production Environment.

1. Click **Save**.

