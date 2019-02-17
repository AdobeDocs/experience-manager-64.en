---
title: Creating a new AEM Mobile app using create wizard
seo-title: Creating a new AEM Mobile app using create wizard
description: AEM Mobile apps are based on a blueprint that defines a page structure and properties. Follow this page to learn about how to create a new app based on an app template.
seo-description: AEM Mobile apps are based on a blueprint that defines a page structure and properties. Follow this page to learn about how to create a new app based on an app template.
uuid: d0149e6e-baa3-4bc9-8f28-c8067a307bf1
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: authoring-adobe-phonegap-enterprise
discoiquuid: 7edc1e9f-3efe-4b02-93e9-4a60ce0395de
index: y
internal: n
snippet: y
---

# Creating a new AEM Mobile app using create wizard{#creating-a-new-aem-mobile-app-using-create-wizard}

>[!NOTE]
>
>Adobe recommends using the SPA Editor for projects that require single page application framework-based client-side rendering (e.g. React). [Learn more](../../sites/developing/using/spa-overview.md).

AEM Mobile apps are based on a blueprint that defines a page structure and properties. You can configure the following application properties:

* **Title:** The application title.
* **Destination Path:** The location in the repository where the application is stored. Leave the default to create a path based on the app name.  

* **Name:** The default value is the value of the Title property with space characters removed. The name is used within AEM to refer to the application, for example for the repository node that represents the application.
* **Description:** A description of the application.
* **Server URL:** The URL that provides Over-the-Air (OTA) content updates to the application. The default value is the publish server URL of the instance that is used to create an application (taken from the externalizer service). Note, this must be a publish server instance rather than an author, which requires authentication.

You can also provide an image file to use as the application thumbnail, select the PhoneGap Build configuration to use, and select the Mobile App analytics configuration to use. This image is only used as a thumbnail to represent your mobile application within the mobile apps console in Experience Manager.

Additional (and optional) tabs exist for build cloud service and integrating the Adobe Mobile Services SDK plug-in into your app.

* Build: Click manage configurations and set up your build.phonegap.com build service here. Then from the drop-down you will be able to select the newly created PhoneGap build cloud service.
* Analytics: Click manage configurations and set up your [Adobe Mobile Services SDK](https://marketing.adobe.com/developer/en_US/get-started/mobile/c-measuring-mobile-applications) cloud service. Then from the drop-down you will be able to select the newly created Mobile Service to integrate into your mobile app.

### Using App Templates {#using-app-templates}

App templates provide an easy way to leverage existing designs created by devlopers, used for the creation of new apps within AEM.

What is an app template? Think of it as a collection of page templates and components that represent a baseline or foundation of an app.   
When creating a new app based on the template of another app, you will get an app that has a starting point representative of the app in which it was created from.

You must have an existing mobile app template (or an app installed that has an app template) to make use of this feature.

The latest AEM Apps samples package includes an updated version of the Geometrixx app with an app template. Alternatively, you can install the [StarterKit](https://github.com/Adobe-Marketing-Cloud-Apps/aem-phonegap-starter-kit) which also provides a template.

Steps to creating a new app based on an app template:

1. Navigate to the AEM Mobile app catalog: &lt;*server-url*&gt;aem/apps.html/content/mobileapps
1. Select **Create** and then choose **App** as shown below

![](assets/chlimage_1-174.png)

Select an app template made available to you by an AEM developer. See [Structure of an AEM Mobile App](../../mobile/using/phonegap-structure-an-app.md) for developer assistance.

![](assets/chlimage_1-175.png)

Fill out your new app's details as needed including optionally changing its thumbnail image. These values can be edited later from the **Manage App** tile.

![](assets/chlimage_1-176.png) 

### The Next Steps {#the-next-steps}

See the following resources to learn more about other authoring roles:

* [The Manage App Tile](../../mobile/using/phonegap-app-details-tile.md)
* [Editing App Metadata](../../mobile/using/phonegap-editmetadata.md)
* [App Definitions](../../mobile/using/phonegap-app-definitions.md)
* [Import an Existing Hybrid App](../../mobile/using/phonegap-import-hybrid-app.md)
* [Content Services](/mobile/using/content-as-a-service)

### Additional Resources {#additional-resources}

To learn about the roles and responsibilities of an Administrator and Developer, see the resources below:

* [Developing for Adobe PhoneGap Enterprise with AEM](../../mobile/using/developing-in-phonegap.md)
* [Administering Content for Adobe PhoneGap Enterprise with AEM](../../mobile/using/administer-phonegap.md)

