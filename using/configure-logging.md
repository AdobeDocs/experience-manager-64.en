---
title: Logging
seo-title: Logging
description: null
seo-description: Learn how to configure global parameters for the central logging service, specific settings for the individual services or how to request data logging.
uuid: e204bc8f-351a-499b-a185-a3d5833dcf08
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/configure-logging
contentOwner: User
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 27 25.469-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 39 53.337-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 254572dc-4f47-4c48-9c2a-b65a7d159bde
firstPublishExternalDate: 2017-10-31T16:18:13.608-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 02 26.377-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:39:51.610-0400
lochandoffdate: 2018-04-30T03 27 25.468-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Logging
publishexternaldate: 2018-04-03T08 39 51.610-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/configure-logging.html
qaDate: 2017-10-12T21:46:58.665-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/configure-logging
sha1: 76b7ac20b3bbbc9da9dc465fb6874ea8e2e31c3c
topicBrowsingSortDate: 2018-04-03T08:39:51.610-0400
index: y
internal: n
snippet: y
translate: y
---

# Logging

AEM offers you the possibility to configure:

* global parameters for the central logging service
* request data logging; a specialized logging configuration for request information
* specific settings for the individual services; for example, an individual log file and format for the log messages

These are all [OSGi configurations](configuring-osgi.md).

>[!NOTE]
>
>Logging in AEM is based on Sling principles. See [Sling Logging](http://sling.apache.org/site/logging.html) for further information.

## Global Logging
[Apache Sling Logging Configuration](osgi-configuration-settings.md#ApacheSlingLoggingConfiguration) is used to configure the root logger. This defines the global settings for logging in AEM:

* the logging level
* the location of the central log file
* the number of versions to be kept
* version rotation; either maximum size or a time interval  
* the format to be used when writing the log messages

>[!NOTE]
>
>This [Knowledge Base article](/content/help/en/experience-manager/kb/HowToRotateRequestAndAccessLog) explains how to rotate the request.log and access.log files.

## Loggers and Writers for Individual Services
In addition to the global logging settings, AEM allows you to configure specific settings for an individual service:

* the specific logging level
* the location of the individual log file
* the number of versions to be kept
* version rotation; either maximum size or the time interval   
* the format to be used when writing the log messages
* the logger (the OSGi service supplying the log messages)

This allows you to channel log messages for a single service into a separate file. This can be particularly useful during development or testing; for example, when you need an increased log level for a specific service.

AEM uses the following to write log messages to file:

1. An **OSGi service** (logger) writes a log message.
1. A **Logging Logger** takes this message and formats it according to your specification.
1. A **Logging Writer** writes all these messages to the physical file that you have defined.

These elements are linked by the following parameters for the appropriate elements:

* **Logger (Logging Logger)** 
  Define the service(s) generating the messages.

* **Log File (Logging Logger)** `` ``   
  Define the physical file for storing the log messages.  
  This is used to link a Logging Logger with a Logging Writer. The value must be identical to the same parameter in the Logging Writer configuration for the connection to be made.  

* **Log File (Logging Writer)** `` ``   
  Define the physical file that the log messages will be written to.  
  This must be identical to the same parameter in the Logging Writer configuration, or the match will not be made. If there is no match then an implicit Writer will be created with default configuration (daily log rotation).

#### Standard Loggers and Writers
Certain Loggers and Writers are included in a standard AEM installation.

The first is a special case as it controls both the `request.log` and `access.log` files:

* The Logger:

    * Apache Sling Customizable Request Data Logger  
      (org.apache.sling.engine.impl.log.RequestLoggerService)
    * Write messages about request content to `request.log`.

* Links to:

    * Apache Sling Request Logger  
      (org.apache.sling.engine.impl.log.RequestLogger)
    * Writes the messages to either `request.log` or `access.log`.

These can be customized if required, though the standard configuration is suitable for most installations.

The other pairs follow the standard configuration:

* The Logger:

    * Apache Sling Logging Logger Configuration  
      (org.apache.sling.commons.log.LogManager.factory.config)
    * Writes `Information` messages to `logs/error.log`.

* Links to the Writer:

    * Apache Sling Logging Writer Configuration  
      (org.apache.sling.commons.log.LogManager.factory.writer)

* The Logger:

    * Apache Sling Logging Logger Configuration  
      (org.apache.sling.commons.log.LogManager.factory.config.649d51b7-6425-45c9-81e6-2697a03d6be7)
    * Writes `Warning` messages to `../logs/error.log` for the service `org.apache.pdfbox`.

* Does not link to a specific Writer so will create and use an implicit Writer with default configuration (daily log rotation).

#### Creating Your Own Loggers and Writers
You can define your own Logger / Writer pair:

1. Create a new instance of the Factory Configuration [Apache Sling Logging Logger Configuration](osgi-configuration-settings.md#ApacheSlingLoggingLoggerConfigurationFactoryConfiguration).

    1. Specify the Log File.
    1. Specify the Logger.
    1. Configure the other parameters as required.

1. Create a new instance of the Factory Configuration [Apache Sling Logging Writer Configuration](osgi-configuration-settings.md#ApacheSlingLoggingWriterConfigurationFactoryConfiguration).

    1. Specify the Log File - this must match that specified for the Logger.
    1. Configure the other parameters as required.

>[!NOTE]
>
>In certain circumstances you may want to create a [custom log file](monitoring-and-maintaining.md#CreateaCustomLogFile).

