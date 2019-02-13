---
title: Generate PDF Service Java API QuickStart(SOAP)
seo-title: Generate PDF Service Java API QuickStart(SOAP)
description: null
seo-description: null
uuid: 97254fae-6b46-40ae-a3cb-93f0b4a59d00
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 18a1d5a9-b005-4efa-9307-c2ce498efd2b
index: y
internal: n
snippet: y
---

# Generate PDF Service Java API QuickStart(SOAP){#generate-pdf-service-java-api-quickstart-soap}

Java API Quick Start(SOAP) is available for the Generate PDF service.

[Quick Start (SOAP mode): Converting a Microsoft Word document to a PDF document using the Java API](generate-pdf-service-java-api#quick_start_soap_mode_converting_a_microsoft_word_document_to_a_pdf_document_using_the_java_api)

[Quick Start (SOAP mode): Converting HTML content to a PDF document using the Java API](generate-pdf-service-java-api#quick_start_soap_mode_converting_html_content_to_a_pdf_document_using_the_java_api)

[Quick Start (SOAP mode): Converting a PDF document to an RTF file using the Java API (SOAP mode)](generate-pdf-service-java-api#quick_start_soap_mode_converting_a_pdf_document_to_an_rtf_file_using_the_java_api_soap_mode)

AEM Forms operations can be performed using the AEM Forms strongly-typed API and the connection mode should be set to SOAP.

***Note**: Quick Start located in Programming with AEM Forms are based on the Forms Server being deployed on JBoss Application Server and the Microsoft Windows operating system. However, if you are using another operating system, such as UNIX, replace Windows-specific paths with paths that are supported by the applicable operating system. Likewise, if you are using another J2EE application server, ensure that you specify valid connection properties. (See [Setting connection properties](/programming-with-aem-forms/invoking-aem-forms-using-java#setting_connection_properties).)*

## Quick Start (SOAP mode): Converting a Microsoft Word document to a PDF document using the Java API {#quick-start-soap-mode-converting-a-microsoft-word-document-to-a-pdf-document-using-the-java-api}

The following code example converts a Word file named *Loan.doc* to a PDF document named *Loan.pdf*. (See [Converting Word Documents to PDF Documents](/programming-with-aem-forms/converting-file-formats-pdf#converting_word_documents_to_pdf_documents).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-generatepdf-client.jar 
     * 2. adobe-livecycle-client.jar 
     * 3. adobe-usermanager-client.jar 
     * 4. adobe-utilities.jar 
     * 5. jboss-client.jar (use a different JAR file if the forms server is not deployed 
     * on JBoss) 
     * 6. activation.jar (required for SOAP mode) 
     * 7. axis.jar (required for SOAP mode) 
     * 8. commons-codec-1.3.jar (required for SOAP mode) 
     * 9.  commons-collections-3.1.jar  (required for SOAP mode) 
     * 10. commons-discovery.jar (required for SOAP mode) 
     * 11. commons-logging.jar (required for SOAP mode) 
     * 12. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
     * 13. jaxen-1.1-beta-9.jar (required for SOAP mode) 
     * 14. jaxrpc.jar (required for SOAP mode) 
     * 15. log4j.jar (required for SOAP mode) 
     * 16. mail.jar (required for SOAP mode) 
     * 17. saaj.jar (required for SOAP mode) 
     * 18. wsdl4j.jar (required for SOAP mode) 
     * 19. xalan.jar (required for SOAP mode) 
     * 20. xbean.jar (required for SOAP mode) 
     * 21. xercesImpl.jar (required for SOAP mode) 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * The adobe-utilities.jar file is located in the following path: 
     * <install directory>/sdk/client-libs/jboss 
     * 
     * The jboss-client.jar file is located in the following path: 
     * <install directory>/jboss/bin/client 
     * 
     * SOAP required JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/thirdparty 
     * 
     * If you want to invoke a remote forms server instance and there is a 
     * firewall between the client application and the server, then it is  
     * recommended that you use the SOAP mode. When using the SOAP mode,  
     * you have to include these additional JAR files 
     * 
     * For information about the SOAP  
     * mode, see "Setting connection properties" in Programming  
     * with AEM Forms 
     */ 
 import java.io.File; 
 import java.io.FileInputStream; 
 import java.util.Properties; 
  
 import com.adobe.idp.Document; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.generatepdf.client.CreatePDFResult; 
 import com.adobe.livecycle.generatepdf.client.GeneratePdfServiceClient; 
  
 public class ConvertWordDocumentSOAP { 
  
     public static void main(String[] args) 
     { 
         try{ 
         //Set connection properties required to invoke AEM Forms using SOAP mode                                 
         Properties connectionProps = new Properties(); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "http://[server]:[port]"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
          
         //Create a ServiceClientFactory instance 
         ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
                  
         //Create a GeneratePdfServiceClient object 
         GeneratePdfServiceClient pdfGenClient = new GeneratePdfServiceClient(myFactory); 
          
         //Get a Microsoft Word file document to convert to a PDF document 
         String inputFileName = "C:\\Adobe\\Loan.doc"; 
         FileInputStream fileInputStream = new FileInputStream(inputFileName); 
         Document inDoc = new Document(fileInputStream); 
          
         //Set createPDF2 parameter values 
         String adobePDFSettings = "Smallest_File_Size"; 
          String securitySettings = "No Security"; 
          String fileTypeSettings = "Filetype Settings"; 
           
          //Convert the Word document to a PDF document 
          CreatePDFResult result = pdfGenClient.createPDF2( 
             inDoc, 
             inputFileName, 
             fileTypeSettings, 
             adobePDFSettings, 
             securitySettings, 
             null, 
             null); 
               
          //Get the newly created document 
          Document createdDocument = result.getCreatedDocument(); 
               
          //Save the converted PDF document as a PDF file 
         createdDocument.copyToFile(new File("C:\\Adobe\\Loan.pdf")); 
     } 
     catch (Exception e) { 
         System.out.println("Error OCCURRED: " + e.getMessage()); 
         } 
     } 
 }
```

## Quick Start (SOAP mode): Converting HTML content to a PDF document using the Java API {#quick-start-soap-mode-converting-html-content-to-a-pdf-document-using-the-java-api}

The following Java code example converts HTML content located at http://www.adobe.com to a PDF document named *AdobeHTML.pdf*. (See [Converting HTML Documents to PDF Documents](/programming-with-aem-forms/converting-file-formats-pdf#converting_html_documents_to_pdf_documents).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-generatepdf-client.jar 
     * 2. adobe-livecycle-client.jar 
     * 3. adobe-usermanager-client.jar 
     * 4. adobe-utilities.jar 
     * 5. jboss-client.jar (use a different JAR file if the forms server is not deployed 
     * on JBoss) 
     * 6. activation.jar (required for SOAP mode) 
     * 7. axis.jar (required for SOAP mode) 
     * 8. commons-codec-1.3.jar (required for SOAP mode) 
     * 9.  commons-collections-3.1.jar  (required for SOAP mode) 
     * 10. commons-discovery.jar (required for SOAP mode) 
     * 11. commons-logging.jar (required for SOAP mode) 
     * 12. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
     * 13. jaxen-1.1-beta-9.jar (required for SOAP mode) 
     * 14. jaxrpc.jar (required for SOAP mode) 
     * 15. log4j.jar (required for SOAP mode) 
     * 16. mail.jar (required for SOAP mode) 
     * 17. saaj.jar (required for SOAP mode) 
     * 18. wsdl4j.jar (required for SOAP mode) 
     * 19. xalan.jar (required for SOAP mode) 
     * 20. xbean.jar (required for SOAP mode) 
     * 21. xercesImpl.jar (required for SOAP mode) 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * The adobe-utilities.jar file is located in the following path: 
     * <install directory>/sdk/client-libs/jboss 
     * 
     * The jboss-client.jar file is located in the following path: 
     * <install directory>/jboss/bin/client 
     * 
     * SOAP required JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/thirdparty 
     * 
     * If you want to invoke a remote forms server instance and there is a 
     * firewall between the client application and the server, then it is  
     * recommended that you use the SOAP mode. When using the SOAP mode,  
     * you have to include these additional JAR files 
     * 
     * For information about the SOAP  
     * mode, see "Setting connection properties" in Programming  
     * with AEM Forms 
     */ 
 import java.io.File; 
 import java.util.Properties; 
 import com.adobe.idp.Document; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.generatepdf.client.GeneratePdfServiceClient; 
 import com.adobe.livecycle.generatepdf.client.HtmlToPdfResult; 
  
 public class ConvertHTMLSOAP { 
  
     public static void main(String[] args) 
     { 
         try{ 
         //Set connection properties required to invoke AEM Forms using SOAP mode                                 
         Properties connectionProps = new Properties(); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "http://[server]:[port]"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
         connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
              
         //Create a ServiceClientFactory instance 
         ServiceClientFactory myFactory = ServiceClientFactory.createInstance(connectionProps); 
          
         //Create a GeneratePdfServiceClient object 
         GeneratePdfServiceClient pdfGenClient = new GeneratePdfServiceClient(myFactory); 
          
         //Get an HTML document to convert to a PDF document a 
         String inputFileName = "http://www.adobe.com"; 
          
          String securitySettings = "No Security"; 
         String fileTypeSettings = "Standard"; 
           
          //Convert HTML content to a PDF document 
          HtmlToPdfResult result = pdfGenClient.htmlToPDF2( 
                  inputFileName, 
                  fileTypeSettings, 
                  securitySettings, 
                  null, 
                 null); 
               
          //Get the newly created document 
          Document createdDocument = result.getCreatedDocument(); 
           
          //Save the PDF document as a PDF file 
         createdDocument.copyToFile(new File("C:\\AdobeHTML.pdf")); 
     } 
     catch (Exception e) { 
         System.out.println("Error OCCURRED: " + e.getMessage()); 
     } 
     } 
 }
```

## Quick Start (SOAP mode): Converting a PDF document to an RTF file using the Java API (SOAP mode) {#quick-start-soap-mode-converting-a-pdf-document-to-an-rtf-file-using-the-java-api-soap-mode}

The following code example converts a PDF document named *Loan.pdf* to an RTF document named *Loan.rtf*. (See [Converting PDF Documents to Non-image Formats](/programming-with-aem-forms/converting-file-formats-pdf#converting_pdf_documents_to_non_image_formats).)

```as3
 /* 
     * This Java Quick Start uses the SOAP mode and contains the following JAR files 
     * in the class path: 
     * 1. adobe-generatepdf-client.jar 
     * 2. adobe-livecycle-client.jar 
     * 3. adobe-usermanager-client.jar 
     * 4. adobe-utilities.jar 
     * 5. jboss-client.jar (use a different JAR file if the forms server is not deployed 
     * on JBoss) 
     * 6. activation.jar (required for SOAP mode) 
     * 7. axis.jar (required for SOAP mode) 
     * 8. commons-codec-1.3.jar (required for SOAP mode) 
     * 9.  commons-collections-3.1.jar  (required for SOAP mode) 
     * 10. commons-discovery.jar (required for SOAP mode) 
     * 11. commons-logging.jar (required for SOAP mode) 
     * 12. dom3-xml-apis-2.5.0.jar (required for SOAP mode) 
     * 13. jaxen-1.1-beta-9.jar (required for SOAP mode) 
     * 14. jaxrpc.jar (required for SOAP mode) 
     * 15. log4j.jar (required for SOAP mode) 
     * 16. mail.jar (required for SOAP mode) 
     * 17. saaj.jar (required for SOAP mode) 
     * 18. wsdl4j.jar (required for SOAP mode) 
     * 19. xalan.jar (required for SOAP mode) 
     * 20. xbean.jar (required for SOAP mode) 
     * 21. xercesImpl.jar (required for SOAP mode) 
     * 
     * These JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/common 
     * 
     * The adobe-utilities.jar file is located in the following path: 
     * <install directory>/sdk/client-libs/jboss 
     * 
     * The jboss-client.jar file is located in the following path: 
     * <install directory>/jboss/bin/client 
     * 
     * SOAP required JAR files are located in the following path: 
     * <install directory>/sdk/client-libs/thirdparty 
     * 
     * If you want to invoke a remote forms server instance and there is a 
     * firewall between the client application and the server, then it is  
     * recommended that you use the SOAP mode. When using the SOAP mode,  
     * you have to include these additional JAR files 
     * 
     * For information about the SOAP  
     * mode, see "Setting connection properties" in Programming  
     * with AEM Forms 
     */ 
 import java.io.File; 
 import java.io.FileInputStream; 
 import java.util.Properties; 
 import com.adobe.idp.Document; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactory; 
 import com.adobe.idp.dsc.clientsdk.ServiceClientFactoryProperties; 
 import com.adobe.livecycle.generatepdf.client.ConvertPDFFormatType; 
 import com.adobe.livecycle.generatepdf.client.ExportPDFResult; 
 import com.adobe.livecycle.generatepdf.client.GeneratePdfServiceClient; 
  
  
 public class GeneratePdf_ExportPDFSOAP { 
  
     public static void main(String[] args) 
     { 
         try{ 
             //Set connection properties required to invoke AEM Forms using SOAP mode                                 
             Properties connectionProps = new Properties(); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_DEFAULT_SOAP_ENDPOINT, "http://[server]:[port]"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_TRANSPORT_PROTOCOL,ServiceClientFactoryProperties.DSC_SOAP_PROTOCOL);           
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_SERVER_TYPE, "JBoss"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_USERNAME, "administrator"); 
             connectionProps.setProperty(ServiceClientFactoryProperties.DSC_CREDENTIAL_PASSWORD, "password"); 
                  
             //Create a ServiceClientFactory instance 
             ServiceClientFactory factory = ServiceClientFactory.createInstance(connectionProps); 
          
             //Create a GeneratePdfServiceClient object 
             GeneratePdfServiceClient pdfGenClient = new GeneratePdfServiceClient(factory); 
           
             //Get a PDF document to convert to an RTF document 
             String inputFileName = "C:\\Adobe\\Loan.pdf.pdf"; 
             FileInputStream fileInputStream = new FileInputStream(inputFileName); 
             Document inDoc = new Document(fileInputStream); 
              
             //Convert a PDF document to a RTF document 
             ExportPDFResult result = pdfGenClient.exportPDF2( 
                 inDoc, 
                 inputFileName, 
                 ConvertPDFFormatType.RTF, 
                 null); 
               
          //Get the newly created RTF document 
          Document createdDocument = result.getConvertedDocument(); 
               
          //Save the RTF file 
         createdDocument.copyToFile(new File("C:\\Adobe\\Loan.pdf.rtf")); 
         } 
         catch (Exception e) { 
             System.out.println("Error OCCURRED: " + e.getMessage()); 
         } 
     } 
 }
```

