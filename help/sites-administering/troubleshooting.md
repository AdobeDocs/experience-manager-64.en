---
title: Working with Logs
seo-title: Working with Logs
description: Learn how to troubleshoot AEM by working with logs.
seo-description: Learn how to troubleshoot AEM by working with logs.
uuid: b64e0b25-5228-4c2f-9cc1-dde524134026
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: b4c1cb82-865b-48dd-b5c0-946e6610ce8e
exl-id: 201e2b57-17c0-4454-9b0e-026e2c95ac63
---
# Working with Logs{#working-with-logs}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

This section includes detailed information on logs available to help you troubleshoot.

CRX records detailed logs. After you unpack and start Quickstart, you can find logs in the following locations:

* crx-quickstart/launchpad/logs 
* crx-quickstart/server/logs 
* crx-quickstart/logs

## Activating the DEBUG Log Level {#activating-the-debug-log-level}

The default log level is INFO, that is, DEBUG messages are not logged.

To activate DEBUG log level, use the CRX explorer to set the

```xml
/libs/sling/config/org.apache.sling.commons.log.LogManager/org.apache.sling.commons.log.level
```

property to debug. Do not leave the log at the DEBUG log level longer than necessary, as it generates a lot of logs.

A line in the debug file usually starts with DEBUG, and then provides the log level, the installer action and the log message. For example:

```xml
DEBUG 3 WebApp Panel: WebApp successfully deployed
```

The log levels are as follows: 

| 0 |Fatal error |The action has failed, and the installer cannot proceed. |
|---|---|---|
| 1 |Error |The action has failed. The installation proceeds, but a part of CRX was not installed correctly and will not work. |
| 2 |Warning |The action has succeeded but encountered problems. CRX may or may not work correctly. |
| 3 |Information |The action has succeeded. |

## Verbose Option Used for Troubleshooting {#verbose-option-used-for-troubleshooting}

When you start CRX, you can add the -v (verbose) option to the command line as in: ``

` java -jar crx-<*version*>-<*edition*>.jar -v`

Use the verbose option for troubleshooting as this option displays some of the quickstart log output on the console.
