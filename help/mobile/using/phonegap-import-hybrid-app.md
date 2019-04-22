---
title: Import an existing hybrid app
seo-title: Import an existing hybrid app
description: A sample app has been created that demonstrates all of the new features in AEM Mobile to support migrating an existing PhoneGap app into AEM as well as valid app structure.
seo-description: A sample app has been created that demonstrates all of the new features in AEM Mobile to support migrating an existing PhoneGap app into AEM as well as valid app structure.
uuid: adf6c737-4510-45fe-b985-e0242f8c68f0
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: authoring-adobe-phonegap-enterprise
discoiquuid: 4003bf11-ccaf-403e-9414-3bcfb161cf5e
redirecttarget: /content/help/en/experience-manager/6-4/mobile/using/phonegap-adding-content-to-imported-app
---

# Import an existing hybrid app{#import-an-existing-hybrid-app}

>[!NOTE]
>
>Adobe recommends using the SPA Editor for projects that require single page application framework-based client-side rendering (e.g. React). [Learn more](/help/sites/developing/using/spa-overview.md).

## The Hybrid App Sample {#the-hybrid-app-sample}

A [sample app](https://github.com/Adobe-Marketing-Cloud-Apps/aem-mobile-hybrid-reference) has been created that demonstrates all of the new features in AEM Mobile to support migrating an existing PhoneGap app into AEM as well as valid app structure.

## Importing a Hybrid App {#importing-a-hybrid-app}

This feature is great for bootstrapping an app in AEM and for demos. Proper AEM package management techniques should still be used before moving an app to production. Any existing PhoneGap app that has been zipped up can be imported into AEM Mobile.

The import process is fully automated and takes care of copying the content to the correct location and setting up the correct app instance properties. A new app will also be created if an existing one cannot be found. An existing app will need to have an **app-assets** handler already but this handler will be included with new apps.

Dragging the zipped app onto the AEM Mobile apps catalog will automatically start the import process as shown below.

![](assets/chlimage_1-37.png)

## The Next Steps {#the-next-steps}

See the following resources to learn more about other authoring roles:

* [The Manage App Tile](/help/mobile/using/phonegap-app-details-tile.md)
* [Editing App Metadata](/help/mobile/using/phonegap-editmetadata.md)
* [App Definitions](/help/mobile/using/phonegap-app-definitions.md)
* [Creating a New App using Create App Wizard](/help/mobile/using/phonegap-create-new-app.md)
* [Content Services](/mobile/using/content-as-a-service.md) [](/mobile/using/content-as-a-service.md)

### Additional Resources {#additional-resources}

To learn about the roles and responsibilities of an Administrator and Developer, see the resources below:

* [Developing for Adobe PhoneGap Enterprise with AEM](/help/mobile/using/developing-in-phonegap.md)
* [Administering Content for Adobe PhoneGap Enterprise with AEM](/help/mobile/using/administer-phonegap.md)