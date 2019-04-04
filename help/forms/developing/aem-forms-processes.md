---
title: Understanding AEM Forms Processes
seo-title: Understanding AEM Forms Processes
description: null
seo-description: null
uuid: 7cbebe7d-f222-42fa-8eb6-d2443458a791
contentOwner: admin
content-type: reference
topic-tags: coding
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: development-tools
discoiquuid: ac9fe461-63e7-442b-bd1c-eb9576ef55aa
---

# Understanding AEM Forms Processes{#understanding-aem-forms-processes}

A common use case is for a set of AEM Forms services to operate on a single document. You can send a request to the service container by creating a process using Workbench. A process represents a business process that you are automating. For information about creating processes, see [Using Workbench](https://www.adobe.com/go/learn_aemforms_workbench_63).

Once a process is activated, it becomes a service and can be invoked like other services. One difference between a standard service, such as the Encryption service and a service that originated from a process, is that the latter has one operation that performs many actions. In contrast, an standard service has many operations. Each operation typically performs one action, such as applying a policy to a document or encrypting a document.

Processes can be short-lived or long-lived. A short-lived process is an operation that is performed synchronously and on the same execution thread from which it was invoked. Short-lived operations are comparable to the standard behavior found in most programming languages, where a client application calls a method and waits for a return value.

However, there are situations where a process cannot be completed synchronously due to factors such as these:

* A process can span a significant amount of time.
* A process can span organizational boundaries.
* A process needs external input in order for it to finish. For example, consider a situation where a form is sent to a manager who is out of the office. In this situation, the process is not complete until the manager returns and fills out the form.

  These types of processes are known as long-lived processes. A long-lived process is performed asynchronously, allowing for systems to interact as resources permit and allowing for the tracking and monitoring of the operation. When a long-lived process is invoked, AEM Forms creates an invocation identifier value as part of a record that tracks the long-lived process status. The record is stored in the AEM Forms database. You can purge long-lived process records when they are no longer required. (See [Purging Process Data](/help/forms/developing/processes-tasks.md#purging_process_data).)

  ***Note**: AEM Forms does not create a record when a short-lived process is invoked. *

  Using the invocation identifier value, you can track the status of the long-lived process. For example, you can use the process invocation identifier value to perform Process Manager operations such as terminating a running process instance. (See [Terminating Process Instances](/programming-with-aem-forms/processes-tasks.md#terminating_process_instances).)

**Short lived process example**

The following illustration is an example of a short-lived process named *MyApplication/EncryptDocument*.

>[!NOTE]
>
>This process is not based on an existing AEM Forms process. To follow along with the code examples that discuss how to invoke this process, create a process named `MyApplication/EncryptDocument` using Workbench. (See [Using Workbench](https://www.adobe.com/go/learn_aemforms_workbench_63).)

When this short-lived process is invoked, it performs the following actions:

1. Obtains the unsecured PDF document that is passed to the process as an input value. 
1. Encrypts the PDF document with a password. The name of the input parameter for this process is `inDoc` and the data type is document. 
1. Saves the password-encrypted PDF document as a PDF file to the local file system. This process returns the encrypted PDF document as an output value. The name of the output parameter for this process is `outDoc` and the data type is document.

   This process is completed synchronously on the same execution thread from which it was invoked. The name of this short-lived process is `MyApplication/EncryptDocument`and its operation is `invoke`.

   >[!NOTE]
   >
   >Typically a short-lived process consists of more than three actions. You create a process using Workbench. (See [Using Workbench](https://www.adobe.com/go/learn_aemforms_workbench_63).)

   *Programming with AEM forms*describes the following ways in which you can programmatically invoke this short-lived process:

    * [Invoking a short-lived process by passing an unsecure document using AEM Forms Remoting](/programming-with-aem-forms/invoking-aem-forms-using-remoting.md#invoking_a_short_lived_process_by_passing_an_unsecure_document_using_remoting) (Using a Flex application)
    * [Invoking a short-lived process using the Invocation API](/programming-with-aem-forms/invoking-aem-forms-using-java.md#invoking_a_short_lived_process_using_the_invocation_api) (Java Invocation API)
    * [Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web.md#invoking_aem_forms_using_base64_encoding) (web service example)
    * [Invoking AEM Forms using MTOM](/programming-with-aem-forms/invoking-aem-forms-using-web.md#invoking_aem_forms_using_mtom) (web service example)
    * [Invoking AEM Forms using SwaRef](/programming-with-aem-forms/invoking-aem-forms-using-web.md#invoking_aem_forms_using_swaref) (web service example)
    * [Invoking AEM Forms using BLOB data over HTTP](/programming-with-aem-forms/invoking-aem-forms-using-web.md#invoking_aem_forms_using_blob_data_over_http) (web service example)
    * [Invoking AEM Forms using DIME](/programming-with-aem-forms/invoking-aem-forms-using-web.md#invoking_aem_forms_using_dime) (web service example)
    * [Invoking the MyApplication/EncryptDocument process using REST](unresolvedlink-lc-in-invoke-using-rest-requests-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7b5e.2)

**Long-lived process example**

The following illustration is an example of a long-lived process.

This process is invoked when an applicant submits a loan form. The process is not complete until a loan officer approves or rejects the loan request. The name of this long-lived process is* FirstAppSolution/PreLoanProcess *and its operation is `invoke_Async`. This process must be invoked asynchronously. For information about programmatically invoking this long-lived process, see [Invoking Human-Centric Long-Lived Processes](/programming-with-aem-forms/invoking-human-centric-long-lived.md#invoking_human_centric_long_lived_processes).

>[!NOTE]
>
>This process can be created by following the tutorial specified in [Creating Your First AEM Forms Application](https://www.adobe.com/go/learn_aemforms_firstapp_ds_63).

