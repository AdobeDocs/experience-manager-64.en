---
title: Assembling Non-Interactive PDF Documents
seo-title: Assembling Non-Interactive PDF Documents
description: null
seo-description: null
uuid: a81d6856-32d2-4275-b91e-ac07c54ff6c0
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/assembling_pdf_documents
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: operations
discoiquuid: ca4229be-b690-44ef-a35b-28169d761ef6
---

# Assembling Non-Interactive PDF Documents{#assembling-non-interactive-pdf-documents}

You can assemble a non-interactive PDF document when using an interactive PDF form as input. That is, assume that you have a form that users can use to enter data into its fields. You can pass that form to the Assembler service, resulting in the Assembler service returning a PDF document that prevents users from entering data into its fields. This document is a non-interactive PDF form. For example, the following illustration shows a mortgage application that represents an interactive form.

![](lc_as_assemble_noninteractive_pdfs_an.xml)

For the purpose of this discussion, assume that the following DDX document is used.

```as3
 <?xml version="1.0" encoding="UTF-8"?> 
 <DDX xmlns="http://ns.adobe.com/DDX/1.0/"> 
      <PDF result="out.pdf"> 
        <PDF source="inDoc"/> 
        <NoXFA/> 
      </PDF> 
 </DDX>
```

Within this DDX document, notice that the source attribute is assigned the value `inDoc`. In situations where only one input PDF document is passed to the Assembler service and one PDF document is returned, and you invoke the `invokeOneDocument` operation, assign the value `inDoc` to the PDF source attribute. When invoking the `invokeOneDocument` operation, the `inDoc` value is a predefined key that must be specified in the DDX document.

In contrast, when passing two or more input PDF documents to the Assembler service, you can invoke the `invokeDDX` operation. In this situation, assign the file name of the input PDF document to the `source` attribute.

This DDX document contains the `NoXFA` element, which instructs the Assembler service to return a non-interactive PDF document.

The Assembler service can assemble non-interactive PDF documents without the Output service being part of your AEM forms installation if the input PDF document is based on an Acrobat form or a static XFA form. However, if the input PDF document is a dynamic XFA form, the Output service must be part of your AEM forms installation. If the Output service is not part of your AEM forms installation when a dynamic XFA form is assembled, an exception is thrown. See [Creating Document Output Streams](/programming-with-aem-forms/creating-document-output-streams-creating creating-document-output-streams-creating#creating_document_output_streams).

>[!NOTE]
>
>Before reading this section, it is recommended that you be familiar with assembling PDF documents using the Assembler service. This section does not discuss concepts, such as creating a collection object that contains input documents or learning how to extract the results from the returned collection object. (See [Programmatically Assembling PDF Documents](/programming-with-aem-forms/programmatically-assembling-pdf-documents-programmatically programmatically-assembling-pdf-documents-programmatically#programmatically_assembling_pdf_documents).)

>[!NOTE]
>
>For more information about the Assembler service, see [Services Reference for AEM Forms](http://www.adobe.com/go/learn_aemforms_services_63).

>[!NOTE]
>
>For more information about a DDX document, see [Assembler Service and DDX Reference](http://www.adobe.com/go/learn_aemforms_ddx_63).

## Summary of steps {#summary-of-steps}

To assemble a non-interactive PDF document, perform the following tasks:

1. Include project files.
1. Create a PDF Assembler client.
1. Reference an existing DDX document.
1. Reference an interactive PDF document.
1. Set run-time options.
1. Assemble the PDF document. 
1. Save the non-interactive PDF document.

**Include project files**

Include the necessary files in your development project. If you are creating a client application by using Java, include the necessary JAR files. If you are using web services, ensure that you include the proxy files.

The following JAR files must be added to your project’s class path:

* adobe-livecycle-client.jar
* adobe-usermanager-client.jar
* adobe-assembler-client.jar
* adobe-utilities.jar (required if AEM Forms is deployed on JBoss) 
* jbossall-client.jar (required if AEM Forms is deployed on JBoss)

if AEM Forms is deployed on a supported J2EE application server other than JBoss, you must replace the adobe-utilities.jar and jbossall-client.jar files with JAR files that are specific to the J2EE application server that AEM Forms is deployed on.

**Create an Assembler client**

Before you can programmatically perform an Assembler operation, you must create an Assembler service client.

**Reference an existing DDX document**

A DDX document must be referenced to assemble a PDF document. This DDX document must contain the `NoXFA` element, which instructs the Assembler service to return a non-interactive PDF document.

**Reference an interactive PDF document**

An interactive PDF document must be referenced and passed to the Assembler service to get back a non-interactive PDF document.

**Set run-time options**

You can set run-time options that control the behavior of the Assembler service while it performs a job. For example, you can set an option that instructs the Assembler service to continue processing a job if an error is encountered.

**Assemble the PDF document**

After you create the Assembler service client, reference the DDX document, reference an interactive PDF document, and set run-time options, you can invoke the `invokeOneDocument` operation. Because only one input PDF document is passed to the Assembler service and a single document is returned, you can use the `invokeOneDocument` operation as opposed to the `invokeDDX` operation.

**Save the non-interactive PDF document**

If only a single PDF document is passed to the Assembler service, the Assembler service returns a single document instead of a collection object. That is, when invoking the `invokeOneDocument` operation, a single document is returned. Because the DDX document referenced in this section contains instructions to create a non-interactive PDF document, the Assembler service returns a non-interactive PDF document that can be saved as a PDF file.

**See also**

[Assemble a non-interactive PDF document using the Java API](/programming-with-aem-forms/assembling-non-interactive-pdf-documents assembling-non-interactive-pdf-documents#assemble_a_non_interactive_pdf_document_using_the_java_api)

[Assemble a non-interactive PDF document using the web service API](/programming-with-aem-forms/assembling-non-interactive-pdf-documents assembling-non-interactive-pdf-documents#assemble_a_non_interactive_pdf_document_using_the_web_service_api)

[Including AEM Forms Java library files](#unresolvedlink-lc-in-invoke-using-java-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7b4b.2)

[Setting connection properties](#unresolvedlink-lc-in-invoke-using-java-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7fd6.2)

[Programmatically Assembling PDF Documents](/programming-with-aem-forms/programmatically-assembling-pdf-documents-programmatically programmatically-assembling-pdf-documents-programmatically#programmatically_assembling_pdf_documents)

## Assemble a non-interactive PDF document using the Java API {#assemble-a-non-interactive-pdf-document-using-the-java-api}

Assemble a non-interactive PDF document by using the Assembler Service API (Java):

1. Include project files.

   Include client JAR files, such as adobe-assembler-client.jar, in your Java project’s class path.

1. Create an Assembler client.

    * Create a `ServiceClientFactory` object that contains connection properties. 
    * Create an `AssemblerServiceClient` object by using its constructor and passing the `ServiceClientFactory` object.

1. Reference an existing DDX document.

    * Create a `java.io.FileInputStream` object that represents the DDX document by using its constructor and passing a string value that specifies the location of the DDX file.
    * Create a `com.adobe.idp.Document` object by using its constructor and passing the `java.io.FileInputStream` object.

1. Reference an interactive PDF document.

    * Create a `java.io.FileInputStream` object by using its constructor and passing the location of an interactive PDF document. 
    * Create a `com.adobe.idp.Document` object and pass the `java.io.FileInputStream` object that contains the PDF document. This `com.adobe.idp.Document` object is passed to the `invokeOneDocument` method.

1. Set run-time options.

    * Create an `AssemblerOptionSpec` object that stores run-time options by using its constructor.
    * Set run-time options to meet your business requirements by invoking a method that belongs to the `AssemblerOptionSpec` object. For example, to instruct the Assembler service to continue processing a job when an error occurs, invoke the `AssemblerOptionSpec` object’s `setFailOnError` method and pass `false`.

1. Assemble the PDF document.

   Invoke the `AssemblerServiceClient` object’s `invokeOneDocument` method and pass the following values:

    * A `com.adobe.idp.Document` object that represents the DDX document. Ensure that this DDX document contains the value `inDoc` for the PDF source element.
    * A `com.adobe.idp.Document` object that contains the interactive PDF document.
    * A `com.adobe.livecycle.assembler.client.AssemblerOptionSpec` object that specifies the run-time options, including default font and job log level.

   The `invokeOneDocument` method returns a `com.adobe.idp.Document` object that contains a non-interactive PDF document.

1. Save the non-interactive PDF document.

    * Create a `java.io.File` object and ensure that the file name extension is .pdf.
    * Invoke the `Document` object’s `copyToFile` method to copy the contents of the `Document` object to the file. Ensure that you use the `Document` object that the `invokeOneDocument` method returned.

For code examples, see these Assembler Service Quick Starts in * [API Quick Starts (Code Examples)](#unresolvedlink-lc-qs-intro-in.xml#ws624e3cba99b79e12-171c1d181336a34f42f-8000.2)*:

* “Quick Start (SOAP mode): Assembling a non-interactive PDF document using the Java API”

## Assemble a non-interactive PDF document using the web service API {#assemble-a-non-interactive-pdf-document-using-the-web-service-api}

Assemble a non-interactive PDF document by using the Assembler Service API (web service):

1. Include project files.

   Create a Microsoft .NET project that uses MTOM. Ensure that you use the following WSDL definition: `http://localhost:8080/soap/services/AssemblerService?WSDL&lc_version=9.0.1`.

   >[!NOTE]
   >
   >Replace `localhost` with the IP address of the server hosting AEM Forms.

1. Create an Assembler client.

    * Create an `AssemblerServiceClient` object by using its default constructor. 
    * Create an `AssemblerServiceClient.Endpoint.Address` object by using the `System.ServiceModel.EndpointAddress` constructor. Pass a string value that specifies the WSDL to the AEM Forms service (for example, `http://localhost:8080/soap/services/AssemblerService?blob=mtom`). You do not need to use the `lc_version` attribute. This attribute is used when you create a service reference. 
    * Create a `System.ServiceModel.BasicHttpBinding` object by getting the value of the `AssemblerServiceClient.Endpoint.Binding` field. Cast the return value to `BasicHttpBinding`. 
    * Set the `System.ServiceModel.BasicHttpBinding` object’s `MessageEncoding` field to `WSMessageEncoding.Mtom`. This value ensures that MTOM is used. 
    * Enable basic HTTP authentication by performing the following tasks:

        * Assign the AEM forms user name to the field `AssemblerServiceClient.ClientCredentials.UserName.UserName`.
        * Assign the corresponding password value to the field `AssemblerServiceClient.ClientCredentials.UserName.Password`.
        * Assign the constant value `HttpClientCredentialType.Basic` to the field `BasicHttpBindingSecurity.Transport.ClientCredentialType`. 
        * Assign the constant value `BasicHttpSecurityMode.TransportCredentialOnly` to the field `BasicHttpBindingSecurity.Security.Mode`.

1. Reference an existing DDX document.

    * Create a `BLOB` object by using its constructor. The `BLOB` object is used to store the DDX document.
    * Create a `System.IO.FileStream` object by invoking its constructor and passing a string value that represents the file location of the DDX document and the mode to open the file in.
    * Create a byte array that stores the content of the `System.IO.FileStream` object. You can determine the size of the byte array by getting the `System.IO.FileStream` object’s `Length` property. 
    * Populate the byte array with stream data by invoking the `System.IO.FileStream` object’s `Read` method. Pass the byte array, the starting position, and the stream length to read.
    * Populate the `BLOB` object by assigning its `MTOM` field with the contents of the byte array.

1. Reference an interactive PDF document.

    * Create a `BLOB` object by using its constructor. The `BLOB` object is used to store the input PDF document. This `BLOB` object is passed to the `invokeOneDocument` as an argument. 
    * Create a `System.IO.FileStream` object by invoking its constructor and passing a string value that represents the file location of the input PDF document and the mode to open the file in.
    * Create a byte array that stores the content of the `System.IO.FileStream` object. You can determine the size of the byte array by getting the `System.IO.FileStream` object’s `Length` property. 
    * Populate the byte array with stream data by invoking the `System.IO.FileStream` object’s `Read` method. Pass the byte array, the starting position, and the stream length to read.
    * Populate the `BLOB` object by assigning its `MTOM` field with the contents of the byte array.

1. Set run-time options.

    * Create an `AssemblerOptionSpec` object that stores run-time options by using its constructor.
    * Set run-time options to meet your business requirements by assigning a value to a data member that belongs to the `AssemblerOptionSpec` object. For example, to instruct the Assembler service to continue processing a job when an error occurs, assign `false` to the `AssemblerOptionSpec` object’s `failOnError` data member.

1. Assemble the PDF document.

   Invoke the `AssemblerServiceClient` object’s `invokeOneDocument` method and pass the following values:

    * A `BLOB` object that represents the DDX document
    * A `BLOB` object that represents the interactive PDF document
    * An `AssemblerOptionSpec` object that specifies run-time options

   The `invokeOneDocument` method returns a `BLOB` object that contains a non-interactive PDF document.

1. Save the non-interactive PDF document.

    * Create a `System.IO.FileStream` object by invoking its constructor and passing a string value that represents the file location of the non-interactive PDF document and the mode to open the file in.
    * Create a byte array that stores the content of the `BLOB` object that the `invokeOneDocument` method returned. Populate the byte array by getting the value of the `BLOB` object’s `MTOM` field.
    * Create a `System.IO.BinaryWriter` object by invoking its constructor and passing the `System.IO.FileStream` object.
    * Write the contents of the byte array to a PDF file by invoking the `System.IO.BinaryWriter` object’s `Write` method and passing the byte array.

For code examples, see this Assembler Service Quick Start in * [API Quick Starts (Code Examples)](#unresolvedlink-lc-qs-intro-in.xml#ws624e3cba99b79e12-171c1d181336a34f42f-8000.2)*:

* “Quick Start (MTOM): Assembling a non-interactive PDF document using the web service API”.

**See also**

[Assembling Non-Interactive PDF Documents](/programming-with-aem-forms/assembling-non-interactive-pdf-documents assembling-non-interactive-pdf-documents#assembling_non_interactive_pdf_documents)

[Invoking AEM Forms using MTOM](#unresolvedlink-lc-in-invoke-using-web-services-iu.xml#ws624e3cba99b79e12e69a9941333732bac8-7fe7.2)
