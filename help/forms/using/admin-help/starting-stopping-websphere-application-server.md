---
title: Starting and stopping WebSphere Application Server
seo-title: Starting and stopping WebSphere Application Server
description: null
seo-description: Several procedures require you to stop or start the instance of WebSphere where you want to deploy AEM forms products. This document describes how to start and stop the WebSphere Application Server.
uuid: 6c598153-3e45-4e77-be52-cc6d0508854c
acrolinxdate: 2016-05-31T07 03 19.724-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/starting_stopping_websphere_application_server_admin_5e12de0b318c6865_2377_report.xml
acrolinxsentences: 6
acrolinxwords: 168
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_application_server
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 3312a965-518c-4748-9808-f4d76656bf44
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Starting and stopping WebSphere Application Server{#starting-and-stopping-websphere-application-server}

Several procedures require you to stop or start the instance of WebSphere where you want to deploy AEM forms products. If you are unsure whether the application server has started, you can first view the status of WebSphere Application Server.

## View the status of WebSphere Application Server {#view-the-status-of-websphere-application-server}

1. From a command prompt, go to the *[appserver root]*/bin directory.
1. Enter the following command, replacing *server_name* with the name of your WebSphere Application Server:

    * (Windows) `serverStatus.bat`*server_name*
    * (Linux, UNIX) ./ `serverStatus.sh`*server_name*

## Start WebSphere Application Server {#start-websphere-application-server}

1. From a command prompt, go to the *[appserver root]*/bin directory.
1. Enter the following command, replacing *server_name* with the name of your WebSphere Application Server:

    * (Windows) `startServer.bat`*server_name*
    * (Linux, UNIX) ./ `startServer.sh`*server_name*

## Stop WebSphere Application Server {#stop-websphere-application-server}

1. From a command prompt, go to the *[appserver root]*/bin directory.
1. Enter the following command, replacing *server_name* with the name of your WebSphere Application Server:

    * (Windows) `stopServer.bat`*server_name*
    * (Linux, UNIX) ./ `stopServer.sh`*server_name*

