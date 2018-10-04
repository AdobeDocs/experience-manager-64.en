---
title: Command Line Start and Stop
seo-title: Command Line Start and Stop
description: null
seo-description: Learn how to start and stop AEM from the command line.
uuid: e3b3d4ee-e5a0-458a-a94f-8336e5d8669c
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/command-line-start-and-stop
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 42.309-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 39 46.972-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: deploying
cq-template: /apps/help/templates/article-3
discoiquuid: 55c74ade-b48d-4b5a-820c-83fa22f6ebf4
firstPublishExternalDate: 2017-10-31T16:18:14.076-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 05 32.999-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:39:45.484-0400
lochandoffdate: 2018-04-30T03 26 42.309-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/deploying
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Command Line Start and Stop
publishexternaldate: 2018-04-03T08 39 45.484-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/command-line-start-and-stop.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/command-line-start-and-stop
sha1: b1d83652ac01a2db131f1f46d9d57c5fa0f66241
topicBrowsingSortDate: 2018-04-03T08:39:45.484-0400
index: y
internal: n
snippet: y
translate: y
---

# Command Line Start and Stop

## Starting Adobe Experience Manager from the Command Line

The `start` script is available under *the &lt;cq-installation&gt;/bin* directory. Both Unix and Windows versions are provided. The script starts the instance installed in *&lt;cq-installation&gt;* directory.

Those two versions support a list of environement variables that could be used to start and tune the AEM instance.

| **Environment variable ** |**Description ** |
|---|---|
| CQ_PORT |TCP port used for stop and status scripts  
|
| CQ_HOST |Host name  
|
| CQ_INTERFACE |Interface that this server should listen to  
|
| CQ_RUNMODE |Runmode(s) separated by comma  
|
| CQ_JARFILE |Name of the jarfile  
|
| CQ_USE_JAAS |Use of JAAS (if true)  
|
| CQ_JAAS_CONFIG |Path of the JAAS configuration  
|
| CQ_JVM_OPTS |Default JVM options  
|

>[!CAUTION]
>
><p>Note that some run modes, among them author and publish, need to be set before first starting AEM and can not be changed afterwards. Before setting up an AEM instance that is supposed to be used in production, please see the <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/configure-runmodes.html">run modes documentation</a> for details.</p>

#### Windows platform start.bat script example

```shell
SET CQ_PORT=1234 & ./start.bat
```

#### Unix platform start script example

```shell
CQ_PORT=1234 ./start
```

>[!NOTE]
>
><p>The start script launches the AEM Quickstart installed under <i>the &lt;cq-installation&gt;/app</i> folder.<br> </p>

## Stopping Adobe Experience Manager

To stop AEM, do one of the following:

* Depending on the platform you are using:

    * If you started AEM from either a script or the command line, press **Ctrl+C **to shut down the server.    
    * If you have used the start script on UNIX, you must use the stop script to stop AEM.

* If you started AEM by double-clicking the jar file, click the **On** button on the startup window (the button then changes to **Off**) to shut down the server.

  ![](assets/chlimage_1.png)

## Stopping Adobe Experience Manager from the Command Line

The `stop` script is available under *the &lt;cq-installation&gt;/bin* directory. Both Unix and Windows versions are provided. The script stops the running instance installed in *&lt;cq-installation&gt;* directory.

#### Unix platform stop script example

```shell
./stop
```

#### Windows platform stop.bat script example

```shell
./stop.bat
```

If you just want to preconfigure the repository (without relocating it) you only have to:

* extract `repository.xml` to the required location

* update `repository.xml` as required  

* create `bootstrap.properties` and define `repository.config`

Again, before starting the actual installation.  

