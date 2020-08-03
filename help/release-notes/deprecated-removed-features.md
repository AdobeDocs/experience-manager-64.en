---
title: Deprecated and Removed Features
description: Release notes specific to deprecated and removed features in Adobe Experience Manager 6.4.
---

# Deprecated and Removed Features {#deprecated-and-removed-features}

Adobe constantly evaluates product capabilities, to over time reinvent or replace older features with more modern alternatives to improve overall customer value, always under careful consideration of backward compatibility.

To communicate the impending removal/replacement of AEM capabilities, the following rules apply:

1. Announcement of deprecation comes first. While deprecated, capabilities are still available, but they will not be further enhanced. 
1. Removal of deprecated capabilities will occur in the following major release at the earliest. Actual target date for removal will be announced.

This process gives customers at least one release cycle to adapt their implementation to a new version or successor of a deprecated capability, before actual removal.

## Deprecated Features {#deprecated-features}

The table below lists features and capabilities that have been marked as deprecated with AEM 6.4. Generally, features that are planned to be removed in a future release are set to deprecated first, with an alternative provided.

Customers are advised to review if they make use of the feature/capability in their current deployment, and make plans to change their implementation to use the alternative provided.

<!-- TBD: This MD table is a replacement of the HTML table below. However, it generates validation error hence commenting and replacing with inline text. Restore if required. -->

|Area|Feature|Replacement|
|---|---|---|
| UI | Adobe does not plan to make further enhancements to the Classic UI. AEM 6.4 has the Classic UI included, and customers upgrading from earlier releases can keep using it as is. Note that Classic UI remains fully supported while being deprecated. <li>`/libs/cq/core/content/welcome.html` </li> <li> `/siteadmin` </li> <li> `/damadmin` </li> <li> `/mcmadmin` </li> <li> `/inbox` </li> <li> `/tagging` </li> <li> `/cf#` (Page Editor) </li><li> `/libs/launches/content/admin.html` </li> <li> `/libs/cq/workflow/content/console.html` </li> | Customers are advised to switch to use the new AEM UI. |
| Components | Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated. <li> foundation/components/account/accountname </li> <li> foundation/components/account/actions </li> <li> foundation/components/account/passwordreset </li> <li> foundation/components/account/requestconfirmation </li> <li> foundation/components/adaptiveimage </li> <li> foundation/components/assetsharepage </li> <li> foundation/components/breadcrumb </li> <li> foundation/components/form/creditcard </li> <li> foundation/components/listchildren </li> <li> foundation/components/login </li> <li> foundation/components/logo </li> <li> foundation/components/mobilefooter </li> <li> foundation/components/mobileimage </li> <li> foundation/components/mobilelist </li> <li> foundation/components/mobilelogo </li> <li> foundation/components/mobilereference </li> <li> foundation/components/mobiletextimage </li> <li> foundation/components/mobiletopnav </li> <li> foundation/components/search </li> <li> foundation/components/sitemap </li> <li> foundation/components/table </li> <li> foundation/components/toolbar </li> <li> foundation/components/topnav </li> <li> foundation/components/userinfo </li> | Customers are advised to use the Core Components for future projects. Existing sites do not need to be changed. |
| Components | Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated. <li>foundation/components/timing</li> | Adobe does not plan to provide a replacement. |
| Portal Director  | The Portal Director is a set of features, that enables the hosting of AEM content via Portlet in 3rd party servers. Adobe does not plan to make further enhancements to the Portal Director feature under the location listed below. AEM 6.4 has the Portal Director included, and customers upgrading from earlier releases can keep using it as is. Note that Portal Direct remains fully supported while being deprecated.<li>/libs/portal/director</li> | Adobe does not plan to provide a replacement. |
| Portlet Component | Portlet Components under /foundation/components/portlet enables the hosting of JSR Portlets in AEM as components. Adobe does not plan to make further enhancements to the Portlet Component feature. AEM 6.4 has the Portlet Component included, and customers upgrading from earlier releases can keep using it as is. Note that Portlet Component remains fully supported while being deprecated. | Adobe does not plan to provide a replacement. |
| Forms | Support for Adobe Central Migration Bridge service has been deprecated as Adobe Central product is no longer supported. | No replacement |
| Forms | Deprecated use of JSONObject in Query and OperationOptions. The following APIs are deprecated: <li>`setArguments(JSONObject arguments)`</li><li> `JSONObject getArguments()`</li><li>`OperationOptions(String operationId, JSONObject arguments)`</li><li>`JSONObject getArguments()`</li><li> `void setArguments(JSONObject arguments)`</li> | Use the `IValueMap` API|
|Forms|Deprecated Central Migration Bridge service.|No replacement is offered.|
|Assets|Assets Offloading has been deprecated starting with AEM 6.4.||

<!-- Original HTML table that came from helpx during migration.

<table> 
 <tbody>
  <tr>
   <td>Area</td> 
   <td>Feature</td> 
   <td>Replacement</td> 
  </tr>
  <tr>
   <td>UI</td> 
   <td><p>Adobe does not plan to make further enhancements to the Classic UI. AEM 6.4 has the Classic UI included, and customers upgrading from earlier releases can keep using it as is. Note that Classic UI remains fully supported while being deprecated. </p> 
    <ul> 
     <li>/libs/cq/core/content/welcome.html</li> 
     <li>/siteadmin</li> 
     <li>/damadmin</li> 
     <li>/mcmadmin</li> 
     <li>/inbox</li> 
     <li>/tagging</li> 
     <li>/cf# (Page Editor)</li> 
     <li>/libs/launches/content/admin.html</li> 
     <li>/libs/cq/workflow/content/console.html</li> 
    </ul> </td> 
   <td><p>Customers are advised to switch to use the new AEM UI.</p> <p> </p> </td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td><p>Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated. </p> 
    <ul> 
     <li>foundation/components/account/accountname</li> 
     <li>foundation/components/account/actions</li> 
     <li>foundation/components/account/passwordreset</li> 
     <li>foundation/components/account/requestconfirmation</li> 
     <li>foundation/components/adaptiveimage</li> 
     <li>foundation/components/assetsharepage</li> 
     <li>foundation/components/breadcrumb</li> 
     <li>foundation/components/form/creditcard</li> 
     <li>foundation/components/listchildren</li> 
     <li>foundation/components/login</li> 
     <li>foundation/components/logo</li> 
     <li>foundation/components/mobilefooter</li> 
     <li>foundation/components/mobileimage</li> 
     <li>foundation/components/mobilelist</li> 
     <li>foundation/components/mobilelogo</li> 
     <li>foundation/components/mobilereference</li> 
     <li>foundation/components/mobiletextimage</li> 
     <li>foundation/components/mobiletopnav</li> 
     <li>foundation/components/search</li> 
     <li>foundation/components/sitemap</li> 
     <li>foundation/components/table</li> 
     <li>foundation/components/toolbar</li> 
     <li>foundation/components/topnav</li> 
     <li>foundation/components/userinfo</li> 
    </ul> </td> 
   <td>Customers are advised to use the Core Components for future projects. Existing sites do not need to be changed.</td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td><p>Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated.</p> 
    <ul> 
     <li>foundation/components/timing</li> 
    </ul> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Portal Director</td> 
   <td><p>The Portal Director is a set of features, that enables the hosting of AEM content via Portlet in 3rd party servers.</p> <p>Adobe does not plan to make further enhancements to the Portal Director feature under the location listed below. AEM 6.4 has the Portal Director included, and customers upgrading from earlier releases can keep using it as is. Note that Portal Direct remains fully supported while being deprecated.</p> 
    <ul> 
     <li>/libs/portal/director</li> 
    </ul> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Portlet Component</td> 
   <td><p>Portlet Components under /foundation/components/portlet enables the hosting of JSR Portlets in AEM as components.</p> <p>Adobe does not plan to make further enhancements to the Portlet Component feature. AEM 6.4 has the Portlet Component included, and customers upgrading from earlier releases can keep using it as is. Note that Portlet Component remains fully supported while being deprecated.</p> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td><p>Support for Adobe Central Migration Bridge service has been deprecated as Adobe Central product is no longer supported.</p> </td> 
   <td>No replacement </td> 
  </tr>
    <tr>
   <td>Forms</td> 
   <td><p>Deprecated use of JSONObject in Query and OperationOptions. The following APIs are deprecated:
   <ul><li>setArguments(JSONObject arguments)</li><li>JSONObject getArguments()</li><li>OperationOptions(String operationId, JSONObject arguments</li><li>JSONObject getArguments()</li><li>void setArguments(JSONObject arguments)</li></ul>
   </p> </td> 
   <td>Use the IValueMap API </td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td><p>Deprecated Central Migration Bridge service</p> </td> 
   <td> No replacement </td> 
  </tr>
  <tr>
   <td>Assets</td> 
   <td><p>Assets Offloading has been deprecated starting with AEM 6.4</p> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>
-->

## Removed Features {#removed-features}

The table below lists features and capabilities that have been removed from AEM 6.4. Prior releases had these capabilities marked as 
deprecated.

|Area|Feature|Replacement|
|---|---|---|
|Analytics Activity Map|The version of the Activity Map that is included within AEM.|Due to security changes within the Adobe Analytics API, it is no longer possible to use the version of Activity Map that is included within AEM. The [ActivityMap plug-in provided by Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html) should now be used.|
|Components-Forms|Form Captcha (foundation/components/form/captcha)|Use the ReCaptcha by Google component instead|
|Components|Slideshow (foundation/components/slideshow)|No replacement|
|Components|Flash (foundation/components/flash)|No replacement|
|Components|Removed support to playback SWF files in the video component (foundation/components/video)|Use none-flash based video formats.|
|Components|Product Table (commerce/components/product_table)|No replacement|
|Task Management|Classic UI Task Management (/libs/cq/taskmanagement/content/taskmanager.html)|Deprecated since 6.0. Use the new task management that is combined with the workflow UI.|
|Workflow|Notification UI used between 5.6-6.2 (/libs/cq/workflow/content/notifications.html)|Workflow Inbox /aem/inbox|
|Forms|Export PDF to PDF/E-1 format using PDF Generator has been removed.|PDF Generator continues to support exporting PDF to PDF/A-1a/b, PDF/A-2a/b, and PDF/A-3a/b formats.|
|Forms|Support for images inside document fragments has been removed.|Interactive communications provides the capability to use images in print and web channels directly.|
|Forms|Out of the place upgrade|Support to perform out of the place upgrade is not available|
|Forms|Sidegrade for TarMK to DocumentMK migrations|You can export the data from older system and then import in a freshly setup system. For detailed instructions, see AEM Forms on JEE upgrade documentations|
|Forms|AEM Forms on JEE 32-bit installer not available.|Adobe has stopped shipping AEM Forms on JEE 32-bit installer. You can continue using 64-bit installer to install AEM Forms on JEE.|
|Forms|Removed support for using DAM images in Document Fragment Component.|You can use Image and Chart component in interactive communication's print channel. If you are using adaptive document's document fragment component in adaptive forms, it stops working after upgrading to AEM 6.4 Forms.|
|Forms|Removed the Adaptive Documents feature|You can use the interactive communications feature to create printed and web-based communications. If you use Adaptive Documents, install the compatibility package to continue using existing adaptive documents|
|Forms|Removed AEM Forms on JEE-specific landing page.|AEM Forms on JEE landing page is replaced with AEM landing page (/aem/start.html)|
|Forms|Removed support for default Captcha|Use reCAPTCHA service by Google.|
|Forms|Removed support for flash fields in AEM Designer. AEM Designer does not allow editing flash fields used in a form.|You can use AEM Designer released for a previous version to edit such forms.|
|Communities|Support for Captcha verification has been removed.|Use custom captcha integration (such as reCAPTCHA by Google) for verification.|

## Pre-announcement for Next Release {#pre-announcement-for-next-release}

The table below provides a list of changes for future release, that are not deprecated, but may impact customers. These are provided for planning purpose.

|Area|Feature|Announcement|
|---|---|---|
|Browser Support|Microsoft Internet Explorer|AEM 6.4 is the last release that supports Microsoft Internet Explorer 11.|
|Foundation|UI Framework|Adobe is deprecating the Coral UI 2 components in 2019. AEM 6.4 is completely based on Coral UI 3 (introduced with AEM 6.2). Adobe recommends its customers and partners that have build custom UIs with Coral 2 to refactored these to Coral 3. Adobe offers a tool to convert Coral 2 dialogs to Coral 3 - [Read more](/help/sites-developing/dialog-conversion.md).|
