---
title: Solr Configuration for SRP
seo-title: Solr Configuration for SRP
description: An Apache Solr installation may be shared between the node store (Oak) and common store (SRP) by using different collections
seo-description: An Apache Solr installation may be shared between the node store (Oak) and common store (SRP) by using different collections
uuid: da93fc95-f84a-4b57-8755-05af87e05a12
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: e783d26c-9c3b-4f61-a76a-ae1890b75d03
index: y
internal: n
snippet: y
---

# Solr Configuration for SRP{#solr-configuration-for-srp}

## Solr for AEM Platform {#solr-for-aem-platform}

An [Apache Solr](http://lucene.apache.org/solr/) installation may be shared between the [node store](../../sites/deploying/using/data-store-config.md) (Oak) and [common store](../../communities/using/working-with-srp.md) (SRP) by using different collections.

If both the Oak and SRP collections are used intensively, a second Solr may be installed for performance reasons.

For production environments, [SolrCloud mode](#solrcloudmode) provides improved performance over standalone mode (a single, local Solr setup).

### Requirements {#requirements}

Download and install Apache Solr :

* [version 4.10](http://archive.apache.org/dist/lucene/solr/4.10.4/) or [version 5](http://archive.apache.org/dist/lucene/solr/5.5.3/)

* Solr requires Java 1.7 or greater
* no service is needed
* choice of run modes :

    * standalone mode
    * [SolrCloud mode](#solrcloudmode) (recommended for production environments)

* choice of Multilingual Search (MLS)

    * [Installing Standard MLS](#installingstandardmls)
    * [Installing Advanced MLS](#installingadvancedmls)

## SolrCloud Mode {#solrcloud-mode}

[SolrCloud](https://cwiki.apache.org/confluence/display/solr/SolrCloud) mode is recommended for production environments. When running in SolrCloud mode, SolrCloud must be installed and configured before installing Multilingual Search (MLS).

The recommendation is to follow the SolrCloud instructions to install :

* 3 SolrCloud nodes on same server
* an external Apache ZooKeeper

It is also recommended to configure JVM to tune memory usage and garbage collection.

#### JVM Configuration Example {#jvm-configuration-example}

```shell
JVM_OPTS="-server -Xmx2048m -XX:MaxPermSize=768M -XX:+UseConcMarkSweepGC -XX:+CMSClassUnloadingEnabled -Xloggc:../logs/gc.log -XX:+PrintGCDetails -XX:+PrintGCDateStamps -Djava.awt.headless=true"  
```

### SolrCloud Setup Commands {#solrcloud-setup-commands}

When running in SolrCloud mode, prior to MLS installation, use and knowledge of the following SolrCloud set-up commands is necessary.

#### 1. Upload a configuration to ZooKeeper {#upload-a-configuration-to-zookeeper}

Reference :  
[https://cwiki.apache.org/confluence/display/solr/Command+Line+Utilities](https://cwiki.apache.org/confluence/display/solr/Command+Line+Utilities)

Usage :  
sh ./scripts/cloud-scripts/zkcli.sh \  
-cmd upconfig \  
-zkhost *server:port* \  
-confname *myconfig-name *\  
-solrhome *solr-home-path* \  
-confdir *config-dir*

#### 2. Create a collection {#create-a-collection}

Reference :  
[https://cwiki.apache.org/confluence/display/solr/Solr+Start+Script+Reference#SolrStartScriptReference-Create  
](https://cwiki.apache.org/confluence/display/solr/Solr+Start+Script+Reference#SolrStartScriptReference-Create)

Usage :  
./bin/solr create \  
-c *mycollection-name *\  
-d *config-dir* \  
-n *myconfig-name* \  
-p *port *\  
-s *number-of-shards* \  
-rf *number-of-replicas*

#### 3. Link a collection to a configuration set {#link-a-collection-to-a-configuration-set}

Link a collection to a configuration already uploaded to ZooKeeper.

Reference :  
[https://cwiki.apache.org/confluence/display/solr/Command+Line+Utilities](https://cwiki.apache.org/confluence/display/solr/Command+Line+Utilities)

Usage :  
sh ./scripts/cloud-scripts/zkcli.sh \  
-cmd linkconfig \  
-zkhost *server:port* \  
-collection *mycollection-name* \  
-confname *myconfig-name*

### Comparison of Standard and Advanced MLS {#comparison-of-standard-and-advanced-mls}

Multilingual Search (MLS) for AEM Communities is built for the Solr platform to provide improved search across all supported languages, including English.

MLS for AEM communities is available as either Standard MLS or Advanced MLS. Standard MLS only includes Solr configuration settings, and excludes any plugins or resource files. Advanced MLS is the more comprehensive solution and includes Solr configuration settings as well as plugins and related resources

Standard MLS includes enhancements for content search for the following languages :

* English : improved stemmer for attempting to match word derivations
* Japanese : improved Japanese tokenization for half-width characters

Advanced MLS includes enhancements for content search for the following languages :

* English : replaced stemmer with lemmatizer
* German : added decompounder
* French : added elision handling
* Chinese (Simplified) : added a smarter tokenizer
* various languages : added a stemmer, stop word list, and a normalizer.

In all, the following 33 languages are supported in Advanced MLS.

| Arabic |German |Norwegian |
|---|---|---|
| Bulgarian |Greek |Polish |
| Chinese (Simplified) |Haitian Creole |Portuguese |
| Chinese (Traditional) |Hebrew |Romanian |
| Czech |Hungarian |Russian |
| Danish |Indonesian |Slovak |
| Dutch |Italian |Slovenian |
| English |Japanese |Spanish |
| Estonian |Korean |Swedish |
| Finnish |Latvian |Thai |
| French |Lithuanian |Turkish |

#### Comparison of AEM 6.1 Solr search, Standard MLS and Advanced MLS {#comparison-of-aem-solr-search-standard-mls-and-advanced-mls}

**Note **: AEM 6.1 refers to AEM 6.1 Communities FP3 and earlier.

![](assets/chlimage_1-283.png) 

### Installing Standard MLS {#installing-standard-mls}

For the SRP collection (either MSRP or DSRP), to support Standard Multilingual Search (MLS) it is necessary to modify two of Solr's configuration files :

* **schema.xml**
* **solrconfig.xml**

standard MLS files (schema.xml, solrconfig.xml) for Solr 4.10

standard MLS files (schema.xml, solrconfig.xml) for Solr 5

The Standard MLS files are stored in the AEM repository.

**Note **: While the Solr files are stored in the msrp/ folder, they are also for DSRP (no changes necessary).

**Download instructions** : replace *solrX *with *solr4 *or *solr5 *as appropriate

1. using CRXDE|Lite, locate

    * /libs/social/config/datastore/msrp/*solrX*/**schema.xml**
    
    * /libs/social/config/datastore/msrp/*solrX*/**solrconfig.xml**

1. 
1. download to local server on which Solr is deployed

    * locate the `jcr:content` node's `jcr:data` property
    
    * select `view` to start the download
    * ensure the files are saved with the appropriate names and encoding (UTF8)

1. follow the installation instructions for either standalone or SolrCloud mode

#### SolrCloud Mode - Standard MLS {#solrcloud-mode-standard-mls}

1. Install and configure Solr in SolrCloud mode
1. Prepare a new configuration :

    1. create *new-config-dir* 
       such as *solr-install-dir*/myconfig/
    
    1. copy the contents of the existing Solr configuration directory to *new-config-dir*

        * for Solr4 : copy *solr-install-dir*/example/solr/collection1/conf/&#42;
        * for Solr5 : copy *solr-install-dir*/server/solr/configsets/data_driven_schema_configs/&#42;

    1. copy the downloaded **schema.xml** and **solrconfig.xml** to *new-config-dir* to overwrite existing files

1. [Upload the new configuration](#1uploadaconfigurationtozookeeper) to ZooKeeper
1. [Create a collection](#2createacollection) specifying the necessary parameters, such as number of shards, number of replicas, and configuration name.
1. If the configuration name was *not *provided during creation of the collection, [link this newly created collection](#3linkacollectiontoaconfigurationset) with the configuration uploaded to ZooKeeper

1. For MSRP, run [MSRP Reindex Tool](../../communities/using/msrp.md#msrpreindextool), unless this is a new installation

#### Standalone Mode - Standard MLS {#standalone-mode-standard-mls}

1. Install Solr in standalone mode
1. If running Solr5, create a collection1 (similar to Solr4) :

    * ./bin/solr start
    * ./bin/solr create_core -c collection1 -d sample_techproducts_configs

1. Backup **schema.xml** and **solrconfig.xml** in the Solr config dir, such as :

    * for Solr4 : *solr-install-dir*/example/solr/collection1/conf/
    * created for Solr5 : *solr-install-dir*/server/solr/collection1/conf/

1. Copy the downloaded **schema.xml** and **solrconfig.xml** to that same directory

1. Restart Solr
1. For MSRP, run [MSRP Reindex Tool](#msrpreindextool), unless this is a new installation

### Installing Advanced MLS {#installing-advanced-mls}

For the SRP collection (MSRP or DSRP) to support advanced MLS, new Solr plug-ins are required in addition to a custom schema and Solr configuration. All required items are packaged into a downloadable zip file. In addition, an install script is included for use when Solr is deployed in standalone mode.

To obtain the Advanced MLS package, see [AEM Advanced MLS](../../communities/using/deploy-communities.md#aemadvancedmls) in the deploy section of the documentation.

To get started with the install for either SolrCloud or standalone mode:

* download AEM-SOLR-MLS zip archive to server hosting Solr
* unpack the archive

#### SolrCloud Mode - Advanced MLS {#solrcloud-mode-advanced-mls}

Installation instructions - note the few differences for Solr4 and Solr5 :

1. Install and configure Solr in SolrCloud mode
1. Extract the contents of the Advanced MLS package to disk. The contents should include :

    * **schema.xml**
    * **solrconfig.xml**
    * **stopwords/ **folder
    * **profiles/ **folder
    * **extra-libs/** folder

1. Prepare a new configuration :

    1. create a *new-config-dir*

        * such as *solr-install-dir*/myconfig/
        * create subfolders stopwords/ and lang/

    1. copy the contents of the existing Solr config dir to *new-config-dir*

        * for Solr4 : copy *solr-install-dir*/example/solr/collection1/conf/&#42;
        * for Solr5 : copy *solr-install-dir*/server/solr/configsets/data_driven_schema_configs/&#42;

    1. copy the extracted **schema.xml** and **solrconfig.xml** to *new-config-dir* to overwrite existing files
    
    1. for Solr5 : copy *solr_install_dir*/server/solr/configsets/sample_techproducts_configs/conf/lang/&#42;.txt" to *new-config-dir*/lang/
    
    1. copy the extracted **stopwords/** folder to *new-config-dir*

        * resulting in *new-config-dir*/stopwords/&#42;.txt

1. [Upload the new configuration](#1uploadaconfigurationtozookeeper) to ZooKeeper
1. Copy the new **profiles/** folder ...

    * for Solr4 : copy to each node's resources/ folder
    * for Solr5 : copy to each Solr installation's server/resources/ folder. If all nodes are in the same Solr install directory, then this step is performed only once.

1. Create a** lib/** folder in the solr-home directory (contains solr.xml) of each node in SolrCloud. Copy jars from the following locations to the new lib/ folder on each node:

    * **extra-libs/** extracted from the advanced MLS package
    * *solr-install-dir*/contrib/extraction/lib/&#42;.jar
    * *solr-install-dir*/dist/solr-cell-&#42;.jar
    * *solr-install-dir*/contrib/clustering/lib/&#42;.jar
    * *solr-install-dir*/dist/solr-clustering-&#42;.jar
    * *solr-install-dir*/contrib/langid/lib/&#42;.jar
    * *solr-install-dir*/dist/solr-langid-&#42;.jar
    * *solr-install-dir*/contrib/velocity/lib/&#42;.jar
    * *solr-install-dir*/dist/solr-velocity-&#42;.jar
    * *solr-install-dir*/contrib/analysis-extras/lib/&#42;.jar
    * *solr-install-dir*/contrib/analysis-extras/lucene-libs/&#42;.jar

1. [Create a collection](#2createacollection) specifying the necessary parameters, such as number of shards, number of replicas, and configuration name.
1. If the configuration name was *not* provided during creation of the collection, [link this newly created collection](#3linkacollectiontoaconfigurationset) with the configuration uploaded to ZooKeeper

1. For MSRP, run [MSRP Reindex Tool](#msrpreindextool), unless this is a new installation

#### Standalone Mode - Advanced MLS {#standalone-mode-advanced-mls}

An install script is included in the Advanced MLS package.

After the contents of the package have been extracted to the server hosting the standalone Solr server, simply execute the install script in order to install the necessary resources and configuration files.

* Install Solr in standalone mode
* If running Solr5, create a collection1 (similar to Solr4) :

    * ./bin/solr start
    * ./bin/solr create_core -c collection1 -d sample_techproducts_configs

* Run the install script : Install [-v 4|5] [-d solrhome] [-c collectionpath]  
  where :

    * -d solrhome  
      Solr installation directory
    * -c collectionpath  
      collection path in solr
    * --help  
      print command line options
    * -v [4|5]  
      set version for solr

* Example for Solr 4.10.4:

    * Install.bat -v 4 -d c:/solr-4.10.4 -c c:/solr-4.10.4/example/solr/collection1

* Example for Solr 5.4.0:

    * Install.sh -v 5 -d /tmp/solr-5.4.0 -c /tmp/solr-5.4.0/server/solr/collection1

**Note**:

* the install script will back-up schema.xml and solrconfig.xml before installing new versions by appending ".orig"

### About solrconfig.xml {#about-solrconfig-xml}

The **solrconfig.xml** file controls the auto commit interval and search visibility and will requiring testing and tuning.

&lt;autoCommit&gt; : By default, the AutoCommit interval, which is a hard commit to stable storage, is set to 15 seconds. The search visibility defaults to using the pre-commit index.

To change search to use an index updated to reflect changes due to the commit, change the contained &lt;openSearcher&gt; to true.

&lt;autoSoftCommit&gt; : A 'soft' commit ensures that changes are visible (the index is updated), but does not ensure changes are synced to stable storage (hard commit). The result is an improvement in performance. By default, &lt;autoSoftCommit&gt; is disabled with the contained &lt;maxTime&gt; set to -1.
