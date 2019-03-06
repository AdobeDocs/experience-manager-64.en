---
title: Overview of configuring SSL
seo-title: Overview of configuring SSL
description: Learn about how to enhance security of communication by configuring SSL.
seo-description: Learn about how to enhance security of communication by configuring SSL.
uuid: e3f8dea9-726f-4d77-a558-99c429019490
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_ssl
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 1de91120-5d51-4f6c-afb3-42a8b27f1632
index: y
internal: n
snippet: y
---

# Overview of configuring SSL{#overview-of-configuring-ssl}

You can create Secure Sockets Layer (SSL) credentials and configure SSL on the application server to enhance the security of communication with your application server.

As a security product, Rights Management requires the configuration of SSL. When configuring SSL certificates, ensure that you use only RSA keys. SSL Certificates with DSA keys are not supported.

The information provided applies to turnkey, automatic, and manual installations. It offers an example of a method for configuring SSL. You can also use other methods that are more appropriate for your network or organization.

>[!NOTE]
>
>It is recommended that you complete the installation, configuration, and deployment of your AEM forms modules and ensure that the products are running correctly before you configure SSL on the application server.

>[!NOTE]
>
>When creating SSL security certificates and credentials, use the same user account privileges as you used to run the application server. If the application server is run by using other user privileges, the form may not render properly for PDFForm renditions when the ContentRootURI points to https.

If you have an SSL-enabled LDAP server, configure User Management to work with it. (See [Configure User Management for an SSL-enabled LDAP server](../../../forms/using/admin-help/configure-user-management-ssl-enabled.md#configure-user-management-for-an-ssl-enabled-ldap-server).)
