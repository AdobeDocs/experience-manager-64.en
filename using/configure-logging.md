---
uuid: 35af367c-3024-49e4-a956-ffc5046db310
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
><p>Logging in AEM is based on Sling principles. See <a href="http://sling.apache.org/site/logging.html">Sling Logging</a> for further information.<br> </p>

---

## Global Logging

[Apache Sling Logging Configuration](osgi-configuration-settings.md#ApacheSlingLoggingConfiguration) is used to configure the root logger. This defines the global settings for logging in AEM:

* the logging level
* the location of the central log file
* the number of versions to be kept
* version rotation; either maximum size or a time interval
* the format to be used when writing the log messages

>[!NOTE]
>
><p>This <a href="/content/help/en/experience-manager/kb/HowToRotateRequestAndAccessLog.html">Knowledge Base article</a> explains how to rotate the request.log and access.log files.<br /> </p>

---

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

* **Logger (Logging Logger)** Define the service(s) generating the messages.
* **Log File (Logging Logger)** `` ``  Define the physical file for storing the log messages. This is used to link a Logging Logger with a Logging Writer. The value must be identical to the same parameter in the Logging Writer configuration for the connection to be made.
* **Log File (Logging Writer)** `` ``  Define the physical file that the log messages will be written to. This must be identical to the same parameter in the Logging Writer configuration, or the match will not be made. If there is no match then an implicit Writer will be created with default configuration (daily log rotation).

#### Standard Loggers and Writers

Certain Loggers and Writers are included in a standard AEM installation.

The first is a special case as it controls both the `request.log` and `access.log` files:

* The Logger:

    * Apache Sling Customizable Request Data Logger (org.apache.sling.engine.impl.log.RequestLoggerService)    
    * Write messages about request content to `request.log`.

* Links to:

    * Apache Sling Request Logger (org.apache.sling.engine.impl.log.RequestLogger)    
    * Writes the messages to either `request.log` or `access.log`.

These can be customized if required, though the standard configuration is suitable for most installations.

The other pairs follow the standard configuration:

* The Logger:

    * Apache Sling Logging Logger Configuration (org.apache.sling.commons.log.LogManager.factory.config)    
    * Writes `Information` messages to `logs/error.log`.

* Links to the Writer:

    * Apache Sling Logging Writer Configuration (org.apache.sling.commons.log.LogManager.factory.writer)

* The Logger:

    * Apache Sling Logging Logger Configuration (org.apache.sling.commons.log.LogManager.factory.config.649d51b7-6425-45c9-81e6-2697a03d6be7)    
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
><p>In certain circumstances you may want to create a <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/monitoring-and-maintaining.html#CreateaCustomLogFile">custom log file</a>.</p> 
