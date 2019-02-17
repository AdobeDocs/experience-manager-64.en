---
title: Working with XMP Utilities
seo-title: Working with XMP Utilities
description: null
seo-description: null
uuid: 4c4e3b04-6e41-43f5-bc45-c2557691bef2
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: operations
discoiquuid: 82cf7926-8757-46e9-91d5-a9eed73c3f3d
index: y
internal: n
snippet: y
---

# Working with XMP Utilities{#working-with-xmp-utilities}

**About the XMP Utilities Service**

PDF documents contain metadata, which is information about the document as distinguished from the contents of the document, such as text and graphics. Adobe Extensible Metadata Platform (XMP) is a standard for handling document metadata.

The XMP Utilities service can retrieve and save XMP metadata from PDF documents, and import XMP metadata into PDF documents.

You can accomplish these tasks using the XMP Utilities service:

* Import metadata into PDF documents. (See [Importing Metadata into PDF Documents](xmp-utilities#importing_metadata_into_pdf_documents).)
* Export metadata from PDF documents. (See [Exporting Metadata from PDF Documents](xmp-utilities#exporting_metadata_from_pdf_documents).)

>[!NOTE]
>
>For more information about the XMP Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

## Importing Metadata into PDF Documents {#importing-metadata-into-pdf-documents}

You can use the XMP Utilities Java and web service APIs to programmatically import XMP metadata into a PDF document. Metadata provides information about a PDF document such as the document’s author and keywords related to the document. Metadata can be located in the document’s Document Properties dialog, as shown in the following illustration. 

![](assets/ww_ww_metadatadialog.png)

To programmatically import metadata into a PDF document, you can use an existing XML document that specifies the metadata values or you can use an object of type `XMPUtilityMetadata`. (See [AEM Forms API Reference](http://www.adobe.com/go/learn_aemforms_javadocs_63_en).)

>[!NOTE]
>
>This section discusses how to use an XML document to import metadata into a PDF document.

The following XML code contains metadata values that correspond to the previous illustration. For example, notice the bold items, which specify keywords.

```as3
 <?xpacket begin="?" id="W5M0MpCehiHzreSzNTczkc9d"?> 
 <x:xmpmeta xmlns:x="adobe:ns:meta/" x:xmptk="Adobe XMP Core 4.2-jc015 52.349034, 2008 Jun 20 00:30:39-PDT (debug)"> 
       <rdf:RDF xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"> 
          <rdf:Description rdf:about="" 
                xmlns:xmp="http://ns.adobe.com/xap/1.0/"> 
             <xmp:MetadataDate>2008-10-22T10:52:21-04:00</xmp:MetadataDate> 
             <xmp:CreatorTool>AEM Forms</xmp:CreatorTool> 
             <xmp:ModifyDate>2008-10-22T10:52:21-04:00</xmp:ModifyDate> 
             <xmp:CreateDate>2008-02-13T11:00:18-05:00</xmp:CreateDate> 
          </rdf:Description> 
          <rdf:Description rdf:about="" 
                xmlns:pdf="http://ns.adobe.com/pdf/1.3/"> 
             <pdf:Producer>AEM Forms</pdf:Producer> 
             <pdf:Keywords>keyword1, keyword2, keyword3,keyword4</pdf:Keywords> 
          </rdf:Description> 
          <rdf:Description rdf:about="" 
                xmlns:xmpMM="http://ns.adobe.com/xap/1.0/mm/"> 
             <xmpMM:DocumentID>uuid:1cce1f84-331e-4d8d-8538-15441c271dd7</xmpMM:DocumentID> 
             <xmpMM:InstanceID>uuid:cdda0ca6-7c91-4771-9dc9-796c8fe59350</xmpMM:InstanceID> 
          </rdf:Description> 
          <rdf:Description rdf:about="" 
                > 
             <dc:format>application/pdf</dc:format> 
             <dc:description> 
                <rdf:Alt> 
                   <rdf:li xml:lang="x-default">Adobe Designer Sample</rdf:li> 
                </rdf:Alt> 
             </dc:description> 
             <dc:title> 
                <rdf:Alt> 
                   <rdf:li xml:lang="x-default">Grant Application</rdf:li> 
                </rdf:Alt> 
             </dc:title> 
             <dc:creator> 
                <rdf:Seq> 
                   <rdf:li>Tony Blue</rdf:li> 
                </rdf:Seq> 
             </dc:creator> 
             <dc:subject> 
                <rdf:Bag> 
                   <rdf:li>keyword1</rdf:li> 
                   <rdf:li>keyword2</rdf:li> 
                   <rdf:li>keyword3</rdf:li> 
                   <rdf:li>keyword4</rdf:li> 
                </rdf:Bag> 
             </dc:subject> 
          </rdf:Description> 
          <rdf:Description rdf:about="" 
                xmlns:desc="http://ns.adobe.com/xfa/promoted-desc/"> 
             <desc:version rdf:parseType="Resource"> 
                <rdf:value>1.0</rdf:value> 
                <desc:ref>/template/subform[1]</desc:ref> 
             </desc:version> 
             <desc:contact rdf:parseType="Resource"> 
                <rdf:value>Adobe Systems Incorporated</rdf:value> 
                <desc:ref>/template/subform[1]</desc:ref> 
             </desc:contact> 
          </rdf:Description> 
       </rdf:RDF> 
 </x:xmpmeta>
```

>[!NOTE]
>
>For more information about the XMP Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

### Summary of steps {#summary-of-steps}

To import XMP metadata into a PDF document, perform the following steps:

1. Include project files.
1. Create an XMPUtilityService client.
1. Invoke the XMP metadata import operation.

**Include project files**

Include necessary files into your development project. If you are creating a client application using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

**Create an XMPUtilityService client**

Before you can programmatically perform an XMP Utilities operation, you must create an XMPUtilityService client. With the Java API, this is accomplished by creating an `XMPUtilityServiceClient` object. With the web service API, this is accomplished by using an `XMPUtilityServiceService` object.

**Invoke the XMP metadata import operation**

After you create the service client, you can invoke one of the XMP metadata import operations to import the XMP metadata into the specified PDF document.

**See also**

[Import XMP metadata using the Java API](xmp-utilities#import_xmp_metadata_using_the_java_api)

[Importing XMP metadata using the web service API](xmp-utilities#importing_xmp_metadata_using_the_web_service_api)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Import XMP metadata using the Java API {#import-xmp-metadata-using-the-java-api}

Import XMP metadata by using the XMP Utilities API (Java):

1. Include project files

   Include client JAR files, such as adobe-pdfutility-client.jar, in your Java project’s class path.

   >[!NOTE]
   >
   >The adobe-pdfutility-client.jar file contains classes that enable you to programmatically invoke the XMP Utilities service.

1. Create an XMPUtilityService client

   Create an `XMPUtilityServiceClient` object by using its constructor and passing a `ServiceClientFactory` object that contains connection properties.**

1. Invoke the XMP metadata import operation

   To modify the XMP metadata, invoke either the `XMPUtilityServiceClient` object’s `importMetadata` method or its `importXMP` method.

   If you use the `importMetadata` method, pass in the following values:

    * A `com.adobe.idp.Document` object that represents the PDF file.
    * An `XMPUtilityMetadata` object that contains the metadata to be imported.

   If you use the `importXMP` method, pass in the following values:

    * A `com.adobe.idp.Document` object that represents the PDF file.
    * A `com.adobe.idp.Document` object that represents an XML file that contains the metadata to be imported.

   In either case, the returned value is a `com.adobe.idp.Document` object that represents the PDF file with the newly imported metadata. You can then save this object to disk.

**See also**

[Importing Metadata into PDF Documents](xmp-utilities#importing_metadata_into_pdf_documents)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Importing XMP metadata using the web service API {#importing-xmp-metadata-using-the-web-service-api}

To programmatically import XMP metadata using the XMP Utilities web service API, perform the following tasks:

1. Include project files

    * Create a Microsoft .NET client assembly that consumes the XMP Utilities service WSDL file. (See [Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_base64_encoding).)
    * Reference the Microsoft .NET client assembly. (See [Creating a .NET client assembly that uses Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#creating_a_net_client_assembly_that_uses_base64_encoding).)

1. Create an XMPUtilityService client

   Create an `XMPUtilityServiceService` object by using your proxy class constructor. 

1. Invoke the XMP metadata import operation

   To modify the XMP metadata, invoke either the `XMPUtilityServiceService` object’s `importMetadata` method or its `importXMP` method.

   If you use the `importMetadata` method, pass in the following values:

    * A `BLOB` object that represents the PDF file.
    * An `XMPUtilityMetadata` object that contains the metadata to be imported.

   If you use the `importXMP` method, pass in the following values:

    * A `BLOB` object that represents the PDF file.
    * A `BLOB` object that represents an XML file that contains the metadata to be imported.

   In either case, the returned value is a `BLOB` object that represents the PDF file with the newly imported metadata. You can then save this object to disk.

**See also**

[Importing Metadata into PDF Documents](xmp-utilities#importing_metadata_into_pdf_documents)

[Quick Start (Base64): Importing XMP metadata using the web service API](#unresolvedlink-lc-qs-xmp-utilities-xu.xml#ws624e3cba99b79e12e69a9941333732bac8-7be8.2)

[Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_base64_encoding)

[Creating a .NET client assembly that uses Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#creating_a_net_client_assembly_that_uses_base64_encoding)

## Exporting Metadata from PDF Documents {#exporting-metadata-from-pdf-documents}

You can use the XMP Utilities Java and web service APIs to programmatically retrieve and save XMP metadata from a PDF document.

>[!NOTE]
>
>For more information about the XMP Utilities service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

### Summary of steps {#summary_of_steps-1}

To export XMP metadata from a PDF document, perform the following steps:

1. Include project files.
1. Create an XMPUtilityService client.
1. Invoke the XMP metadata export operation.

**Include project files**

Include necessary files into your development project. If you are creating a client application using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

**Create an XMPUtilityService client**

Before you can programmatically perform an XMP Utilities operation, you must create an XMPUtilityService client. With the Java AP,I this is accomplished by creating an `XMPUtilityServiceClient` object. With the web service API, this is accomplished using an `XMPUtilityServiceService` object.

**Invoke the XMP metadata export operation**

After you create the service client, you can invoke one of the XMP metadata export operations, which can be used to inspect the XMP metadata or save it to disk.

**See also**

[Import XMP metadata using the Java API](xmp-utilities#import_xmp_metadata_using_the_java_api)

[Importing XMP metadata using the web service API](xmp-utilities#importing_xmp_metadata_using_the_web_service_api)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Export XMP metadata using the Java API {#export-xmp-metadata-using-the-java-api}

Export XMP metadata by using the XMP Utilities API (Java):

1. Include project files

   Include client JAR files, such as adobe-pdfutility-client.jar, in your Java project’s class path.

   >[!NOTE]
   >
   >The adobe-pdfutility-client.jar file contains classes that enable you to programmatically invoke the XMP Utility service.

1. Create an XMPUtilityService client

   Create an `XMPUtilityServiceClient` object by using its constructor and passing a `ServiceClientFactory` object that contains connection properties.**

1. Invoke the XMP metadata import operation

   To inspect the XMP metadata, invoke the `XMPUtilityServiceClient` object’s `exportMetadata` method and pass in a `com.adobe.idp.Document` object that represents the PDF file. The method returns an `XMPUtilityMetadata` object that contains the retrieved metadata.

   To retrieve and save the XMP metadata, invoke the `XMPUtilityServiceClient` object’s `exportXMP` method and pass in a `com.adobe.idp.Document` object that represents the PDF file. The method returns a `com.adobe.idp.Document` object that contains the retrieved metadata, which you can subsequently save to disk as an XML file.

**See also**

[Exporting Metadata from PDF Documents](xmp-utilities#exporting_metadata_from_pdf_documents)

[Including AEM Forms Java library files](/programming-with-aem-forms/invoking-aem-forms-using-java#including_aem_forms_java_library_files)

[Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties)

### Export XMP metadata using the web service API {#export-xmp-metadata-using-the-web-service-api}

Export XMP metadata by using the XMP Utilities API (web service):

1. Include project files

    * Create a Microsoft .NET client assembly that consumes the XMP Utilities service WSDL file. 
    * Reference the Microsoft .NET client assembly.

1. Create an XMPUtilityService client

   Create an `XMPUtilityServiceService` object by using your proxy class constructor. 

1. Invoke the XMP metadata import operation

   To inspect the XMP metadata, invoke the `XMPUtilityServiceClient` object’s `exportMetadata` method and pass in a `BLOB` object that represents the PDF file. The method returns an `XMPUtilityMetadata` object that contains the retrieved metadata.

   To retrieve and save the XMP metadata, invoke the `XMPUtilityServiceClient` object’s `exportXMP` method and pass in a `BLOB` object that represents the PDF file. The method returns a `BLOB` object that contains the retrieved metadata, which you can subsequently save to disk as an XML file.

**See also**

[Exporting Metadata from PDF Documents](xmp-utilities#exporting_metadata_from_pdf_documents)

[Invoking AEM Forms using Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_base64_encoding)

[Creating a .NET client assembly that uses Base64 encoding](/programming-with-aem-forms/invoking-aem-forms-using-web#creating_a_net_client_assembly_that_uses_base64_encoding)
