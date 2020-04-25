---
title: Deprecated and Removed Features
seo-title: Deprecated and Removed Features
description: Release notes specific to deprecated and removed features in Adobe Experience Manager 6.4.
seo-description: Release notes specific to deprecated and removed features in Adobe Experience Manager 6.4.
uuid: 2619039b-72b4-4c6c-a813-90eed622b423
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 15819d42-4897-40fa-a013-e019d1580fa2
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

## Removed Features {#removed-features}

The table below lists features and capabilities that have been removed from AEM 6.4. Prior releases had these capabilities marked as 
deprecated.

<table> 
 <tbody>
  <tr>
   <td><strong>Area</strong></td> 
   <td><strong>Feature</strong></td> 
   <td><strong>Replacement</strong></td> 
  </tr>
  <tr>
   <td>Analytics Activity Map</td> 
   <td>The version of the Activity Map that is included within AEM.</td> 
   <td>Due to security changes within the Adobe Analytics API, it is no longer possible to use the version of Activity Map that is included within AEM.<br><br>The <a href="https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html">ActivityMap plug-in provided by Adobe Analytics</a> should now be used.</td> 
  </tr>
  <tr>
   <td>Components-Forms</td> 
   <td>Form Captcha<br /> (foundation/components/form/captcha)</td> 
   <td>Use the ReCaptcha by Google component instead</td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td>Slideshow<br /> (foundation/components/slideshow)</td> 
   <td>No replacement</td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td>Flash<br /> (foundation/components/flash)</td> 
   <td>No replacement</td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td>Removed support to playback SWF files in the video component<br /> (foundation/components/video)</td> 
   <td>Use none-flash based video formats.</td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td>Product Table<br /> (commerce/components/product_table)</td> 
   <td>No replacement</td> 
  </tr>
  <tr>
   <td>Task Management</td> 
   <td>Classic UI Task Management<br /> (/libs/cq/taskmanagement/content/taskmanager.html)</td> 
   <td>Deprecated since 6.0. Use the new task management that is combined with the workflow UI.</td> 
  </tr>
  <tr>
   <td>Workflow</td> 
   <td>Notification UI used between 5.6-6.2<br /> (/libs/cq/workflow/content/notifications.html)</td> 
   <td>Workflow Inbox /aem/inbox</td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td>Export PDF to PDF/E-1 format using PDF Generator has been removed.</td> 
   <td>PDF Generator continues to support exporting PDF to PDF/A-1a/b, PDF/A-2a/b, and PDF/A-3a/b formats.</td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td>Support for images inside document fragments has been removed. </td> 
   <td>Interactive communications provides the capability to use images in print and web channels directly.<br /> </td> 
  </tr>
    <tr>
   <td>Forms</td> 
   <td> Out of the place upgrade </td> 
   <td>Support to perform out of the place upgrade is not available <br/> </td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td> Sidegrade for TarMK to DocumentMK migrations </td> 
   <td> You can export the data from older system and then import in a freshly setup system. For detailed instructions, see AEM Forms on JEE upgrade documentations <br/> </td> 
  </tr>
    <tr>
   <td>Forms</td> 
 <td>AEM Forms on JEE 32-bit installer not available.</td> 
   <td>Adobe has stopped shipping AEM Forms on JEE 32-bit installer. You can continue using 64-bit installer to install AEM Forms on JEE. </td>  
  </tr>
    <tr>
    <td>Forms</td> 
    <td>Removed support for using DAM images in Document Fragment Component.</td> 
    <td> You can use Image and Chart component in interactive communication's print channel. If you are using adaptive document's document fragment component in adaptive forms, it stops working after upgrading to AEM 6.4 Forms. </td>  
  </tr>
  <tr>
   <td>Forms</td> 
   <td> Removed the Adaptive Documents feature</td> 
   <td> You can use the interactive communications feature to create printed and web-based communications. If you use Adaptive Documents, install the compatibility package to continue using existing adaptive documents<br/> </td> 
  </tr>
    <tr>
    <td>Forms</td> 
    <td>Removed AEM Forms on JEE-specific landing page.</td> 
    <td>AEM Forms on JEE landing page is replaced with AEM landing page (/aem/start.html) </td>  
  </tr>
   <tr>
   <td>Forms</td> 
   <td>Removed support for default Captcha</td> 
   <td>Use reCAPTCHA service by Google.</td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td>Removed support for flash fields in AEM Designer. AEM Designer does not allow editing flash fields used in a form.</td> 
   <td>You can use AEM Designer released for a previous version to edit such forms.</td> 
  </tr>
  <tr>
   <td>Communities</td> 
   <td>Support for Captcha verification has been removed.</td> 
   <td>Use custom captcha integration (such as reCAPTCHA by Google) for verification.</td> 
  </tr>
 </tbody>
</table>

## Pre-announcement for Next Release {#pre-announcement-for-next-release}


The table below provides a list of changes for future release, that are not deprecated, but may impact customers. These are provided for planning purpose.

<table> 
 <tbody>
  <tr>
   <td>Area<br /> </td> 
   <td>Feature<br /> </td> 
   <td>Announcement</td> 
  </tr>
  <tr>
   <td>Browser Support</td> 
   <td>Microsoft Internet Explorer</td> 
   <td>AEM 6.4 is the last release that supports Microsoft Internet Explorer 11.</td> 
  </tr>
  <tr>
   <td>Foundation</td> 
   <td>UI Framework</td> 
   <td>Adobe is deprecating the Coral UI 2 components in 2019. AEM 6.4 is completely based on Coral UI 3 (introduced with AEM 6.2). Adobe recommends its customers and partners that have build custom UIs with Coral 2 to refactored these to Coral 3. Adobe offers a tool to convert Coral 2 dialogs to Coral 3 - <a href="/help/sites-developing/dialog-conversion.md">Read more</a>.</td> 
  </tr>
 </tbody>
</table>
