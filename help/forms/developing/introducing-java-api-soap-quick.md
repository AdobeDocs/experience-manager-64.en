---
title: Introducing Java API QuickStart
seo-title: Introducing Java API QuickStart
description: null
seo-description: null
uuid: 46635283-3431-4a31-8b5f-9abbefbfcce5
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
topic-tags: development-tools
discoiquuid: 23ab3e6a-8095-4f27-8550-763c735a3bae
index: y
internal: n
snippet: y
---

# Introducing Java API QuickStart{#introducing-java-api-quickstart}

Adobe AEM Forms API Quick Start can help you accelerate your efforts to develop programs that interact with AEM Forms services. *Quick Start*s are complete programs that you can copy and paste into your own projects and use as a starting point. You can run a Quick Start to see how it behaves and modify it for your own needs.

AEM Forms operations can be performed using the AEM Forms strongly-typed API and the connection mode should be set to SOAP.

Java strongly-typed API Quick Start provides a listing of JAR files that are required to execute the Java application. Most Java Quick Starts are console application that run within `main`. However, the Forms Java strongly-typed API Quick Start is implemented as Java servlet that run within a web application.

The JAR file listing is located in a comment section located at the beginning of the Quick Start. For example, the following comment is located in an Output quick start and is a typical JAR file listing found in each Java Quick Start.

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-output-client.jar 
     * 2. adobe--client.jar 
     * 3. adobe-usermanager-client.jar 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/Adobe/Adobe_Experience_Manager_forms/SDK/client-libs/common 
     * 
     * The adobe-utilities.jar file is located in the following path: 
     * <install directory>/Adobe/Adobe_Experience_Manager_forms/SDK/client-libs/jboss 
     * 
     * The jboss-client.jar file is located in the following path: 
     * <install directory>/Adobe/Adobe_Experience_Manager_forms/jboss/bin/client 
     * 
     * If you want to invoke a remote AEM Forms instance and there is a 
     * firewall between the client application and AEM Forms, then it is  
     * recommended that you use the SOAP mode. When using the SOAP mode,  
     * you have to include additional JAR files located in the following  
     * path 
     * <install directory>/Adobe/Adobe_Experience_Manager_forms/SDK/client-libs/thirdparty 
     * 
     * For information about the SOAP  
     * mode and the additional JAR files that need to be included,  
     * see "Setting connection properties" in Programming  
     * with AEM Forms 
     * 
     * For complete details about the location of the AEM Forms JAR files,  
     * see "Including AEM Forms library files" in Programming  
     * with AEM Forms 
     */
```

## Multiple Services Quick Start {#multiple-services-quick-start}

Most Quick Starts located in *Programming with AEM Forms *invoke a specific service in order to perform an operation. However, some Quick Starts invoke multiple AEM Forms services in order to perform a given workflow. The following list provides Java quick starts that invoke more than one AEM Forms service:

[Quick Start (SOAP mode): Passing a document located in the AEM Forms Repository to the Output service using the Java API](/programming-with-aem-forms/output-service-java-api-quick#quick_start_soap_mode_passing_a_document_located_in_the_repository_to_the_output_service_using_the_java_api) (invokes the Repository and Output service)

[Quick Start (SOAP mode): Creating a PDF document based on fragments using the Java API](/programming-with-aem-forms/output-service-java-api-quick#quick_start_soap_mode_creating_a_pdf_document_based_on_fragments_using_the_java_api) (invokes the Assembler and Output service)

[Quick Start (SOAP mode): Creating PDF Documents with submitted XML data using the Java API](/programming-with-aem-forms/forms-service-api-quick-starts#quick_start_soap_mode_creating_pdf_documents_with_submitted_xml_data_using_the_java_api) (invokes the Forms, Output, and Document Management service)

[Quick Start (SOAP mode): Passing documents to the Forms Service using the Java API](/programming-with-aem-forms/forms-service-api-quick-starts#quick_start_soap_mode_passing_documents_to_the_forms_service_using_the_java_api) (invokes the Forms and Document Management service)

[Quick Start (SOAP mode): Digitally signing a XFA-based Form using the Java API](#unresolvedlink-lc-qs-signature-si.xml#ws624e3cba99b79e12e69a9941333732bac8-7fd0.2) (invokes the Forms and Signature service)

[Quick Start (SOAP mode): Managing roles and permissions using the Java API](/programming-with-aem-forms/user-manager-java-api-quick#quick_start_soap_mode_managing_roles_and_permissions_using_the_java_api) (invokes the DirectoryManager and the AuthorizationManager service )

[Quick Start (SOAP mode): Passing documents to the Output Service using the Java API](/programming-with-aem-forms/output-service-java-api-quick#quick_start_soap_mode_passing_documents_to_the_output_service_using_the_java_api) (invoke the Output and Document Management service)

>[!NOTE]
>
>Quick Start located in Programming with AEM Forms are based on AEM Forms being deployed on JBoss® Application Server and the Microsoft® Windows® operating system. However, if you are using another operating system, such as UNIX®, replace Windows-specific paths with paths that are supported by the applicable operating system. Likewise, if you are using another J2EE application server, ensure that you specify valid connection properties. (See [Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties).)

>[!NOTE]
>
>Most web service Quick Starts are written in C# and uses the .NET framework. However, you can create client application logic that is able to invoke AEM Forms services in any development environment that supports SOAP standards. (See [Invoking AEM Forms Using Web Services](/programming-with-aem-forms/invoking-aem-forms-using-web#invoking_aem_forms_using_web_services).)

