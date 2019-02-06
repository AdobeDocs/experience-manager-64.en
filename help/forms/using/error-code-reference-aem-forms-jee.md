---
title: AEM Forms Error Code Reference (JEE Only)
seo-title: AEM Forms Error Code Reference (JEE Only)
description: null
seo-description: null
page-status-flag: de-activated
uuid: 903f9443-5995-4455-90f2-3cef3f050082
topic-tags: developer-reference
discoiquuid: bd634834-51f5-4660-bff5-5a1ec30cdb9e
index: y
internal: n
snippet: y
---

# AEM Forms Error Code Reference (JEE Only){#aem-forms-error-code-reference-jee-only}

## Application and Services Error Codes {#application-and-services-error-codes}

## Assembler Error Codes {#assembler-error-codes}

## Barcoded Forms Error Codes {#barcoded-forms-error-codes}

## Central Migration Bridge service error codes {#central-migration-bridge-service-error-codes}

## Configuration Manager error codes {#configuration-manager-error-codes}

## Connector for ECM error codes {#connector-for-ecm-error-codes}

## Connector for Microsoft SharePoint error codes {#connector-for-microsoft-sharepoint-error-codes}

## Content Services error codes {#content-services-error-codes}

## Convert PDF service error codes {#convert-pdf-service-error-codes}

## Core error codes {#core-error-codes}

## Core - DSC error codes {#core-dsc-error-codes}

## DB2 error codes {#db-error-codes}

## Data Services error codes {#data-services-error-codes}

## Database error codes {#database-error-codes}

## Doc Component error code {#doc-component-error-code}

## Document Security error codes {#document-security-error-codes}

## Encryption error codes {#encryption-error-codes}

## FDI error codes {#fdi-error-codes}

## File Provider error codes {#file-provider-error-codes}

## File Utilities error codes {#file-utilities-error-codes}

## Forms error codes {#forms-error-codes}

## Foundation error codes {#foundation-error-codes}

## Guides error codes {#guides-error-codes}

## JBoss error codes {#jboss-error-codes}

## Job Manager error codes {#job-manager-error-codes}

## Output error codes {#output-error-codes}

## PDF Generator error codes {#pdf-generator-error-codes}

## Process Management error codes {#process-management-error-codes}

## Reader Extensions error codes {#reader-extensions-error-codes}

## Repository error codes {#repository-error-codes}

## Rights Management error codes {#rights-management-error-codes}

## Solutions - Asset Composer error codes {#solutions-asset-composer-error-codes}

## Solutions - Data Dictionary error codes {#solutions-data-dictionary-error-codes}

## Solutions - Expression Manager error codes {#solutions-expression-manager-error-codes}

## Trust Store error codes {#trust-store-error-codes}

## User Manager error codes {#user-manager-error-codes}

## Utilities error codes {#utilities-error-codes}

## Web Services error codes {#web-services-error-codes}

## WebSphere error codes {#websphere-error-codes}

## Workspace error codes {#workspace-error-codes}

## XLIFF Tooling error codes {#xliff-tooling-error-codes}

## XML Form service error codes {#xml-form-service-error-codes}

## Miscellaneous Errors {#miscellaneous-errors}

These types of errors are typically caused by one of these issues:

* Running out of threads
* Threads and memory allocation

Many different types of threads are available; however, they fall into two categories: Java threads and native threads. All threads that are running within a Java™ virtual machine (JVM™) are Java threads ( java.lang.Thread class inside Java). The native code (C++/C) creates native threads that are scheduled and managed by the operating system. Here are the key differences between the two types:

* Operating system tools (such as perfmon or Task Manager) knows only about native threads.
* Java threads are created and managed by LiveCycle ES4 code, application server, or the JVM itself.

Because the operating system has no visibility into Java threads, when you monitor threads by using operating system tools such as perfmon , you are monitoring only native threads. The only way to get details into Java threads is to get a Java thread dump . The process about how to get a Java thread dump varies, depending on your application server and JVM. Refer to the manufacturer's documentation.

Incidentally, the implementation of the JVM is done in C/C++ code and that JVM code maps Java threads to native threads. This mapping can be either 1:1 (1 Java thread to 1 native thread) or N:1 (multiple Java threads to 1 native thread). The details of how this mapping works will be specific to the JVM vendor; however, 1:1 mapping is a typical default. This means that each Java thread will have a corresponding native thread. The number of Java threads has no definite limit; however, because 1:1 mapping is typical and the number of native threads has definite limits, you can run out of Java threads as well. This limit applies per process (JVM being a single process) and varies on each operating system. You can assume that the limit will be in the thousands (but less than 10,000). Regardless of this number, having several hundreds of threads is a performance problem because the operating system has to schedule up to that many threads.

Another common issue for threads pertains to memory allocations. When a new Java thread is allocated, a fixed amount of memory is required for the thread's stack. This thread stack space is a tunable parameter ( -Xss option for JVM) and the default is ~512 KB . Therefore, if you have 1000 threads, 500 MB of memory will be required just for the thread's stacks. This memory will compete with all the other memory allocations being done in the JVM (for example, what LiveCycle ES4 allocates) and will create memory allocation issues.

In practice, when the JVM cannot allocate memory or create threads, it throws an OutOfMemory exception back to the caller. Along with this exception will be a stack trace and a reason for throwing the exception. This reason is very important to take notice of; it will give you further clues to what the problem may be.

The following code is an example of a message that displays two errors and their associated reason codes:*"unable to create new native thread: java.lang.OutOfMemoryError: unable to create new native thread java.lang.OutOfMemoryError: Java heap space"*

These errors mean that the JVM could not create more threads for one of these reasons:

* The per-process thread limit is reached.
* The thread stack could not be allocated.

To determine the exact cause, you need to get a thread dump (also known as Java jump ). Thread dump will generally be called javacore.xxxx.txt and reside under an application server's log directories. Much information will be inside the thread dump, but you can quickly determine the number of threads by counting the occurrences of the TID: token on the list. A typical entry will look like this example:

"Thread-1227" (TID:0x106948F0, sys_thread_t:0x78996DA0, state:R, native ID:0x191C) prio=54XESTACKTRACE at java.net.SocketInputStream.socketRead0(Native Method)4XESTACKTRACE at java.net.SocketInputStream.read(SocketInputStream.java(Compiled Code))4XESTACKTRACE at java.io.BufferedInputStream.fill(BufferedInputStream.java(Compiled Code))4XESTACKTRACE at java.io.BufferedInputStream.read1(BufferedInputStream.java(Compiled Code))4XESTACKTRACE at java.io.BufferedInputStream.read(BufferedInputStream.java(Compiled Code))4XESTACKTRACE at com.sun.jndi.ldap.Connection.run(Connection.java(Compiled Code))4XESTACKTRACE at java.lang.Thread.run(Thread.java:567)

If you find thousands of threads, you are probably running out of threads. Developers should be able to identify obvious culprits by scanning the stack traces of these threads.

>[!NOTE]
>
>Thread dumps are typically intrusive and require that you restart the application server afterward.

If the thread count is in the hundreds, the reason for the java.lang.OutOfMemory error is not the thread limit. Reduce the thread stack size ( -Xss option mentioned above), rerun LiveCycle ES4, and check whether the problem disappears.

### 404 File not found {#file-not-found}

>[!NOTE]
>
>If you see this error, perform these checks:
>
>* Confirm the problem in the browser's access log.
>* Confirm that the EAR file deployed properly and that the application initialized.
>* If the URL is intended for the HTTP server, check that the file exists. Look in the error_log file or error.log file for the full file name that the web server is looking for.
>* (JBoss) Make sure the URL uses the correct case (it is case-sensitive).
>* (JBoss) Check whether the web application context root (first part of the URL) exist in the uriworkermap.properties file of the JK plug-in configuration.
>* (JBoss) If the file is a JSP, does the file exist in the EAR? This option will be confirmed by the absence of an entry in the HTTP server's error log file.
>

### Class not found {#class-not-found}

>[!NOTE]
>
>If you see this error, check whether any of these problems exist:
>
>* The class path setting is invalid or missing.
>* The JAR file is obsolete.
>* A compilation problem exists in the class.
>

### JNDI name not found {#jndi-name-not-found}

If the symptom is an exception stack trace showing javax.naming.NameNotFoundException: jdbc/ , check whether the expected name is spelled correctly; if it is not, fix the code.

1. Check the JNDI tree on the LiveCycle ES4 application server. Does the name used appear in the tree?

    * If yes, it is most likely that your code has not properly set up the InitialContext object being used for the look-up, and the look-up is being done on a JNDI tree that is not the one the resource is listed in. For the property values to use, see the Installing and Deploying LiveCycle ES4 document for your application server.
    * If no, continue to step 2.

1. Check whether the resource appears in the JNDI tree under a name other than the name that is listed in the look-up?

    * If yes, you are using the incorrect look-up name. Provide the correct name.
    * If no, continue to step 3.

1. Review the application server logs during startup. If the application server is configured to make this resource available but it is not working properly, an exception appears here. Did an exception appear?

    * If yes, review the exception and stack trace. If the NameNotFoundException is a symptom of another problem based on your investigation of the server logs, go to the troubleshooting steps for that problem.
    * If no, continue to step 4.

1. If the resource is not listed in the JNDI tree and no exception appears at startup to explain why it is not available, the most probable issue is that the application server is not configured properly to make that resource available. Review the application server configuration. Is it configured to make this resource available?

    * If no, refer to the Installing and Deploying LiveCycle ES4 document for your application server.
    * If yes, this problem is not one of the common ones that cause this issue. Contact Adobe Support.

## Log Files {#log-files}

### Using LiveCycle ES4 and Application Server Log Files {#using-livecycle-es-and-application-server-log-files}

Log files are useful for LiveCycle ES4 and application server failure analysis and may be required when dealing with Adobe Enterprise Support.

This section lists the common log files that you can use to diagnose LiveCycle ES4 problems. It also describes some of the most common errors that may be included in the LiveCycle ES4 log file.

#### LiveCycle ES4 Log files {#livecycle-es-log-files}

You can use log files to troubleshoot problems with LiveCycle ES4 installation or operation:

* LiveCycle ES4 log file: By default, the LiveCycle ES4 log file is located in the [LiveCycleES4 root] directory and named log.txt.
* LiveCycle Configuration Manager log file: By default, the LiveCycle Administration Console log file is in [LiveCycleES4 root] /ConfigurationManager/log and is named lcm.0.log or similar (the higher the number, the more recent the logs). The log files are useful for LiveCycle Configuration Manager failure analysis.

#### Application server log files {#application-server-log-files}

The application server log files are useful for application server and LiveCycle ES4 bootstrapping failure analysis. The default log files are in the following location for your application server:

JBoss: [LiveCycleES4 root] /jboss/server/all/log or [JBoss root] /server/all/log and named boot.log and server.log

WebLogic: /var/log/httpd/error_log

WebSphere: [WebSphere root] /logs/server1/trace.log

If the log file does not provide enough information to help you troubleshoot problems, you can specify the level of tracing in the log file to increase logging details. (See "Troubleshooting" in LiveCycle ES4 Administration Help .)

>[!MORE_LIKE_THIS]
>
>* [AEM Forms Error Code Reference](../../forms/using/error-code-reference.md)
