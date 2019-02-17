---
title: Working with PDF Utilities
seo-title: Working with PDF Utilities
description: null
seo-description: null
uuid: cce3e89b-19e8-42cc-97bb-769c76ebedcc
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: operations
discoiquuid: 7aaa1548-9b1f-48b6-b3ba-ab00e0078927
index: y
internal: n
snippet: y
---

# Working with PDF Utilities{#working-with-pdf-utilities}

**About the PDF Utilities Service**

The PDF Utilities service can convert between PDF and XDP file formats, set and retrieve PDF document properties, and manipulate XMP metadata. For example, before converting a PDF document to another format, it is useful to inspect its properties to determine which service operation to invoke for the conversion.

You can accomplish these tasks using the PDF Utilities service:

* Convert PDF documents to XDP documents. (See [Converting PDF Documents into XDP Documents](lc_ut_convert_pdf_into_xdp_cp.md#WS624e3cba99b79e12e69a9941333732bac8-7d40).)
* Convert XDP documents to PDF documents. (See [Converting XDP Documents into PDF Documents](pdf-utilities#converting_xdp_documents_into_pdf_documents).)
* Retrieve PDF document properties. (See [Retrieving PDF Document Properties](pdf-utilities#retrieving_pdf_document_properties).)
* Save a PDF document and optimize it for fast web viewing. (See [Setting PDF Document Save Modes](pdf-utilities#setting_pdf_document_save_modes).)

>[!NOTE]
>
>For more information about the PDF Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

## Converting PDF Documents into XDP Documents {#converting-pdf-documents-into-xdp-documents}

You can use the PDF Utilities Java and web service APIs to programmatically convert PDF documents into XDP documents.

>[!NOTE]
>
>For more information about the PDF Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

### Summary of steps {#summary-of-steps}

To convert a PDF document into an XDP document, perform the following steps:

1. Include project files.
1. Create a PDFUtilityService client.
1. Invoke the PDF to XDP conversion operation.

**Include project files**

Include necessary files into your development project. If you are creating a client application using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

**Create a PDFUtilityService client**

Before you can programmatically perform a PDF Utilities operation, you must create a PDFUtilityService client. With the Java API, this is accomplished by creating a `PDFUtilityServiceClient` object. With the web service API, this is accomplished by using a `PDFUtilityServiceService` object.

**Invoke the PDF to XDP conversion operation**

After you create the service client, you can invoke the PDF to XDP conversion operation.

**See also**

[Convert PDF documents into XDP documents using the Java API](pdf-utilities#convert_pdf_documents_into_xdp_documents_using_the_java_api)

[Convert PDF documents into XDP documents using the web service API](pdf-utilities#convert_pdf_documents_into_xdp_documents_using_the_web_service_api)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Convert PDF documents into XDP documents using the Java API {#convert-pdf-documents-into-xdp-documents-using-the-java-api}

Convert PDF documents into XDP documents by using the PDF Utilities API(Java):

1. Include project files

   Include client JAR files, such as the adobe-pdfutility-client.jar, in your Java project’s class path..

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceClient` object by using its constructor and passing a `ServiceClientFactory` object that contains connection properties. 

1. Invoke the PDF to XDP conversion operation

   To perform the conversion, invoke the `PDFUtilityServiceClient` object’s `convertPDFtoXDP` method and pass in a `com.adobe.idp.Document` object that represents the PDF file. The method returns a `com.adobe.idp.Document` object that represents the newly created XDP file.

**See also**

[Converting PDF Documents into XDP Documents](pdf-utilities#converting_pdf_documents_into_xdp_documents)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Convert PDF documents into XDP documents using the web service API {#convert-pdf-documents-into-xdp-documents-using-the-web-service-api}

Convert PDF documents into XDP documents by using the PDF Utilities API (web service):

1. Include project files

    * Create a Microsoft .NET client assembly that consumes the PDF Utilities service WSDL file. 
    * Reference the Microsoft .NET client assembly.

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceService` object by using your proxy class constructor. 

1. Invoke the PDF to XDP conversion operation

   Invoke the `PDFUtilityServiceService` object’s `convertPDFtoXDP` method and pass in a `BLOB` object that represents the PDF file. The method returns a `BLOB` object that represents the newly created XDP file.

**See also**

[Converting PDF Documents into XDP Documents](pdf-utilities#converting_pdf_documents_into_xdp_documents)

[Quick Start (Base64): Converting a PDF document to an XDP document using the web service API](#unresolvedlink-lc-qs-pdf-utilities-pu.xml#ws624e3cba99b79e12e69a9941333732bac8-7d2c.2)

[Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_base64_encoding)

[Creating a .NET client assembly that uses Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#creating_a_net_client_assembly_that_uses_base64_encoding)

## Converting XDP Documents into PDF Documents {#converting-xdp-documents-into-pdf-documents}

You can use the PDF Utilities Java and web service APIs to programmatically convert XDP documents into PDF documents.

>[!NOTE]
>
>For more information about the PDF Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

### Summary of steps {#summary_of_steps-1}

To convert an XDP document into a PDF document, perform the following steps:

1. Include project files.
1. Create a PDFUtilityService client.
1. Invoke the XDP to PDF conversion operation.

**Include project files**

Include necessary files into your development project. If you are creating a client application using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

**Create a PDFUtilityService client**

Before you can programmatically perform a PDF Utilities operation, you must create a PDFUtilityService client. With the Java API, this is accomplished by creating a `PDFUtilityServiceClient` object. With the web service API, this is accomplished by using a `PDFUtilityServiceService` object.

**Invoke the XDP to PDF conversion operation**

After you create the service client, you can invoke the XDP to PDF conversion operation.

**See also**

[Convert XDP documents into PDF documents using the Java API](pdf-utilities#convert_xdp_documents_into_pdf_documents_using_the_java_api)

[Converting XDP documents into PDF documents using the web service API](pdf-utilities#converting_xdp_documents_into_pdf_documents_using_the_web_service_api)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Convert XDP documents into PDF documents using the Java API {#convert-xdp-documents-into-pdf-documents-using-the-java-api}

Convert XDP documents into PDF documents by using the PDF Utilities API (Java):

1. Include project files

   Include client JAR files, such as adobe-pdfutility-client.jar, in your Java project’s class path. 

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceClient` object by using its constructor and passing a `ServiceClientFactory` object that contains connection properties. 

1. Invoke the XDP to PDF conversion operation

   To perform the conversion, invoke the `PDFUtilityServiceClient` object’s `convertXDPtoPDF` method and pass in a `com.adobe.idp.Document` object that represents the XDP file. The method returns a `com.adobe.idp.Document` object that represents the newly created PDF file.

**See also**

[Converting XDP Documents into PDF Documents](pdf-utilities#converting_xdp_documents_into_pdf_documents)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Converting XDP documents into PDF documents using the web service API {#converting-xdp-documents-into-pdf-documents-using-the-web-service-api}

Convert XDP documents into PDF documents by using the PDF Utilities API (web service API):

1. Include project files

    * Create a Microsoft .NET client assembly that consumes the PDF Utilities service WSDL file. 
    * Reference the Microsoft .NET client assembly.

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceService` object by using your proxy class constructor. 

1. Invoke the XDP to PDF conversion operation

   To perform the conversion, invoke the `PDFUtilityServiceService` object’s `convertXDPtoPDF` method and pass in a `BLOB` object that represents the XDP file. The method returns a `BLOB` object that represents the newly created PDF file.

**See also**

[Converting XDP Documents into PDF Documents](pdf-utilities#converting_xdp_documents_into_pdf_documents)

[Quick Start (Base64): Converting an XDP document to a PDF document using the web service API](#unresolvedlink-lc-qs-pdf-utilities-pu.xml#ws624e3cba99b79e12e69a9941333732bac8-7d2f.2)

[Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_base64_encoding)

[Creating a .NET client assembly that uses Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#creating_a_net_client_assembly_that_uses_base64_encoding)

## Retrieving PDF Document Properties {#retrieving-pdf-document-properties}

You can use the PDF Utilities Java and web service APIs to programmatically retrieve PDF document properties, such as whether the document is a fillable form or the minimum Acrobat version required to read the document.

>[!NOTE]
>
>For more information about the PDF Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63)

### Summary of steps {#summary_of_steps-2}

To retrieve PDF document properties, perform the following steps:

1. Include project files.
1. Create a PDFUtilityService client.
1. Invoke the properties retrieval operation.

**Include project files**

Include necessary files into your development project. If you are creating a client application using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

**Create a PDFUtilityService client**

Before you can programmatically perform a PDF Utilities operation, you must create a PDFUtilityService client. With the Java API, this is accomplished by creating a `PDFUtilityServiceClient` object. With the web service API, this is accomplished using a `PDFUtilityServiceService` object.

**Invoke the properties retrieval operation**

After you create the service client, you can invoke the properties retrieval operation.

**See also**

[Retrieve PDF document properties using the Java API](pdf-utilities#retrieve_pdf_document_properties_using_the_java_api)

[Retrieve PDF document properties using the web service API](pdf-utilities#retrieve_pdf_document_properties_using_the_web_service_api)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Retrieve PDF document properties using the Java API {#retrieve-pdf-document-properties-using-the-java-api}

Retrieve PDF document properties by using the PDF Utilities API (Java):

1. Include project files

   Include client JAR files, such as adobe-pdfutility-client.jar, in your Java project’s class path. 

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceClient` object by using its constructor and passing a `ServiceClientFactory` object that contains connection properties. 

1. Invoke the properties retrieval operation

   To perform the conversion, invoke the `PDFUtilityServiceClient` object’s `getPDFProperties` method and pass in the following:

    * A `com.adobe.idp.Document` object that represents the PDF document. 
    * A `PDFPropertiesOptionSpec` object that contains the properties to be evaluated.

   The method returns a `PDFPropertiesResult` object that contains the results of the query.

**See also**

[Retrieving PDF Document Properties](pdf-utilities#retrieving_pdf_document_properties)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Retrieve PDF document properties using the web service API {#retrieve-pdf-document-properties-using-the-web-service-api}

Retrieve PDF document properties by using the PDF Utilities web service API:

1. Include project files

    * Create a Microsoft .NET client assembly that consumes the PDF Utilities service WSDL file. 
    * Reference the Microsoft .NET client assembly.

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceService` object by using your proxy class constructor. 

1. Invoke the properties retrieval operation

   To perform the conversion, invoke the `PDFUtilityServiceService` object’s `getPDFProperties` method and pass in the following:

    * A `BLOB` object that represents the PDF document. 
    * A `PDFPropertiesOptionSpec` object that contains the properties to be evaluated.

   The method returns a `PDFPropertiesResult` object that contains the results of the query.

**See also**

[Retrieving PDF Document Properties](pdf-utilities#retrieving_pdf_document_properties)

[Quick Start (Base64): Retrieving PDF document properties using the web service API](#unresolvedlink-lc-qs-pdf-utilities-pu.xml#ws624e3cba99b79e12e69a9941333732bac8-7d2b.2)

[Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_base64_encoding)

[Creating a .NET client assembly that uses Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#creating_a_net_client_assembly_that_uses_base64_encoding)

## Setting PDF Document Save Modes {#setting-pdf-document-save-modes}

You can use the PDF Utilities service Java and web service APIs to programmatically set a save mode for a PDF document. When using the PDF Utilities service to set a save mode, the PDF Utilities service only sets the save mode and does not actually save the PDF document. The PDF document is saved when it is passed to another service operation. For example, you can use the PDF Utilities service to set a specific save mode and pass it to the Encryption service, where the PDF document is actually saved and encrypted.

>[!NOTE]
>
>For more information about the PDF Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

### Summary of steps {#summary_of_steps-3}

To set the save option for PDF documents, perform the following steps:

1. Include project files.
1. Create a PDFUtilityService client.
1. Set the save mode.
1. Invoke the save operation.
1. Pass the PDF document to another operation.

**Include project files**

Include necessary files into your development project. If you are creating a client application using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

**Create a PDFUtilityService client**

Before you can programmatically perform a PDF Utilities operation, you must create a PDFUtilityService client. With the Java API, this is accomplished by creating a `PDFUtilityServiceClient` object. With the web service API, this is accomplished using a `PDFUtilityServiceService` object.

**Set the Save mode**

You can choose one of the following save options:

* `INCREMENTAL`: To save incrementally to reduce the time required to save
* `FAST_WEB_VIEW`: save for fast web viewing 
* `FULL`: To save using a full save (without optimizations)

**Invoke the save style operation**

After you create the service client, you can invoke the properties retrieval operation.

**Pass the PDF document to another AEM Forms operation**

Once the PDF Utilities service sets the specified Save mode, pass the PDF document to another AEM Forms operation. Once returned from that operation, the PDF document is saved in the specified mode. For example, if you use the PDF Utilities service to set the `FAST_WEB_VIEW` mode and then pass the PDF document to the Encryption service’s `encryptUsingPassword` operation, the returned PDF document is encrypted with a password and save in the `FAST_WEB_VIEW` mode.

>[!NOTE]
>
>The Quick Start that is associated with this section sets the `FAST_WEB_VIEW` mode and then passes the PDF document to the Encryption service’s `encryptUsingPassword` operation.

**See also**

[Set PDF document save options using the Java API](pdf-utilities#set_pdf_document_save_options_using_the_java_api)

[Set PDF document save options using the web service API](pdf-utilities#set_pdf_document_save_options_using_the_web_service_api)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

[Encrypting PDF Documents with a Password](/programming-with-aem-forms/encrypting-decrypting-pdf-documents#encrypting_pdf_documents_with_a_password)

### Set PDF document save options using the Java API {#set-pdf-document-save-options-using-the-java-api}

Set the PDF document save options by using the PDF Utilities API (Java):

1. Include project files

   Include client JAR files, such as adobe-pdfutility-client.jar, in your Java project’s class path. 

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceClient` object by using its constructor and passing a `ServiceClientFactory` object that contains connection properties. 

1. Set the Save mode

    * Create a `PDFUtilitySaveMode` object by using its constructor. 
    * Set the save mode by invoking the `PDFUtilitySaveMode` object’s `setSaveStyle` method and passing a string value that specifies the save mode. For example, to save for fast web viewing, pass `FAST_WEB_VIEW`.

1. Invoke the save style operation

   Invoke the `PDFUtilityServiceClient` object’s `setSaveMode` method and pass the following values:

    * A `com.adobe.idp.Document` object that represents the PDF document. 
    * A `PDFUtilitySaveMode` object that contains the save style to be used.
    * A Boolean value used to determine whether to override any previous settings.

   The method returns a `com.adobe.idp.Document` object formatted using the specified save style. 

1. Pass the PDF document to another AEM Forms operation

    * Pass the returned `com.adobe.idp.Document` object to another AEM Forms operation.

**See also**

[Setting PDF Document Save Modes](pdf-utilities#setting_pdf_document_save_modes)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Set PDF document save options using the web service API {#set-pdf-document-save-options-using-the-web-service-api}

Set the PDF document save options by using the PDF Utilities AP (web service):

1. Include project files

    * Create a Microsoft .NET client assembly that consumes the PDF Utilities service WSDL file. 
    * Reference the Microsoft .NET client assembly.

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceService` object by using your proxy class constructor. 

1. Set the Save mode

    * Create a `PDFUtilitySaveMode` object by using its constructor. 
    * Set the save mode by assigning a string value to the `PDFUtilitySaveMode` object’s `saveStyle` method that specifies the save mode. For example, to save for fast web viewing, specify `FAST_WEB_VIEW`.

1. Invoke the save style operation

   Invoke the `PDFUtilityServiceService` object’s `setSaveMode` method and pass the following values:

    * A `BLOB` object that represents the PDF document. 
    * A `PDFUtilitySaveMode` object that contains the save style to be used.
    * A Boolean value used to determine whether to override any previous settings.

   The method returns a `BLOB` object formatted using the specified save style. You can then save that object as a PDF document.

1. Pass the PDF document to another Forms operation

    * Pass the returned `BLOB` object to another AEM Forms operation.

**See also**

[Setting PDF Document Save Modes](pdf-utilities#setting_pdf_document_save_modes)

[Quick Start (Base64): Setting the save style for a PDF document using the web service API](#unresolvedlink-lc-qs-pdf-utilities-pu.xml#ws624e3cba99b79e12e69a9941333732bac8-7d2a.2)

[Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_base64_encoding)

[Creating a .NET client assembly that uses Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#creating_a_net_client_assembly_that_uses_base64_encoding)

## Sanitizing PDF Documents {#sanitizing-pdf-documents}

You can use the PDF Utilities Java APIs to programmatically convert PDF documents into XDP documents.

>[!NOTE]
>
>For more information about the PDF Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

### Summary of steps {#summary_of_steps-4}

To sanitize PDF document, perform the following steps:

1. Include project files.
1. Create a PDFUtilityService client.
1. Invoke the sanitization operation.

**Include project files**

Include necessary files into your development project. To create a client application using Java, include the necessary JAR files.

**Create a PDFUtilityService client**

Before you can programmatically perform a sanitization operation, you must create a PDFUtilityService client. With the Java API, this is accomplished by creating a `PDFUtilityServiceClient` object.

**Invoke the PDF to XDP conversion operation**

After you create the service client, you can invoke the sanitization operation.

**See also**

[Convert PDF documents into XDP documents using the Java API](pdf-utilities#convert_pdf_documents_into_xdp_documents_using_the_java_api)

[Convert PDF documents into XDP documents using the web service API](pdf-utilities#convert_pdf_documents_into_xdp_documents_using_the_web_service_api)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Sanitize PDF documents using the Java API {#sanitize-pdf-documents-using-the-java-api}

Sanitize documents by using the PDF Utilities API (Java):

1. Include project files

   Include client JAR files, such as the adobe-pdfutility-client.jar, in your Java project’s class path.

1. Create a PDFUtilityService client

   Create a `PDFUtilityServiceClient` object by using its constructor and passing a `ServiceClientFactory` object that contains connection properties. 

1. Invoke the PDF to XDP conversion operation

   To perform the conversion, invoke the `PDFUtilityServiceClient` object’s `convertPDFtoXDP` method and pass in a `com.adobe.idp.Document` object that represents the PDF file. The method returns a `com.adobe.idp.Document` object that represents the newly created XDP file.

**See also**

[Sanitizing PDF documents](/programming-with-aem-forms/pdf-utilities-service-java-api#quick_start_soap_mode_sanitizing_pdf_documents)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)S
