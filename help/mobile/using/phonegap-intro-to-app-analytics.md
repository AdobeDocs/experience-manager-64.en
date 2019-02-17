---
title: Track App Performance with Adobe Mobile Analytics
seo-title: Track App Performance with Adobe Mobile Analytics
description: With Adobe Mobile Services you can gain insight on how your users are using your mobile apps by tracking usage, app crashes, device details and so many other critical metrics for your mobile apps. Follow this page to learn more.
seo-description: With Adobe Mobile Services you can gain insight on how your users are using your mobile apps by tracking usage, app crashes, device details and so many other critical metrics for your mobile apps. Follow this page to learn more.
uuid: 550aec12-754f-4fff-8486-92c8a154980b
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: developing-adobe-phonegap-enterprise
discoiquuid: 91b4baf8-4f6d-46a1-afd3-68fbbac5b526
index: y
internal: n
snippet: y
---

# Track App Performance with Adobe Mobile Analytics{#track-app-performance-with-adobe-mobile-analytics}

>[!NOTE]
>
>Adobe recommends using the SPA Editor for projects that require single page application framework-based client-side rendering (e.g. React). [Learn more](../../sites/developing/using/spa-overview.md).

You want to drive higher customer conversions and loyalty.

You want to deliver relevent and engaging experiences to your customers.

What is your AEM Mobile app doing for your marketing campaigns?

How can you fine tune your mobile applications to provide the best experience for your users?

With Adobe Mobile Services you can gain insight on how your users are using your mobile apps by tracking usage, app crashes, device details and so many other critical metrics for your mobile apps.

Adobe Experience Manager Mobile provides a glimpse into the details of your mobile analytics directly from the AEM Mobile Application Dashboard. The **Mobile Metrics Tile** in the dashboard provides real-time analytics for your mobile application, allowing developers, authors and administrators to get a quick glipse of the health of your mobile app. Under the covers powering the analytics is the [Adobe Mobile Analytics](http://www.adobe.com/ca/solutions/digital-analytics/mobile-web-apps-analytics.html) SDK. The Adobe Mobile Analytics SDK can be plugged into your applications natively or through a PhoneGap bridge plug-in for webviews. Metrics are collected and cached on the device until the device is connected, at which the data is pushed to the Adobe Mobile Services Cloud for reporting and analysis.

Adobe Mobile Analytics SDK provides the following:

1. **Data collection for mobile channels** - Collect comprehensive data for your mobile websites and apps on all major operating systems.
1. **Mobile engagement analysis** - Understand user engagement within your mobile app, website, or video, including how frequently consumers launch the channel, whether they make purchases from it, and more.
1. **Mobile app dashboards and reports** - Get usage reports that include lifecycle metrics for your apps and app store metrics — see trends for users, launches, average session length, retention length, and crashes.
1. **Mobile campaign analysis** - Quantify the effectiveness of mobile-specific campaigns such as SMS, mobile search ads, mobile display ads, and QR codes.
1. **Geolocation analysis** - Find where your app users launch and interact with your mobile experiences by GPS location or points of interest.
1. **Pathing analysis** - See how users navigate through your app to determine which screens and UI elements are engaging users and which cause users to drop off.

This section describes how [AEM Developers](#developers) can then learn how to instrument AEM Mobile apps with analytics tracking.

Finally, [AEM Administrators](#administrators)* *learn to:

* create a cloud service to Adobe Mobile Services
* create a mobile service config and associate a report suite
* associate the mobile service config to a mobile app
* view metrics via the AEM Apps Command Center
* assign the AMS SDK Config to your mobile app

## For Developers - Integrate Analytics into your App {#for-developers-integrate-analytics-into-your-app}

**Prerequisite:** AEM administrators need to configure the Adobe Mobile Services cloud config, [as discussed below](#amscloudserviceconfig).

Developers are responsible for [adding analytics to an AEM Mobile app](/content/docs/en/aem/6-3/develop/mobile-apps/apps/add-analytics-to-apps) as necessary to track, report and understand how you users engage with your mobile app content and to measure key lifecycle metrics such as launches, time in app, and crash rate.

## For Administrators - Configure the Adobe Mobile Services Cloud Service {#for-administrators-configure-the-adobe-mobile-services-cloud-service}

In order to take advantage of Adobe Mobile Services you need to configure the AEM Adobe Mobile Services Cloud Service with your Adobe Analytics account information. The Apps Command Center provides a **Analyze Metrics** tile where you can create and associate the cloud service with your mobile app.

Configure the cloud service to your mobile app begins by clicking the gear icon located on the Analyze Metrics tile.

![](assets/chlimage_1-130.png)

Clicking the gear icon in the Analyze Metrics tile will open the 'Configure Mobile Services Analytics' modal dialog. Select your configuration from the 'Select a Mobile Service Configuration' drop-down. If you need to create a new configuration, click the wrench button.

To create a Adobe Mobile Service cloud service there are two steps involved, the connection to the service and selecting what reporting suite to assign to the configuration.

To begin, click on the '+' button on the Manage Cloud Services tile in the dashboard.

![](assets/chlimage_1-131.png)

Upon clicking the '**+**' button, the **Add Cloud Service **wizard will be displayed.

![](assets/chlimage_1-132.png)

Select or create a new mobile service configuration by filling required fields as shown below. Your AEM administrator will require this information to successfully create the connection to Adobe Mobile Services.

![](assets/chlimage_1-133.png)

Once you've completed the Mobile Services Account Settings, you will be prompted to select an app. Doing so connects Adobe Mobile Service analytics reporting to that application.

Select the desired mobile service, and click 'Update' to assign the mobile service configuration and close the dialog.

Now that you have associated the mobile service config to the AEM Mobile app the tile will start to fetch the metric data and begin reporting.

![](assets/chlimage_1-134.png)

### Adobe Mobile Services SDK Config File {#adobe-mobile-services-sdk-config-file}

At this point your mobile application is associated with a cloud service, however the mobile application does not yet know how to communicate the collected mobile metrics back to Adobe Analytics. To wire up the mobile app to Adobe Analytics, the Adobe Mobile Services SDK Config file needs to be added to Adobe Experience Manager.

From the Analyze Metrics tile, click on the arrow icon to expose the Download / Upload AMS SDK Config menu entries.

![](assets/chlimage_1-135.png)

The first step is to obtain the SDK Config from Adobe Mobile Services, clicking on the 'Download AMS SDK Config' will redirect you to the Adobe Mobile Services website where you can download the config file from. Once you have obtained the ADBMobileConfig.json file, click on the "Upload AMS SDK Config" to upload the config file into AEM.

![](assets/chlimage_1-136.png)

Click the 'Upload Adobe Mobile Services Application Config' button and browse for the ADBMobileConfig.json file, then click 'Upload'.

Now that the mobile app has access to the ADBMobileConfig.json file it has the knowledge on how to communicate back to Adobe Analytics and begin reporting on those important metrics value that will help drive your apps success.

## What's Next? {#what-s-next}

1. [Start my AEM Mobile app experience](/content/docs/en/aem/6-3/develop/mobile-apps/starting-a-new-aem-mobile-app)
1. [Manage my app's content](/content/docs/en/aem/6-3/develop/mobile-apps/manage-my-apps-content)
1. [Build my application](/content/docs/en/aem/6-3/author/authoring-mobile-apps/build-app-through-adobe-phonegap-build-cloud-service)
1. [Track my app's performance with Adobe Mobile Analytics](../../mobile/using/phonegap-intro-to-app-analytics.md)
1. 

   ##### [Deliver a personalized app experience with Adobe Target](/content/docs/en/aem/6-3/develop/mobile-apps/apps/aem-mobile-content-personalization) {#deliver-a-personalized-app-experience-with-adobe-target}

1. [Send important messages to my users](/content/docs/en/aem/6-3/develop/mobile-apps/apps/push-notifications)

