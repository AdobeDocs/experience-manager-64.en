---
title: Assessing the Upgrade Complexity with the Pattern Detector
seo-title: Assessing the Upgrade Complexity with the Pattern Detector
description: null
seo-description: Learn how to use the Pattern Detector to assess the complexity of your upgrade.
uuid: c8ce5d3d-f275-4154-94f4-61b9af2ed9d4
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/pattern-detector
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-08-01T05 33 14.316-0400
cq-lastmodifiedby: arkadius
cq-lastreplicated: 2018-08-01T05 33 47.605-0400
cq-lastreplicatedby: arkadius
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 26849d62-6b15-4bad-9f6d-b747979ad45a
firstPublishExternalDate: 2018-04-04T04:17:40.921-0400
isreadyforlocalization: false
jcr-created: 2018-03-22T07 28 45.442-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-11T04:33:15.387-0400
lochandoffdate: 2018-04-30T03 26 37.953-0400
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/upgrading
pagecreatedat: en
publishexternaldate: 2018-04-11T04 33 15.387-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/pattern-detector.html
sha1: 66161697b518b54c367966d1ff4f14a992f07ffb
topicBrowsingSortDate: 2018-04-11T04:33:15.387-0400
unpublishinternaldate: 2018-03-30T04 56 09.255-0400
index: y
internal: n
snippet: y
---

# Assessing the Upgrade Complexity with the Pattern Detector

## Overview

This feature allows you to check existing AEM instances for their upgradability by detecting patterns in use that:

1. Violate certain rules and are done in areas that will be affected or overwritten by the upgrade
1. Use an AEM 6.x feature or an API that is not backwards compatible on AEM 6.4 and can potentially break after upgrade.

This could serve as an assessment of the development effort that is involved in upgrading to AEM 6.4.

## How to Set Up

The Pattern detector is released as part of the new `pre-upgrade-package` for source AEM versions 6.1 to 6.3 and can be installed using the [Package Manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager).

See these links to packages for each AEM 6 version (starting from AEM 6.1):

* [AEM 6.1](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq610/featurepack/pre-upgrade-package-cq61)
* [AEM 6.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq620/featurepack/pre-upgrade-package-cq62)
* [AEM 6.3](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/featurepack/pre-upgrade-package-cq63)

## How to Use

>[!NOTE]
>
>Pattern Detector can run on any environment, including local development instances. However, in order to:
>
>* increase the detection rate
>* avoid any slowdowns on business critical instances  
  
>
>both at the same time it is recommended to run it **on staging environments** that are as close as possible to production ones in the areas of user applications, content and configurations.

You can use several methods to check the Pattern Detector output:

* **Via the Felix Inventory console:**

1. Go to the AEM Web Console by browsing to *http://serveraddress:serverport/system/console/configMgr*
1. Select **Status - Pattern Detector** as shown in the image below:

   ![](assets/screenshot-2018-2-5pattern-detector.png)

* **Via a reactive text based or regular JSON interface** 

* **Via a reactive JSON lines interface, **that generates a separate JSON document in each line.

Both of these methods are detailed below:

## Reactive Interface

The reactive interface allows for the processing of the violation report as soon as a suspicion is detected.

The output is currently available under 2 URLs:

1. Plain text interface  
1. JSON interface

## Handling the Plain Text Interface

The information in the output is formatted as a series of event entries. There are two channels - one for publishing violations and the second for publishing the current progress.

They can be obtained by using the following commands:

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.txt | tee patterns-report.log | grep SUSPICION
```

The output will look like this:

```
2018-02-13T14:18:32.071+01:00 [SUSPICION] The pattern=ECU/extraneous.content.usage was found by detector=ContentAccessDetector with id=a07fd94318f12312c165e06d890cbd3c2c8b8dad0c030663db8b4c800dd7c33f message="Cross-boundary overlay of internal marked path /libs/granite/operations/components/commons/commons.jsp/jcr:content referenced at /apps/granite/operations/components/commons/commons.jsp/jcr:content with properties redefined: jcr:lastModifiedBy, jcr:mimeType, jcr:data, jcr:lastModified, jcr:uuid". More info at=https://www.adobe.com/go/aem6_EC
```

The progress can be filtered using the `grep` command:

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.txt | tee patterns-report.log | grep PROGRESS
```

Which results in the following output:

```
2018-02-13T14:19:26.909+01:00 [PROGRESS] emitted=127731/52 MB patterns (from=6.4), analysed=45780/16 MB items, found=0 suspicions so far in period=PT5.005S (throughput=34667 items/sec)
2018-02-13T14:19:31.904+01:00 [PROGRESS] emitted=127731/52 MB patterns (from=6.4), analysed=106050/39 MB items, found=0 suspicions so far in period=PT10S (throughput=23378 items/sec)
2018-02-13T14:19:35.685+01:00 [PROGRESS] Finished in period=PT13.782
```

## Handling the JSON Interface

Similarly, JSON can be processed using the [jq tool](https://stedolan.github.io/jq/) as soon as it is published.

<!-- 

Comment Type: remark
Last Modified By: Alexandru Sarchiz (sarchiz)
Last Modified Date: 2018-04-02T03:52:41.470-0400

<p>We should describe here what jq comes from: https://stedolan.github.io/jq/ and what is the purpose of this tool.</p> 
<p>AS: I think a link to to github would suffice.</p>

 -->

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.json | tee patterns-report.json | jq --unbuffered -C 'select(.suspicion == true)'
```

With the output:

```
{
  "timestamp": "2018-02-13T14:20:18.894+01:00",
  "suspicion": true,
  "pattern": {
    "code": "ECU",
    "type": "extraneous.content.usage",
    "detective": "ContentAccessDetector",
    "moreInfo": "https://www.adobe.com/go/aem6_ECU"
  },
  "item": {
    "id": "a07fd94318f12312c165e06d890cbd3c2c8b8dad0c030663db8b4c800dd7c33f",
    "message": "Cross-boundary overlay of internal marked path /libs/granite/operations/components/commons/commons.jsp/jcr:content referenced at /apps/granite/operations/components/commons/commons.jsp/jcr:content with properties redefined: jcr:lastModifiedBy, jcr:mimeType, jcr:data, jcr:lastModified, jcr:uuid"
  }
}
```

The progress is reported every 5 seconds and can fetched by excluding other messages than those marked as suspicions:

```shell
curl -Nsu 'admin:admin' http://localhost:4502/system/console/status-pattern-detector.json | tee patterns-report.json | jq --unbuffered -C 'select(.suspicion == false)'
```

With the output:

```
{
  "suspicion": false,
  "timestamp": "2018-02-13T14:21:17.279+01:00",
  "type": "PROGRESS",
  "database": {
    "patternsEmitted": 127731,
    "patternsEmittedSize": "52 MB",
    "databasesEmitted": [
      "6.4"
    ]
  },
  "state": {
    "itemsAnalysed": 57209,
    "itemsAnalysedSize": "26 MB",
    "suspicionsFound": 0
  },
  "progress": {
    "elapsedTime": "PT5.003S",
    "elapsedTimeMilliseconds": 5003,
    "itemsPerSecond": 36965
  }
}
{
  "suspicion": false,
  "timestamp": "2018-02-13T14:21:22.276+01:00",
  "type": "PROGRESS",
  "database": {
    "patternsEmitted": 127731,
    "patternsEmittedSize": "52 MB",
    "databasesEmitted": [
      "6.4"
    ]
  },
  "state": {
    "itemsAnalysed": 113194,
    "itemsAnalysedSize": "46 MB",
    "suspicionsFound": 0
  },
  "progress": {
    "elapsedTime": "PT10S",
    "elapsedTimeMilliseconds": 10000,
    "itemsPerSecond": 24092
  }
}
{
  "suspicion": false,
  "timestamp": "2018-02-13T14:21:25.762+01:00",
  "type": "FINISHED",
  "database": {
    "patternsEmitted": 127731,
    "patternsEmittedSize": "52 MB",
    "databasesEmitted": [
      "6.4"
    ]
  },
  "state": {
    "itemsAnalysed": 140744,
    "itemsAnalysedSize": "63 MB",
    "suspicionsFound": 1
  },
  "progress": {
    "elapsedTime": "PT13.486S",
    "elapsedTimeMilliseconds": 13486,
    "itemsPerSecond": 19907
  }
}
{
  "suspicion": false,
  "type": "SUMMARY",
  "suspicionsFound": 1,
  "totalTime": "PT13.487S"
}
```

>[!NOTE]
>
>The recommended approach is to save the whole output from curl into the file and then process it via `jq` or `grep` to filter information type.

## Detection scope

Currently Pattern Detector allows to check:

* OSGi bundles exports and imports mismatch
* Sling resource types and super types (with search-path content overlays) overusages
* definitions of Oak indices (compatibility)
* VLT packages (overuse)
* rep:User nodes compatibility (in context of OAuth configuration)

