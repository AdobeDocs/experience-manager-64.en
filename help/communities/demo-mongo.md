---
title: How to Setup MongoDB for Demo
seo-title: How to Setup MongoDB for Demo
description: How to setup MSRP for one author instance and one publish instance
seo-description: How to setup MSRP for one author instance and one publish instance
uuid: d2035a9e-f05c-4f90-949d-7cdae9646750
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 0b126218-b142-4d33-a28c-a91ab4fe99ac
---

# How to Setup MongoDB for Demo{#how-to-setup-mongodb-for-demo}

## Introduction {#introduction}

This tutorial describes how to setup [MSRP](/help/communities/msrp.md) for* one author *instance and *one publish* instance.

With this setup, the community content is accessible from both author and publish environments without needing to forward or reverse replicate user generated content (UGC).

This configuration is suitable for* non-production* environments such as for development and/or demonstration.

**A *production* environment should:**

* run MongoDB with a replica set
* use SolrCloud
* contain multiple publisher instances

## MongoDB {#mongodb}

### Install MongoDB {#install-mongodb}

* Download MongoDB from [https://www.mongodb.org/](https://www.mongodb.org/)

    * choice of OS:

        * Linux
        * Mac 10.8
        * Windows 7

    * choice of version:

        * at a minimum, use version 2.6

* Basic configuration

    * follow the MongoDB install instructions
    * configure for mongod

        * no need to configure mongos or sharding

    * the installed MongoDB folder will be referred to as &lt;mongo-install&gt;
    * the defined data directory path will be referred to as &lt;mongo-dbpath&gt;

* MongoDB may run on same host as AEM or run remotely

### Start MongoDB {#start-mongodb}

* &lt;mongo-install&gt;/bin/mongod --dbpath &lt;mongo-dbpath&gt;

This will start a MongoDB server using default port 27017.

* For Mac, increase ulimit with start arg 'ulimit -n 2048'

>[!NOTE]
>
>If MongoDB is started *after *AEM, **restart **all **AEM **instances so they properly connect to MongoDB.

### Demo Production Option: Setup MongoDB Replica Set {#demo-production-option-setup-mongodb-replica-set}

The following commands are an example of setting up a replica set with 3 nodes on localhost:

* bin/mongod --port 27017 --dbpath data --replSet rs0&
* bin/mongo

    * cfg = {"_id": "rs0","version": 1,"members": [{"_id": 0,"host": "127.0.0.1:27017"}]}
    * rs.initiate(cfg)

* bin/mongod --port 27018 --dbpath data1 --replSet rs0&
* bin/mongod --port 27019 --dbpath data2 --replSet rs0&
* bin/mongo

    * rs.add("127.0.0.1:27018") 
    * rs.add("127.0.0.1:27019")
    * rs.status()

## Solr {#solr}

### Install Solr {#install-solr}

* Download Solr from [Apache Lucene](https://archive.apache.org/dist/lucene/solr/):

    * suitable for any OS 
    * use version 4.10 or version 5
    * Solr requires Java 1.7 or greater

* Basic configuration

    * follow 'example' Solr setup
    * no service is needed
    * the installed Solr folder will be referred to as &lt;solr-install&gt;

### Configure Solr for AEM Communities {#configure-solr-for-aem-communities}

To configure a Solr collection for MSRP for demo, there are two decisions to be made (select the links to main documentation for details):

1. run Solr in standalone or [SolrCloud mode](/help/communities/msrp.md#solrcloudmode)
1. install [standard](/help/communities/msrp.md#installingstandardmls) or [advanced](/help/communities/msrp.md#installingadvancedmls) multilingual search (MLS)

### Standalone Solr {#standalone-solr}

The method for running Solr may differ depending on the version and manner of installation. The [Solr reference guide](https://archive.apache.org/dist/lucene/solr/ref-guide/) is the authoritative documentation.

For simplicity, using version 4.10 as an example, start Solr in standalone mode:

* cd to &lt;solrinstall&gt;/example
* java -jar start.jar

This will start a Solr HTTP server using default port 8983. You can browse to the Solr Console to get a Solr console for testing.

* default Solr console: [http://localhost:8983/solr/](http://localhost:8983/solr/)

>[!NOTE]
>
>If Solr Console is not available, check the logs under &lt;solrinstall&gt;/example/logs. Look to see if SOLR is trying to bind to a specific hostname that cannot be resolved (e.g. "user-macbook-pro").
>
>If so, update etc/hosts file with a new entry for this hostname (e.g 127.0.0.1 user-macbook-pro) and Solr will start properly.

### SolrCloud {#solrcloud}

To run a very basic (not production) solrCloud setup, start solr with:

* java -Dbootstrap_confdir=./solr/collection1/conf -Dbootstrap_conf=true -DzkRun -jar start.jar

## Identify MongoDB as Common Store {#identify-mongodb-as-common-store}

Launch the author and publish AEM instances, if necessary.

If AEM was running before MongoDB was started, then the AEM instances will need to be restarted.

Follow the instructions on the main documentation page: [MSRP - MongoDB Common Store](/help/communities/msrp.md)

## Test {#test}

To test and verify the MongoDB common store, post a comment on the publish instance and view it on the author instance, as well as view the UGC in MongoDB and Solr:

1. on the publish instance, browse to the [Community Components Guide](http://localhost:4503/content/community-components/en/comments.html) page and select the Comments component.
1. sign in to post a comment:
1. enter text in the comment text entry box and click **Post**

   ![](assets/chlimage_1-191.png)

1. Simply view the comment on the [author instance](http://localhost:4502/content/community-components/en/comments.html) (likely still signed in as admin / admin).

   ![](assets/chlimage_1-192.png)

   Note: while there are JCR nodes under the *asipath *on author, these are for the SCF framework. The actual UGC is not in JCR, it is in the MongoDB.

1. view the UGC in mongodb (communities &gt; Collections &gt; content)

   ![](assets/chlimage_1-193.png)

1. view the UGC in Solr:

    * browse to Solr dashboard: [http://localhost:8983/solr/](http://localhost:8983/solr/)
    * user 'core selector' to select 'collection1'
    * select `Query`
    * select `Execute Query`

   ![](assets/chlimage_1-194.png)

## Troubleshooting {#troubleshooting}

### No UGC Appears {#no-ugc-appears}

1. Make sure MongoDB is installed and running properly.

1. Make sure MSRP has been configured to be the default provider:

    * On all author and publish AEM instances, revisit the [Storage Configuration console](/help/communities/srp-config.md)
     
    or check the AEM repository:

    * in JCR, if [/etc/socialconfig](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/)

        * does not contain an [srpc](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc) node, it means the storage provider is JSRP
        * if the srpc node exists and contains node [defaultconfiguration](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc/defaultconfiguration), the defaultconfiguration's properties should define MSRP to be the default provider

1. Make sure AEM was restarted after MSRP selected.
