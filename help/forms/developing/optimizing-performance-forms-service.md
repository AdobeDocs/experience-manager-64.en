---
title: Optimizing the Performance of theForms Service
seo-title: Optimizing the Performance of theForms Service
description: null
seo-description: null
uuid: 38ad45dd-5f7a-4bcd-ab1e-cdac81307012
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/rendering_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: operations
discoiquuid: 5eefa40a-7f09-4c6b-b1fb-8b40cd809324
index: y
internal: n
snippet: y
---

# Optimizing the Performance of theForms Service{#optimizing-the-performance-of-theforms-service}

## Optimizing the Performance of the Forms Service {#optimizing-the-performance-of-the-forms-service}

When rendering a form, you can set run-time options that will optimize the performance of the Forms service. Another task that you can perform to improve the performance of the Forms service is to store XDP files in the repository. However, this section does not describe how to perform this task. (See [Invoking a service using a Java client library](#unresolvedlink-lc-in-invoke-using-java-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7b46.2).)

>[!NOTE]
>
>For more information about the Forms service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

### Summary of steps {#summary-of-steps}

To optimize the performance of the Forms service while rendering a form, perform the following tasks:

1. Include project files.
1. Create a Forms Client API object. 
1. Set performance run-time options.
1. Render the form.
1. Write the form data stream to the client web browser.

**Include project files**

Include necessary files into your development project. If you are creating a client application using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

**Create a Forms Client API object**

Before you can programmatically perform a Forms service Client API operation, you must create a Forms service client. If you are using the Java API, create a `FormsServiceClient` object. If you are using the Forms web service API, create a `FormsService` object.

**Set performance run-time options**

You can set the following performance run-time options to improve the performance of the Forms service:

* **Form caching**: You can cache a form that is rendered as PDF in the server cache. Each form is cached after it is generated for the first time. On a subsequent render, if the cached form is newer than the form design’s timestamp, the form is retrieved from the cache. By caching forms, you improve the performance of the Forms service because it does not have to retrieve the form design from a repository.
* Form Guides (deprecated) may take longer to render than other transformation types. It is recommended that you cache form Guides (deprecated) in order to improve performance.
* **Standalone option**: If you do not require the Forms service to perform server-side calculations, you can set the Standalone option to `true`, which results in forms being rendered without state information. State information is necessary if you want to render an interactive form to an end user who then enters information into the form and submits the form back to the Forms service. The Forms service then performs a calculation operation and renders the form back to the user with the results displayed in the form. If a form without state information is submitted back to the Forms service, only the XML data is available and server-side calculations are not performed.
* **Linearized PDF**: A linearized PDF file is organized to enable efficient incremental access in a network environment. The PDF file is valid PDF in all respects, and is compatible with all existing viewers and other PDF applications. That is, a linearized PDF can be viewed while it is still being downloaded.
* This option does not improve performance when a PDF form is rendered on the client. 
* **GuideRSL option**: Enables form Guide (deprecated) generation using run-time shared libraries. This means the first request will download a smaller SWF file, plus larger shared-libraries that are stored in the browser cache. For more information, see RSL in the Flex documentation. 
* You can also improve the performance of the Forms service by rendering a form on the client. (See [Rendering Forms at the Client](/programming-with-aem-forms/rendering-forms-rendering-forms rendering-forms-client-rendering-forms#rendering_forms_at_the_client).)

**Render the form**

To render the form after setting performance options, you use the same application logic as rendering a form without performance options.

**Write the form data stream to the client web browser**

After the Forms service renders a form, it returns a form data stream that you must write to the client web browser. When written to the client web browser, the form is visible to the user.

**See also**

[Optimize the performance using the Java API](/programming-with-aem-forms/rendering-forms-rendering-forms optimizing-performance-forms-service-optimizing optimizing-performance-forms-service-optimizing#optimize_the_performance_using_the_java_api)

[Optimize the performance using the web service API](/programming-with-aem-forms/rendering-forms-rendering-forms optimizing-performance-forms-service-optimizing optimizing-performance-forms-service-optimizing#optimize_the_performance_using_the_web_service_api)

[Including AEM Forms Java library files](#unresolvedlink-lc-in-invoke-using-java-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7b4b.2)

[Setting connection properties](#unresolvedlink-lc-in-invoke-using-java-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7fd6.2)

[Forms Service API Quick Starts](#unresolvedlink-lc-qs-forms-fo.xml#ws624e3cba99b79e12e69a9941333732bac8-7af6.2)

[Rendering Interactive PDF Forms](/programming-with-aem-forms/rendering-forms-rendering-forms rendering-interactive-pdf-forms-rendering#rendering_interactive_pdf_forms)

[Rendering Forms as HTML](/programming-with-aem-forms/rendering-forms-rendering-forms rendering-forms-html-rendering-forms rendering-forms-html-rendering-forms#rendering_forms_as_html)

[Creating Web Applications that Renders Forms](/programming-with-aem-forms/rendering-forms-rendering-forms creating-web-applications-renders-forms#creating_web_applications_that_renders_forms)

### Optimize the performance using the Java API {#optimize-the-performance-using-the-java-api}

Render a form with optimized performance by using the Forms API (Java):

1. Include project files

   Include client JAR files, such as adobe-forms-client.jar, in your Java project’s class path.

1. Create a Forms Client API object

    * Create a `ServiceClientFactory` object that contains connection properties. 
    * Create an `FormsServiceClient` object by using its constructor and passing the `ServiceClientFactory` object.

1. Set performance run-time options

    * Create a `PDFFormRenderSpec` object by using its constructor. 
    * Set the form cache option by invoking the `PDFFormRenderSpec` object’s `setCacheEnabled` method and passing `true`. 
    * Set the linearized option by invoking the `PDFFormRenderSpec` object’s `setLinearizedPDF` method and passing `true.`

1. Render the form

   Invoke the `FormsServiceClient` object’s `renderPDFForm` method and pass the following values:

    * A string value that specifies the form design name, including the file name extension.
    * A `com.adobe.idp.Document` object that contains data to merge with the form. If you do not want to merge data, pass an empty `com.adobe.idp.Document` object. 
    * A `PDFFormRenderSpec` object that stores run-time options to improve performance. 
    * A `URLSpec` object that contains URI values that are required by the Forms service. 
    * A `java.util.HashMap` object that stores file attachments. This is an optional parameter and you can specify `null` if you do not want to attach files to the form.

   The `renderPDFForm` method returns a `FormsResult` object that contains a form data stream that must be written to the client web browser.

1. Write the form data stream to the client web browser

    * Create a `javax.servlet.ServletOutputStream` object used to send a form data stream to the client web browser. 
    * Create a `com.adobe.idp.Document` object by invoking the `FormsResult` object ‘s `getOutputContent` method. 
    * Create a `java.io.InputStream` object by invoking the `com.adobe.idp.Document` object’s `getInputStream` method. 
    * Create a byte array and populate it with the form data stream by invoking the `InputStream` object’s `read`method and passing the byte array as an argument. 
    * Invoke the `javax.servlet.ServletOutputStream` object’s `write` method to send the form data stream to the client web browser. Pass the byte array to the `write` method.

**See also**

[Optimizing the Performance of the Forms Service](/programming-with-aem-forms/rendering-forms-rendering-forms optimizing-performance-forms-service-optimizing#optimizing_the_performance_of_the_forms_service)

[Quick Start (SOAP mode): Optimizing performance using the Java API](#unresolvedlink-lc-qs-forms-fo.xml#ws624e3cba99b79e12e69a9941333732bac8-7e1e.2)

[Including AEM Forms Java library files](#unresolvedlink-lc-in-invoke-using-java-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7b4b.2)

[Setting connection properties](#unresolvedlink-lc-in-invoke-using-java-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7fd6.2)

### Optimize the performance using the web service API {#optimize-the-performance-using-the-web-service-api}

Render a form with optimized performance by using the Forms API (web service):

1. Include project files

    * Create Java proxy classes that consume the Forms service WSDL. 
    * Include the Java proxy classes into your class path.

1. Create a Forms Client API object

   Create a `FormsService` object and set authentication values. 

1. Set performance run-time options

    * Create a `PDFFormRenderSpec` object by using its constructor. 
    * Set the form cache option by invoking the `PDFFormRenderSpec` object’s `setCacheEnabled` method and passing true. 
    * Set the standalone option by invoking the `PDFFormRenderSpec` object’s `setStandAlone` method and passing true.
    * Set the linearized option by invoking the `PDFFormRenderSpec` object’s `setLinearizedPDF` method and passing true.

1. Render the form

   Invoke the `FormsService` object’s `renderPDFForm` method and pass the following values:

    * A string value that specifies the form design name, including the file name extension.
    * A `BLOB` object that contains data to merge with the form. If you do not want to merge data, pass `null`. 
    * A `PDFFormRenderSpecc` object that stores run-time options.
    * A `URLSpec` object that contains URI values that are required by the Forms service. 
    * A `java.util.HashMap` object that stores file attachments. This is an optional parameter and you can specify `null` if you do not want to attach files to the form.
    * An empty `com.adobe.idp.services.holders.BLOBHolder` object that is populated by the method. This is used to store the rendered PDF form. 
    * An empty `javax.xml.rpc.holders.LongHolder` object that is populated by the method. (This argument will store the number of pages in the form).
    * An empty `javax.xml.rpc.holders.StringHolder` object that is populated by the method. (This argument will store the locale value).
    * An empty `com.adobe.idp.services.holders.FormsResultHolder` object that will contain the results of this operation.

   The `renderPDFForm` method populates the `com.adobe.idp.services.holders.FormsResultHolder` object that is passed as the last argument value with a form data stream that must be written to the client web browser.

1. Write the form data stream to the client web browser

    * Create a `FormResult` object by getting the value of the `com.adobe.idp.services.holders.FormsResultHolder` object’s `value` data member. 
    * Create a `javax.servlet.ServletOutputStream` object used to send a form data stream to the client web browser. 
    * Create a `BLOB` object that contains form data by invoking the `FormsResult` object’s `getOutputContent` method. 
    * Create a byte array and populate it by invoking the `BLOB` object’s `getBinaryData` method. This task assigns the content of the `FormsResult` object to the byte array. 
    * Invoke the `javax.servlet.http.HttpServletResponse` object’s `write` method to send the form data stream to the client web browser. Pass the byte array to the `write` method.

**See also**

[Optimizing the Performance of the Forms Service](/programming-with-aem-forms/rendering-forms-rendering-forms optimizing-performance-forms-service-optimizing#optimizing_the_performance_of_the_forms_service)

[Quick Start (Base64): Optimizing performance using the web service API](#unresolvedlink-lc-qs-forms-fo.xml#ws624e3cba99b79e12e69a9941333732bac8-7e1d.2)

[Invoking AEM Forms using Base64 encoding](#unresolvedlink-lc-in-invoke-using-web-services-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7fca.2)

