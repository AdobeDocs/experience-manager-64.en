---
title: Invoking AEM Forms using APIs
seo-title: Invoking AEM Forms using APIs
description: null
seo-description: null
uuid: 384001a3-d7e8-47b0-836d-3946c30eb969
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: coding
topic-tags: development-tools
discoiquuid: 0c86a9f6-48e6-42a5-8a1f-d107a76e15b7
index: y
internal: n
snippet: y
---

# Invoking AEM Forms using APIs{#invoking-aem-forms-using-apis}

Adobe Experience Manager Forms is J2EE-based enterprise software that consists of services that operate within a shared infrastructure. Service operations typically consume or produce documents. By using AEM Forms, you can combine forms workflow with electronic forms, document security, and document generation in an integrated and cohesive set of services. These services can be accessed from inside and outside the firewall.

Client applications can programmatically invoke AEM Forms services using a Java API, web services, Remoting, and REST. Using administration console, you can configure a service to expose an endpoint that lets AEM Forms services by programmatically invoked. By default, most services are pre-configured to expose Remoting, Java, and web service endpoints.

Your business requirements determine which invocation method to use. For example, using the Java API, you can integrate AEM Forms functionality into your Java enterprise applications, such as Java Entity and Message beans. Likewise, you can integrate AEM Forms functionality into .NET projects (or other projects developed with development environments that support web service standards) using web services.

Services require a service container to run, similar to how Enterprise JavaBeans™ (EJBs) require a J2EE container. AEM Forms includes only one implementation of a service container. The service container is responsible for managing the lifetime of a service, including deploying it and ensuring that all requests are sent to the correct service. It also manages documents that a service consumes or produces.

>[!NOTE]
>
>Programming with AEM forms does not include information on how to invoke AEM Forms using Watched Folders or e-mail.

