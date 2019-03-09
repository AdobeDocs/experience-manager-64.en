---
title: Programmatically managing the PreferencesNodes
seo-title: Programmatically managing the PreferencesNodes
description: null
seo-description: null
uuid: eb5a775c-f3e4-47a7-9934-936ececc06ab
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: operations
discoiquuid: bbaa9c10-25d9-4481-8e4c-7a5a36298dd9
---

# Programmatically managing the PreferencesNodes{#programmatically-managing-the-preferencesnodes}

This topic describes how you can use the Preferences Manager Service API (Java) to programmatically manage the Preferences Nodes.

You can manually change configuration settings from Administrator UI. To change the options, navigate to `Home>Settings>User Management> Configuration>Manual Configuration`. Import `config.xml` after making the changes, you would notice that all the changes except changes made at node `/Adobe/Adobe Experience Manager Forms/Config/UM persist` are lost. The preview of User Management Import and export does not support changing configuration settings for other components. Now, these changes can be made using `PreferencesManagerServiceClient` APIs.

**Summary of steps**To programmatically manage the Preferences Nodes, perform the following steps:

1. Include project files. 
1. Create an PreferencesManagerService client
1. Invoke the appropriate role or permission operations

**Include project files**

Include necessary files in your development project. If you are creating a client application using Java, then include the necessary JAR files. If you are using web services, then make sure that you include the proxy files.

**Create an PreferencesManagerService client**

Before you can programmatically perform a User Management PreferencesManagerService operation, you must create a PreferencesManagerService client. With the Java API this is accomplished by creating an PreferencesManagerServiceClient object.

**Invoke the appropriate role or permission operations**

Once you have created the service client, you can then invoke the Preferences Manager operations. The service client allows you to read and set permissions.
