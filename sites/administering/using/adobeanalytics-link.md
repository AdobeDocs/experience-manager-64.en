---
title: Configuring Link Tracking for Adobe Analytics
seo-title: Configuring Link Tracking for Adobe Analytics
description: null
seo-description: Learn about configuring link tracking for SiteCatalyst.
uuid: baf3c6e2-7136-4ef9-a997-30913be5da22
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: b727d878-0217-45e1-8e06-96c8897a1501
disttype: dist5
gnavtheme: light
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Configuring Link Tracking for Adobe Analytics{#configuring-link-tracking-for-adobe-analytics}

When users click links on pages of your website you can capture related information in Adobe Analytics. For example, use link tracking to learn how users interact with your site, track file downloads, and track exit links.

## Configuring Link Tracking for an Adobe Analytics Framework {#configuring-link-tracking-for-an-adobe-analytics-framework}

## Tracking File Downloads {#tracking-file-downloads}

Configure the Adobe Analytics framework so that files downloaded from associated pages are automatically tracked as downloads in Adobe Analytics. When you enable the tracking of downloads, only the file types that you specify are tracked.

Downloads of the following file types are tracked by default:

* exe
* zip
* wav
* mp3
* mov
* mpg
* avi
* wmv
* doc
* pdf
* xls

<!--
Comment Type: remark
Last Modified By: Roland Schaer (rschaer)
Last Modified Date: 2018-05-31T05:35:38.205-0400
<p>what's the current name for analytics.sitecatalyst.js ?</p>
<p>rschaer: name still applies</p>
-->

So for example, with download trackng enabled for PDF files, whenever users click links to PDF files, the download of the PDF is tracked.

The download tracking properties of the framework are implemented as code in the `analytics.sitecatalyst.js` file that is generated for a page. The following code sample represents the default download tracking configuration:

```
s.trackDownloadLinks= true;
s.linkDownloadFileTypes= 'exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls';
```

To enable download tracking for your Adobe Analytics framework:

1. [Open the Adobe Analytics framework and expand the **Link Tracking Configuration** section](#configuringlinktrackingforanadobeanalyticsframework).
1. Enable **Track Downloads**.
1. In the **Download File Types** box, type the filename extensions for the types of files that you want tracked.

## Tracking external links {#tracking-external-links}

You can track the clicking of external links (exit links) on your pages.

To track external links for your Adobe Analytics framework:

1. [Open the Adobe Analytics framework and expand the **Link Tracking Configuration** section](#configuringlinktrackingforanadobeanalyticsframework).
1. Configure the following properties according to your requirements.

Properties for tracking when external links are clicked:

* **Track External** 
  Enables external link tracking.

* **External Filters** 
  (Optional) Defines filters for matching the external URLs of the link targets. When the link targets match the filter, the link is tracked. External filters are useful for tracking only some of the external links on your pages.  
  To specify the external links to track, type all or part of the URL of the link target. Separate multiple filters with a comma. Enclose string literals within single quotation marks. No value (the default value of `''`, two single quotes) causes all external links to be tracked.

* **Internal Filters** 
  Defines filters for matching the URLs of internal links. When the link targets URLs that match this filter, the link is not tracked. The default value is a javascript command that returns the hostname of the URL for the current window address.  
  To specify the internal links that are not tracked, type all or part of the internal URL of the link target. Separate multiple filters with a comma. Enclose string literals within single quotation marks.  
  The default value is `'javascript:,'+window.location.hostname`  

* **Leave Query String** 
  Includes URL parameters when evaluating matches with internal and external filters.  
  Enable to include URL parameters when evaluating link target URLs against external and internal filters.

The external link tracking properties are implemented as code in the `analytics.sitecatalyst.js` file that is generated for a page. The following example code is generated for a page that is associated with a framework that has enabled external link tracking with the following configuration:

* External filter is `'google.com'`
* Internal filter is the default value of `'javascript:,'+window.location.hostname`
* Query strings are not included when evaluating the link target against filters.

```
s.trackExternalLinks= false;
s.linkExternalFilters= 'google.com';
s.linkInternalFilters= 'javascript:,'+window.location.hostname;
s.linkLeaveQueryString= false;
```

## Sending Variable Data with Link Clicks {#sending-variable-data-with-link-clicks}

You can configure AEM to send event and variable data to Adobe Analytics when a user clicks a link. The **Link Tracking Configuration** properties enable you to specify the Adobe Analytics events and variables to track when link clicks occur.

The framework mappings determine the event and variable values. You can map Adobe Analytics variables to the variables of your content components that store the data you want tracked when links are clicked.

To send variable data with link clicks:

1. [Open the Adobe Analytics framework and expand the **Link Tracking Configuration** section](#configuringlinktrackingforanadobeanalyticsframework).
1. Configure the following properties according to your requirements.

Properties for sending variable data with link clicks:

* **Link Track Events** 
  Enter the Adobe Analytics event variables that you want to use for counting link clicks.   
  Separate multiple variable names with a comma.   
  The default value of `None` causes no event tracking.

* **Link Track Vars** 
  Enter the Adobe Analytics variables that you want to send to Adobe Analytics when links are clicked. Separate multiple variable names with a comma.   
  The default value of `None` causes no variable data to be sent.

When you specify the events and variables to send, the configuration is implemented as code in the `analytics.sitecatalyst.js` file that is generated for a page. The following example code is generated for a page when the framework tracks the `event10` event and the `prop4` property:

```
s.linkTrackEvents= 'event10';
s.linkTrackVars= 'prop4';
```

## Example Link Tracking Configuration {#example-link-tracking-configuration}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-02-21T09:14:50.606-0500
<p>examples need reworking for we.retail </p>
-->

<!--
Comment Type: remark
Last Modified By: Roland Schaer (rschaer)
Last Modified Date: 2018-05-31T05:37:32.099-0400
<p>Adobe DigitalPulse Debugger used to point to:</p>
<p><a href="http://blogs.adobe.com/digitalmarketing/analytics/meet-the-new-digitalpulse-debugger/">http://blogs.adobe.com/digitalmarketing/analytics/meet-the-new-digitalpulse-debugger/</a></p>
<p>This is from 2010. Should we be using something more up-to-date?</p>
<p>Like the Adobe Debugger see https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html ?</p>
<p>rschaer: Yes. Please use https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger_install.html</p>
-->

Perform the following procedures to explore the link tracking behavior of the Adobe Analytics integration. The procedures show results from [Adobe Marketing Cloud Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger_install.html).

### General configuration {#general-configuration}

This example illustrates how the mapping works in the context of tracking and the debugger:

1. Open the framework that has been associated with a web page.
1. Drag the **Page** component to the mappings area of the framework. The **Page** component belongs to the **General** component group in Sidekick.

   >[!NOTE]
   >
   >The component that you should use in a real-life scenario depends on the component inherited from (if at all). 
   >
   >
   >If not you should have your own component exposed there (by defining an analytics subnode in its page component).

   Configure the mapping according to the following table, by dragging the Analytics (SiteCatalyst) variable from the left side-panel:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>CQ Variable<br /> </th> 
   <th>Entry in Variables Browser<br /> </th> 
   <th>Adobe Analytics Variable</th> 
  </tr> 
  <tr> 
   <td>pagedata.title</td> 
   <td>Custom eVar 1 (eVar1)</td> 
   <td>eVar1</td> 
  </tr> 
  <tr> 
   <td>eventdata.events.pageView</td> 
   <td>Custom 1 (event1)</td> 
   <td>event1</td> 
  </tr> 
 </tbody> 
</table>

1. Drag the Search component to the mappings area of the framework. The Search component belongs to the General component group in Sidekick. Configure the mapping according to the following table, by dragging the Analytics (SiteCatalyst) variable from the left side-panel:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <th>CQ Variable<br /> </th> 
   <th>Entry in Variables Browser</th> 
   <th>Adobe Analytics Variable</th> 
  </tr> 
  <tr> 
   <td>eventdata.keyword</td> 
   <td>Custom eVar 2 (eVar2)</td> 
   <td>eVar2</td> 
  </tr> 
  <tr> 
   <td>eventdata.results</td> 
   <td>Custom eVar 3 (eVar3)</td> 
   <td>eVar3</td> 
  </tr> 
  <tr> 
   <td>eventdata.events.search</td> 
   <td>Custom 2 (event2)</td> 
   <td>event2</td> 
  </tr> 
 </tbody> 
</table>

### Configure external link tracking {#configure-external-link-tracking}

1. In your framework, expand the **Link tracking Configuration** area.
1. Deselect **Track Downloads**.  

1. Select **Track External**.
1. Deselect **Leave Query String**.
1. Use the following value for the **External Filters** list to identify it as an external URL:  
   `‘yahoo.com’`  

1. Add the following value to the **Link Track Events** field: `  
   event1,event2`  

1. Add the following value to the **Link track vars** field: `  
   eVar1,eVar2`  

1. On the page that is associated with the framework, add a **Text **component. Inside the **Text** component, add a hyperlink pointing to the following address:  
   `https://search.yahoo.com/?p=this`  

1. Switch to **Preview mode** and click the link.

The call made will look like this when viewed with the Adobe Marketing Cloud Debugger:

![](assets/AA-LeaveQuerySearch-Blank.png) 

<!--
Comment Type: draft

<img imageRotate="0" src="assets/linkexternal1.png" />
-->

>[!NOTE]
>
>The URL does not contain the Query string: `?p=this`

### Include the URL parameter {#include-the-url-parameter}

1. In the framework, expand the **Link Tracking Configuration** area.
1. Enable **Leave Query String**.
1. Reload the page preview, and click the link.

The call details that appear in Adobe Marketing Cloud Debugger are similar to the following example:

![](assets/AA-LeaveQuerySearch-Active.png) 

<!--
Comment Type: draft

<img imageRotate="0" src="assets/linkexternal2.png" />
-->

>[!NOTE]
>
>This time the URL does contain the Query string: `?p=this`

<!--
Comment Type: draft

<h3>Perform a search</h3>
-->

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-06-28T10:00:11.117-0400
<p>Don't have a Search component in We.Retail and the page Search doesn't respond in Preview, nor trigger anything in the debugger.</p>
-->

<!--
Comment Type: draft

<ol>
<li>On the page that is associated with the framework, add the <strong>Search</strong> component.<br /> </li>
<li>Preview the page and perform a search using the <span class="kbd">aaaaaaaaaaa</span> keyword, which returns<strong> </strong>no results.</li>
</ol>
<p>The call details that appear in DigitalPulse Debugger are similar to the following example:</p>
-->

<!--
Comment Type: draft

<img imageRotate="0" src="assets/linkexternal3.png" />
-->

## Ad-Hoc Link Tracking {#ad-hoc-link-tracking}

Ad-hoc link tracking allows content authors to configure link tracking for a component. The configuration of the component overrides the **Link Tracking Configuration** of the framework, so on pages that are associated with the framework, **Text** components can be configured for link tracking of URLs.

Ad-hoc link tracking enables you to track download links, external links, together with event and variables data.

To enable ad-hoc link tracking you need to:

* [Associate the page that contains the **Text** component with the framework](../../administering/using/adobeanalytics-connect.md#associatingapagewithaadobeanalyticsframework).
* [Configure the Adobe Analytics framework to enable ad-hoc link tracking](#enablingadhoclinktracking).
* [Configure Link Tracking for a Text component](#configuringlinktrackingforatextcomponent).

<!--
Comment Type: remark
Last Modified By: Roland Schaer (rschaer)
Last Modified Date: 2018-05-31T05:43:38.104-0400
<p>is ad-hoc link tracking only for Text components?</p>
<p>what about Text-based components (eg Table, Text&Image, etc)?</p>
<p>rschaer: the link tracking is injected in the Rich-Text-Editor so as far the component uses RTE it should work</p>
-->

### Enabling Ad-hoc Link Tracking {#enabling-ad-hoc-link-tracking}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-02-21T09:14:51.192-0500
<p>to associate a page with the framework:</p>
<p>- https://chl-author.corp.adobe.com/content/help/en/experience-manager/6-4/sites/administering/using/adobeanalytics-connect.html#AssociatingaPagewithaAdobeAnalyticsFramework</p>
-->

Configure your Adobe Analytics framework to enable ad-hoc link tracking.

1. Open the Adobe Analytics framework and expand the **Link Tracking Configuration** section.  

1. Enable **Ad-hoc Link Tracking**.

   >[!NOTE]
   >
   >Not all user types have access to this checkbox. Contact your site administrator if you need access.

<!--
Comment Type: remark
Last Modified By: Roland Schaer (rschaer)
Last Modified Date: 2018-05-31T05:41:13.244-0400
<p>is this Note, and the rule extension, still valid?</p>
<p>rschaer: Yes</p>
-->

>[!NOTE]
>
>The XSS Antisamy configuration is now in SLING under path **/libs/sling/xss.config.xml** and the following rules need to be added to for ad-hoc linking to work:

#### Anchor tag rule extension {#anchor-tag-rule-extension}

```xml
<attribute name="onclick">
    <literal-list>
        <literal value="CQ_Analytics.Sitecatalyst.customTrack(this)"/>
    </literal-list>
</attribute>
<attribute name="adhocenable">
    <literal-list>
        <literal value="true"/>
        <literal value="false"/>
    </literal-list>
</attribute>
<attribute name="adhocevents">
    <regexp-list>
        <regexp name="anything"/>
    </regexp-list>
</attribute>
<attribute name="adhocevars">
    <regexp-list>
        <regexp name="anything"/>
    </regexp-list>
</attribute>
```

### Configuring Link Tracking for a Text Component {#configuring-link-tracking-for-a-text-component}

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-05-10T05:08:32.307-0400
<p>Need input - not all options available</p>
-->

Before you can configure ad-hoc link tracking for **Text** components themselves, the following configurations must have already been implemented:

* The [Adobe Analytics framework is configured to enable ad-hoc link tracking](#enablingadhoclinktracking).
* The [page that contains the **Text** component is associated with the framework](../../administering/using/adobeanalytics-connect.md#associatingapagewithaadobeanalyticsframework).

Use the following procedure to configure link tracking for a **Text** component:

1. Open the page in edit mode and edit the **Text** component.  

1. Select the text that you want to use as hypertext and click the Hyperlink button.

   ![](assets/chlimage_1-1.png)

1. Add the target URL in the Link To box, then expand the Link Tracking area.

   >[!NOTE]
   >
   >Custom link tracking is visible as a separate action, beside the Link/Unlink action (Analytics Icon). 
   >
   >
   >It will only be enabled when you have selected a valid Link in the RTE.

   <!--
   Comment Type: remark
   Last Modified By: Roland Schaer (rschaer)
   Last Modified Date: 2018-05-31T06:57:18.120-0400
   <p>screenshot</p>
   <p>can't find an equivalent in touch or classic (geometrixx/6.3) - was this a special implementation of the Text component?</p>
   <p>can't test the procedure without it</p>
   <p> </p>
   <p>rschaer: In Touch UI the custom link tracking is visible as a separate action besides the Link/Unlink action (Analytics Icon). It will only be enabled if the user has selected a valid Link in the RTE. Note: Link Tracking seems only to be available if Report Suite in Framework is using run mode "all" or "author".</p>
   -->

   <!--
   Comment Type: remark
   Last Modified By: Alison Heimoz (aheimoz)
   Last Modified Date: 2018-06-28T05:04:54.906-0400
   <p>is set to "all"....</p>
   -->

   <!--
   Comment Type: draft

   <img imageRotate="0" src="assets/chlimage_1-2.png" />
   -->

   ![](assets/AA-17.png)

1. Enable **Custom Link Tracking** to override the link tracking configuration of the Adobe Analytics framework and to enable link tracking for the current link.  

1. (Optional) To track events with the link click, add Adobe Analytics event names in the **Include Adobe Analytics Variables** field. Separate multiple event name with commas, for example  
   `event1, event22`.
1. (Optional) To track variable data with the link click, add Adobe Analytics variables in the **Include Adobe Analytics Variables** field. Use either of the following formats:

    * `*<Variable-name>*: *<Dynamic Value>*`
    * `*<Variable-name>*: *‘CONSTANT’*`

   The following examples illustrate each format:

    * `eVar10:pagedata.title`
    * `prop1: ‘Aubergine'`

   Separate multiple values with a comma.

1. Select **OK**.

