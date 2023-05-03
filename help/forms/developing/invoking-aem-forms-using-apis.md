---
title: Invoking AEM Forms using APIs
seo-title: Invoking AEM Forms using APIs
description: Adobe Experience Manager Forms is J2EE-based enterprise software that consists of services that operate within a shared infrastructure. Learn how to use client applications to invoke AEM Forms programmatically using a Java API, web services, Remoting, and REST API. 
seo-description: Adobe Experience Manager Forms is J2EE-based enterprise software that consists of services that operate within a shared infrastructure. Learn how to use client applications to invoke AEM Forms programmatically using a Java API, web services, Remoting, and REST API.
uuid: d100e106-e508-4d3c-ba8c-b5fe13c9e2d6
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: development-tools, coding
discoiquuid: 1825e12c-0306-4e0a-9643-47ce1ce82132
role: Developer
exl-id: 6b60209f-aced-4698-97f1-b1a7782eef46
---
# Invoking AEM Forms using APIs {#invoking-aem-forms-using-apis}

>[!CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Forms is J2EE-based enterprise software that consists of services that operate within a shared infrastructure. Service operations typically consume or produce documents. By using AEM Forms, you can combine forms workflow with electronic forms, document security, and document generation in an integrated and cohesive set of services. These services can be accessed from inside and outside the firewall.

Client applications can programmatically invoke AEM Forms services using a Java API, web services, Remoting, and REST. Using administration console, you can configure a service to expose an endpoint that lets AEM Forms services by programmatically invoked. By default, most services are pre-configured to expose Remoting, Java, and web service endpoints.

Your business requirements determine which invocation method to use. For example, using the Java API, you can integrate AEM Forms functionality into your Java enterprise applications, such as Java Entity and Message beans. Likewise, you can integrate AEM Forms functionality into .NET projects (or other projects developed with development environments that support web service standards) using web services.

Services require a service container to run, similar to how Enterprise JavaBeans™ (EJBs) require a J2EE container. AEM Forms includes only one implementation of a service container. The service container is responsible for managing the lifetime of a service, including deploying it and ensuring that all requests are sent to the correct service. It also manages documents that a service consumes or produces.

>[!NOTE]
>
>Programming with AEM forms does not include information on how to invoke AEM Forms using Watched Folders or e-mail.
