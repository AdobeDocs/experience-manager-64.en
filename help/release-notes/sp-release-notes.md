---
title: AEM 6.4 Service Pack Release Notes
seo-title: AEM 6.4 Service Pack Release Notes
description: Release notes specific to Adobe Experience Manager 6.4 Service Pack 3.
seo-description: Release notes specific to Adobe Experience Manager 6.4 Service Pack 3.
uuid: 49a710a8-7cd5-47de-9a96-7af7f3c00dfc
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 93067308-e275-490f-8d78-ae79e046059c
legacypath: /content/docs/en/aem/6-1/release-notes-sp1
---

# AEM 6.4 Service Pack Release Notes {#aem-service-pack-release-notes}

## Release Information {#release-information}

| Products |**Adobe Experience Manager (AEM) 6.4** |
|---|---|
| Version |6.4.4.0 |
| Type |Service Pack Release |
| Date |April 04, 2019 |
| Download URL | [AEM 6.4.4.0 on PackageShare](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/servicepack/AEM-6.4.4.0) |

## What's included in AEM 6.4.4.0 {#what-s-included-in-aem}

AEM 6.4.4.0 is an important update that includes performance, stability, security and key customer fixes and enhancements released since the general availability of AEM 6.4 in **April 2018.**

It is also cumulative which means that 6.4.4.0 includes all AEM 6.4 service packs release before it.

Some of the key highlights of AEM 6.4.4.0 are:

* The built-in repository (Apache Jackrabbit Oak) is updated to version 1.8.11.
* Added support for caching service version to avoid frequent service version HTTP requests.
* Added support for deleting auto tags.
* Implemented endless scrolling for catalog wizard.
* Backported ability to restrict permissions according to community sites.
* Performance fixes (caching, async execution, exclusion list) for Sling Granite Content Health Check.
* Added assetpicker button to pagethumbnail dialog.
* Added new property to allow tooltip positioning on fields.
* Improved support of ColorPicker inside the Multifield.
* Added a check to ignore empty values for number input multifields in the clientlibs of Content Fragment.
* Enabled support for Microsoft Translator Text API v3.

## List of changes {#list-of-changes}

### Assets {#assets}

* Migrate of ACP and Stock Integration to AEM 6.4.4.0 NPR-27632
* Publish later empty asset folder with sub-folders makes the sub-folders disappear. NPR-27558: Hotfix for CQ-4254701
* Addition of Single non-namespaced String[] property causes incomplete XMP writeback. NPR-26805: Hotfix for CQ-4254142
* After rasterizing the input pdf, the output produced has missing images. NPR-27929: Hotfix for CTG-4150481
* Move Asset Wizard is showing an incorrect count of Referencing pages for published pages. NPR-27833: Hotfix for CQ-4258014
* AssetPicker search only the first tag to filter the result when filtering with tags. NPR-27778: Hotfix for CQ-4257705
* AEM OOTB PDF handler gets stuck on processing PDF with foreign characters. NPR-28778: Hotfix for CQ-4254234
* When a CSV file has value which is separated by comma in a single column, AEM CSV editor does not escape the comma and treats it as a separate column. NPR-28801: Hotfix for CQ-4261694
* Issue with Metadata Schema Editor while using path Browser to select data. NPR-28674: Hotfix for CQ-4263005
* Too many assets get processed to the Smart Content Service resulting in a huge amount of time to complete the periodic tagging process. NPR-28640: Hotfix for CQ-4262661, CQ-4262644, CQ-4263234
* Desktop actions do not work for Omnisearch results from aem/start.html page. NPR-27242: Hotfix for CQ-4248176
* Assets API does not allow upload of file > 2GB causing upload failure. NPR-27629: Hotfix for Granite-23590
* Metadata does not save in downloaded asset in the first attempt in case Dynamic Media is enabled on the instance. NPR-28233: Hotfix for CQ-4260759
* Service resolver is not closed in SiteCatalyst configuration. NPR-28015: Hotfix for CQ-4259397
* Moving assets in DAM does not result in a similar move on Scene7 (p2p config). NPR-28313: Hotfix for CQ-4261091

### Sites {#sites}

* [Classic UI] A fraction of live copies appear in rollout list. NPR-28598, NPR-28574: Hotfix for CQ-4263410
* LiveRelationshipManagerImpl throws exceptions when cq:master is empty or invalid. NPR-28590: Hotfix for CQ-4263115
* The out of the box "Request for Deletion" workflow doesn't delete the pages properly. NPR-28668: Hotfix for CQ-4263195
* Relationship Status UI does not show proper year or timestamp values for related coral-datepicker fields. NPR-28666: Hotfix for CQ-4263661
* Cross-site scripting (XSS) in SuggestionHandler for 6.4. NPR-28693: Hotfix for CQ-4253821
* Move folder from siteadmin ends in out of memory and makes AEM unavailable. NPR-28346: Hotfix for CQ-4261398
* MSM LiveCopy Rollout configurations are lost after update. NPR-28311: Hotfix for CQ-4258705
* Unable to scroll beyond 40 blueprint configurations. NPR-27640: Hotfix for CQ-4239166
* Usage of SyntheticResource as reference throws a Null Pointer Exception and blocks the move of the pages.  NPR-27576: Hotfix for CQ-4258262
* The PushOnModify does not work on delete on 6.1 to 6.4 upgraded instance. NPR-28108: Hotfix for CQ-4259833
* [Classic UI]  Cancel inheritance button is missing and component is editable on a live copy page. NPR-28256: Hotfix for CQ-4260161
* OakState0001: Unresolved conflicts on Rollout. NPR-27982: Hotfix for CQ-4259548
* When copy/pasting a structure containing SyntheticResource references, the process ends with an error 500. NPR-27709: Hotfix for CQ-4259179
* Unable to terminate running workflows when payloads are activated. NPR-27672: Hotfix for CQ-4258520
* Rollout shows duplicate rollout paths after upgrade from 6.1 to 6.4. NPR-27845: Hotfix for CQ-4259487
* Integrate dam assetpicker modal in page thumbnail component. NPR-28131: Hotfix for CQ-108042
* [Classic UI] Unable to open Dialogs with Tags widget. NPR-28575: Hotfix for CQ-4262680
* Multifield file upload does not show drop zone. NPR-28676: Hotfix for CQ-4263516
* 'Invalid recursion selector value' error while migrating a component from AEM 6.0 to AEM 6.2. NPR-28609: Hotfix for CQ-4241258 
* Rich Text Editor in dialog is flickering when popover of a plugin is higher than text area, hence, blocking any further authoring. NPR-27579: Hotfix for CQ-4257440
* [Classic UI] cq:action editannotate does not work. NPR-28232: Hotfix for CQ-4257703
* Removing tags from the tags filter  asset search panel of the page editor doesn't refresh the list properly. NPR-27983: Hotfix for CQ-4245567
* If the multifield number values are empty, clicking Save will result in infinite loading prompt without actually ever completing.  NPR-28400, NPR-28393: Hotfix for CQ-4244058, CQ-4244349
* With just read permission, users/groups are not able to select an XF and have no option to view the XF and its page properties. NPR-28341: Hotfix for CQ-4260412
* The JSON data received from Target has a number of escape characters causing the application page to break. NPR-28318: Hotfix for CQ-4252043
* Unable to edit any component after installing AEM 6.4.3. NPR-28125: Hotfix for CQ-4261216
* Deletion of all the tags for a tag field is not persisted for a structured content fragment. NPR-28133: Hotfix for CQ-4247241
* When editing a Content Fragment “jcr:lastmodifiedby” and “jcr:lastmodified” property, values are getting updated without user making any changes. NPR-27847: Hotfix for CQ-4257138
* Content Fragments versioning compare diff improvements for AEM 6.4. NPR-27764
* If there is no cq:allowedTemplates defined on /content/experience-fragments and allowedPaths is used on the Experience Fragement template, an error is thrown when the Experience Fragement is moved/copied. NPR-27487: Hotfix for CQ-4257489
* Create  button appears on refresh for the new user. NPR-27335: Hotfix for CQ-4255360
* While trying to move a published page, the "Referencing Pages" count that appears on the first page of the "Move Page" wizard is  incorrect. NPR-28111: Hotfix for CQ-4259663
* [Touch UI] References Rail doesn't show incoming links. NPR-28529: Hotfix for CQ-4262306
* Unable to edit any component and Page properties after installing AEM 6.4.3. NPR-27998: Hotfix for CQ-4261216, CQ-4260441
* Migrate contexthub to jquery 3. NPR-28397: Hotfix for GRANITE-19902

### Commerce {#commerce}

* Unable to select catalog if there are more than 20 catalogs in a folder. NPR-27649: Hotfix for CQ-4258119
* Commerce wizards & properties views are broken due to header.referer missing. Hotfix for CQ-4261122

### Campaign - Targeting {#campaign-targeting}

* com.day.cq.personalization.impl.TeaserResourceEventHandler goes into an infinite loop and causes updates to nodes on publish instances. Hotfix for CQ-4263096

### Replication {#replication}

* Error while building replication content com.day.cq.replication.AccessDeniedException. NPR-28314: Hotfix for CQ-4261401
* Session leak when User agent id is set to admin in replication agent. NPR-28220: Hotfix for CQ-4255517

### DAM - Creative Cloud {#dam-creative-cloud}

* Backport HTTP API to find similar images from within AEM Assets. Hotfix for CQ-4254091
* Enhance the ACP API to allow the results of a query to be restricted to the members of a collection. Hotfix for CQ-4258708

### DAM - Formats {#dam-formats}

* After metadata export is triggered, the page is redirected to a 404 page. Hotfix for CQ-4262447

### DAM - General {#dam-general}

* [Adobe Stock Integration] Server error modal is displayed with an Oauth error in the error.log file. Hotfix for CQ-4260406
* Adobe Stock integration does not function if 6.4.4 is applied to 6.4.3. Hotfix for CQ-4266009
* The Link to CF Model is missing even after applying SP3 patch. Hotfix for CQ-4259029

### Platform {#platform}

* [Classic UI] The edit button is not available in Base Report component after upgrading to 6.4.2. NPR-28560: Hotfix for CQ-4262825
* When using a query combining property.operation=like and property.depth, it ends up in an InvalidQueryException. NPR-28570: Hotfix for CQ-4262652
* Internal Server Error when newly added language node is removed from overlayed language node. NPR-28661: Hotfix for CQ-4239194
* Null Pointer Exception in stderr.log in sling-oak-1 thread on random starts. NPR-28665: Hotfix for CQ-4237845

### Felix {#felix}

* webconsole.plugins.memoryusage causes a deadlock on refresh. NPR-27895:  Hotfix for GRANITE-20715

### Granite {#granite}

* Sling Content Access Health Check performs long excessive /libs validation for cutom resource resolver search path. NPR-28113: Hotfix for GRANITE-23529

### Content Fragment Management {#content-fragment-management}

* Usability improvements and feature parity with Assets for Content Fragments. Hotfix for CQ-4253883

### Communities {#communities}

* Upgrade vulnerable bootstrap to 3.4 and ckeditor libraries to 4.5.11. NPR-28490: Hotfix for CQ-4257511
* Cancellation of the editing modes does not restore the deleted attachment. NPR-27902: Hotfix for CQ-4255150
* The compose on behalf of box should only be visible to the privileged members. NPR-27900: Hotfix for CQ-4251235
* Add rep:cache into Ignorable Nodes at AEM Communities User Sync Listener on publish instances. NPR-27842: Hotfix for CQ-4247234
* The search box is showing escape character at UI level. NPR-27838: Hotfix for CQ-4259757
* Error is generated while searching for special characters like ( , +,? in quicksearch. NPR-28213: Hotfix for CQ-4260969
* Create a 'community-specific administrators' group for the users to be able to edit and author the relevant communtiy site. NPR-27731
* Added logic for keyboard event to open up video. NPR-27726: Hotfix for CQ-4254026
* Enabled keyboard navigation for AEM Communities Enablement components on Publish. NPR-27728: Hotfix for CQ-4254028
* Added aria-label for list and card view button. NPR-27727: Hotfix for CQ-4254027
* Handling open resource resolver sessions in Social- Communities. NPR-27721: Hotfix for CQ-4258714

### Translation {#translation}

* Provide support for Microsoft Translator Text API v3. NPR-28366: Hotfix for CQ-4249755
* jcr:language & cq:language are not automatically updated in the Translated Language. NPR-28338: Hotfix for CQ-4256046
* Cyclic references cause StackOverflowError when creating language copy. NPR-27596: Hotfix for CQ-4255621
* In a multi-language translation project, clicking save and close results in subsequent pages added to the project results in new projects being created instead of new translation jobs being created in existing project. NPR-28219, NPR-28236: Hotfix for CQ-4261276, CQ-4260731
* Error String too long when adding content fragment with bulk data due to limitation on the number of characters allowed. NPR-28722: Hotfix for CQ-4262362

### Social {#social}

* Comment posted to next page gets highlighted with yellow everytime a new comment is posted. Hotfix for CQ-4261359
* Unable to delete comments in the User Generated Content using API. NPR-28075: Hotfix for CQ-4261135
* AbstractNotificationOperationService cause ClassCastException. Hotfix for CQ-4260456
* Remove reference to Shareable Content Object Reference Model (SCORM) Cloud in the player. Hotfix for CQ-4260779

### UI - Foundation {#ui-foundation}

* The "Filesystem output cache" feature integrated in the HTML Client Library Manager breaks the "debugClientLibs" feature for compiled scripts like LESS files. NPR-27249: Hotfix for Granite-23313
* The number of assets displayed when the debug mode is activated is always 1 and a lot of JS errors are thrown in the console of the browser.  NPR-27575: Hotfix for GRANITE-23750
* Save and close on page properties doesn't return to proper page in AEM WAR with Tomcat. NPR-27566: Hotfix for GRANITE-23671

### Integration {#integration}

* com.day.cq.personalization.impl.TeaserResourceEventHandler goes into an infinite loop and causes updates to nodes on publish instances. NPR-28561: Hotfix for CQ-4263096
* The cq:actions are not taken in consideration for a targeted component. NPR-27616: Hotfix for CQ-4257497
* LiveCopy inheritance cancellation does not work properly on targeted containers. NPR-28129: Hotfix for CQ-4259813
* [Cloud Service Configs] The "inherited from" checkbox appearing at the root level should be removed. NPR-27856:  Hotfix for CQ-4259676

### Sling {#sling}

* Update to Sling Models API 1.3.8, Impl 1.4.10. NPR-27636: Hotfix for GRANITE-23537

### OAK - Segment Persistence {oak-segment-persistence}

* SegmentBufferWriter not flushed after OnRC. NPR-27464

### Projects

* Multi-language translation project is not creating multiple language jobs for the users that are not part of the administrators group. NPR-28508: Hotfix for CQ-4262023
* The ProjectTaskListServlet is leaking a ResourceResolver whenever getTaskRenderers is called during startup of the service. NPR-27590: Hotfix for CQ-4258011
* If a directory has more subdirectories than the page size and ordering is by date or size, then an error prevents to move beyond the first page. NPR-28867: Hotfix for CQ-4265039
* Backport Cross-site scripting (XSS) fixes in DAM Viewers. NPR-28106:  Hotfix for CQ-4253215
* Unable to add pages to translation project by project-administrators as the link to add new pages to the translation project is not visible. Hotfix for CQ-4266334

### Workflow

* When we open complete work item dialog in the workflow notification which has a Tag field , clicking on cross mark  adds a Tag property to it. NPR-28304: Hotfix for CQ-4261321
* User Selection Toggle Button in Reassign Task Dialog is not working. NPR-28963: Hotfix for CQ-4264206

### Forms {#forms}

>[!NOTE]
>
>AEM Service Pack does not include fixes for AEM Forms. They are delivered using a separate Forms add-on package. In addition, a cumulative installer is released that includes fixes for AEM Forms on JEE. For more information, see [Install AEM Forms add-on](/help/release-notes/sp-release-notes.md#install-aem-forms-add-on-package) and [Install AEM Forms JEE installer](/help/release-notes/sp-release-notes.md#forms-jee-installer).

The key highlights for AEM 6.4.4.0 forms are:

* Added support to record document security APIs for signing and certifying as transactions.

### Forms add-on package {#forms-add-on-package}

#### Adobe Sign integration {#adobe-sign-integration}

* AEM 6.4 Forms Client SDK does not contain adobesign-recipent package. NPR-27735: Hotfix for CQ-4259372

#### Adaptive Forms {#adaptive-forms}

* When an adaptive form is created with a blank template, customers are not able to child panels to the root panel of the form.. NPR-28758: Hotfix for CQ-4264157
* When the value of the year field of date component is 9999, the validation script fails. NPR-28580: Hotfix for  CQ-4262620
* When an adaptive form is created with a blank template, customers are not able to child panels to the root panel of the form.. NPR-28758: Hotfix for CQ-4264157
* Unable to set value between the fields of lazy loaded fragments of an adaptive form. NPR-27758: Hotfix for CQ-4259703
* Adaptive form does not use Rich text Editor but loads its libraries.  NPR-27759:  Hotfix for CQ-4259193
* Redirect to URL is not working for adaptive forms embeded in an AEM Sites page. NPR-27620: Hotfix for CQ-4239287
* Unable to set value between the fields of lazy loaded fragments of an adaptive form. NPR-28320: Hotfix for CQ-4262345
* Adaptive form does not use Rich text Editor but loads its libraries.  NPR-28001: Hotfix for  CQ-4259703, CQ-4259193
* Scribble Signature does not work for AEM Forms App running on Apple iOS 12.1. NPR-28497: Hotfix for CQ-4261765
* Submit Action using 'Forms Workflow' Classic authoring issues in 6.4. Hotfix for CQ-4252740
* Error handling block and tmp storage removal. NPR-28806: Hotfix for CQ-4264441

### Forms - Correspondence Management {#correspondence-management}

* Agent UI fails to retain original size of the image. NPR-28800: Hotfix for CQ-4259767
* CCR/Agent UI: Labels of Date fields shifted in Data tab. Hotfix for CQ-4255499

#### Forms - Transaction Reporting {#forms-transaction-reporting}

* Added support to count using digital signatures or certifying a document as billable transactions. NPR-28495: Hotfix for CQ-4260236
* Add Digital signature and Certify to Billable API. Hotfix for CQ-4260236

#### Forms Management {#forms-management}

* Added support to replace usage of handlebars client library with underscore in Forms Manager's start review wizard and move asset wizard. NPR-27643: Hotfix for CQ-4246536.
* One bundle remains in installed state after installing Forms Management package on release/640 branch. Hotfix for CQ-4265410
* Forms submitted with attachments in them are not appearing in workflow with submit action "Invoke AEM Forms Workflow" & enable portal submit checked . Hotfix for CQ-4263110

#### Forms - Backend Integration {forms-backend-integration}

* Unable to do testing of pre/post preprocessor and custom submit using Client SDK, Hotfix for CQ-4238469

### Forms JEE installer {#forms-jee-installer}

#### Forms - Document Security {#forms-document-security}

* On using the updatepolicy service, the cannot coerse object error occurs. NPR-28751: Hotfix for CQ-4252287
* Signature Build failing with older version of commons-pkg. Hotfix for  CQ-4265535

#### Forms - Foundation JEE {#forms-foundation-jee}

* When AEM Forms is inatlled on IBM WebSphere, creating a Form Data Model based on SOAP fails. NPR-27923:  Hotfix for CQ-4251134
* SRT tool of PDF Generator fails to detect installed version of Adobe Acrobat. NPR-27971

#### Forms - Designer {#forms-designer}

* Some JPEG images in an XDP template do not render properly.  NPR-26702: Hotfix for LC-3917457

#### Forms - OBSOLETE {#forms-obsolete}

* The paper capture service crashes while processing  TIFF files. NPR-28079:  Hotfix for CQ-4240649

#### Forms - Workflow {forms-workflow}

* HTML5 Forms with default submit process in an.lca do not work on JBoss 7. NPR-28675: Hotfix for CQ-4243928
* Unable to submit PDF Forms in HTML Workspace. NPR-28058: Hotfix for CQ-4260373 
* Customer data gets printed in info logs using Invoke FDM Service Forms Workflow. Hotfix for CQ-4260385

## Feature Packs Included {#feature-packs-included}

>[!NOTE]
>
>For AEM Forms customers, it is essential to install AEM Forms add-on package after installing any AEM Service Pack, Cumulative Fix Pack, or Feature Pack.

### Sites {#sites}

* Content Fragments versioning compare difference improvements for AEM 6.4.  NPR-26760: FP for CQ-4248839
* Content Fragments variation difference improvements for AEM 6.4.  NPR-27866: FP for CQ-4248839
* Enabled feature in OSGI configuration "AEM Workflow Withdraw Feature Flag". The withdraw action should terminate the workflow instance after setting the flag. NPR-26451: Hotfix for CQ-4259090

### Platform {#platform}

* Enhance Query Builder Facet Extraction leverage Oak API for 6.4. NPR-26674: FP for CQ-4230337

## Hotfixes and Feature Packs included in previous Service Packs {#hotfixes-and-feature-packs-included-in-previous-service-packs}

<div class="details"> 
 <h3 class="summary">AEM 6.4.3.0</h3> 
<p>AEM 6.4.3.0 is an important update that includes performance, stability, security and key customer fixes and enhancements released since the general availability of AEM 6.4 in <strong>April 2018.</strong></p> 
 <p>It is also cumulative which means that 6.4.3.0 includes all AEM 6.4 service packs release before it.</p> 
 <p>Some of the key highlights of AEM 6.4.3.0 are:</p> 
 <ul> 
   <li>The built-in repository (Apache Jackrabbit Oak) is updated to version 1.8.9.</li>
   <li>Added support for allowedPaths property on Adaptive forms templates.</li>
   <li>Enhanced panel based search for Assets in AEM
    Cross-site scripting (XSS) fixes in the Login page.</li>
   <li>Improved UI instrumentation.</li>
   <li>Improvements in FormData handling.</li>
   <li>Improved handling of item naming inside a Multifield.</li>
   <li>Improved handling of placeholder items (Card View and List View) during selection.</li>
   <li>Added Adobe IMS Authentication and Admin Console Support for Managed Services.</li>
  </ul>
  <h3>Assets</h3>
  <ul>
  <li>The DAM Update Asset workflow does not extract references from INDD files if the IDS Decouple option is enabled. NPR-26243; Hotfix for CQ-4250933</li>
  <li>The success message is not displayed when assets are published with Assets Bulk Editor. NPR-26252; Hotfix for CQ-4251688.</li>
  <li>Having looked at an asset from a search result, if you click the Back button in the browser, it leads to a 'Bad Request' error message with 400 error code. NPR 26578; Hotfix for CQ-4253741</li>
  <li>The asset metadata shows invalid namespace error after installing a service pack. NPR-22341; Quickfix for CQ-4237202</li>
  <li>The option to reorder folders and content fragments in list view is not displayed for the applicable folders. NPR-27153; Hotfix for CQ-4255873</li>
  <li>Users are not able to add assets to a new collection, as it results in an error message with a broken image in the error popup dialog. NPR-22431; Hotfix for CQ-4237086</li>
  <li>Cascading dropdown is not supported on dynamic dropdown lists. NPR-27043; Hotfix for CQ-4252564</li>
  <li>If users set a non-default value for the 'Company Root Folder' in the DMS7 cloud config, the Viewer Preset does not work as expected. NPR-26360; Hotfix for CQ-4249505</li>
  <li>Asset reporting is failing for instances with a very large number of assets. NPR-27278; Hotfix for CQ-4256748</li>
  <li>Subfolders do not inherit the parent folder's SmartCrop image profile. NPR-27197; Hotfix for CQ-4256273</li>
  <li>When Dynamic Media integration is enabled, some metadata properties of Assets are modified. The width, the height, and the location attributes are not displayed. NPR-27203; Hotfix for CQ-4256258</li>
  <li>Dynamic Media does not use the configured proxy for some types of assets. NPR-25211; Hotfix for CQ-4244871</li>
  <li>Metadata Editor page contains Null Pointer Exception for invalid item parameter. NPR-26169; Hotfix for CQ-4241368.</li>
  <li>If a drop-down has a choice rule and a required rule applied to it, the required rule cannot be satisfied in the metadata editor. NPR-27479; Hotfix of CQ-4251428</li>
</ul>
<h3>Sites</h3>
<ul>
  <li>A user can control the rich text editor features in the in-line full screen mode using content policies, but cannot control the Edit Dialog rich text editor features with content policies. NPR-26750: Hotfix for CQ-4241130</li>
  <li>Rich text editor becomes un-usable when switched from full screen to floating dialog. The floating view contains two rich text editors. NPR-25589: Hotfix for CQ-4206008</li>
  <li>When the return key (Enter key) is pressed in a text field, the rich text editor switches to full-screen mode. NPR-26204: Hotfix for CQ-4245893</li>
  <li>List plugin of rich text editor is disabled automatically and does not allow modifications. NPR-26507: Hotfix for CQ-4239387</li>
  <li>When a special character is added to the rich text editor window, the window scrolls to the top. NPR-26435: Hotfix for CQ-4249869</li>
  <li>Client Context segment.js caching vs. non-caching questions. NPR-26622: Hotfix for CQ-4253486</li>
  <li>When a child rule is activated from the author instance to the publish instance, the publish instance stops working. NPR-26601: Hotfix for CQ-4253588</li>
  <li>When the rich text editor is combined with multiple fields, the Uncaught TypeError: fieldAPI.getName is not a function at foundation.js error occurs. NPR-27146: Hotfix for CQ-4253155</li>
  <li>Salesforce integration is not able to use the proxy configuration. NPR-27244: Hotfix for CQ-4245300</li>
  <li>When you schedule a page for activation using the Manage Publication option for a later date and switch to the list view, the calendar icon is missing. NPR-26974: Hotfix for CQ-4239206</li>
  <li>Users are not able to edit closed user group permissions in the page properties. NPR-27138: Hotfix for CQ-4256089</li>
  <li>Unable to edit tags via tagging. NPR-26957: Hotfix for CQ-4254858</li>
  <li>When a tag referenced from a structured content fragment model is moved, the existing references to the tag within a content fragment is not updated. This happens in the edit screen of the content fragment model. NPR-26776: Hotfix for CQ-4251805</li>
  <li>When you create and promote a launch with several pages, multiple version for each page are created. NPR-26917: Hotfix for CQ-4254663</li>
  <li>AEM  siteadmin  does not handle paths typed into the browser address bar. NPR-26780: Hotfix for CQ-4254097</li>
  <li>When a page is moved to a new location without renaming it, the version history of the page is lost. NPR-26706: Hotfix for CQ-4254025</li>
  <li>URLs in experience fragment admin editor does not allow overlays. NPR-26319: Hotfix for CQ-4252156</li>
  <li>When a page is created with a template containing empty experience fragment and published, the page fails to open and a DefaultSlingScript error occurs. NPR-26305: Hotfix for CQ-4252460</li>
  <li>When data-sly-use is used with classes with identical name, non-compliable code is produced. NPR-27282: Hotfix for Sling-7581</li>
  <li>Post upgrade SP installation, the sites have blank blueprint rollout configuration. NPR-27609: Hotfix for CQ-4257078</li>
</ul>
<h3>DAM - Brand Portal</h3>
<ul>
  <li>Tag predicates are not published when metadata schema form is published to Brand Portal. Hotfix for CQ-4256218</li>
  <li>When a third-level folder is published from AEM to Brand Portal, without publishing the parent folders, the folder name changes. Hotfix for CQ-4255423</li>
  <li>The path browser predicate is published from AEM Assets to Brand Portal as expected. However, the published path at BP remains /content/dam, which must be updated. Hotfix for CQ-4256240</li>
</ul>
<h3>DAM - Creative Cloud</h3>
<ul>
  <li>"Search Adobe Assets" Icon is missing from the AEM main navigation. Hotfix for CQ-4254343</li>
</ul>
<h3>DAM - DM Client</h3>
<ul>
  <li>After ingesting videos into a folder associated with the AVS Video Processing Profile, the browser window refreshes over and over again. Hotfix for CQ-4253563</li>
  <li>YouTube Publish fails when using an Ad Hoc Tag that includes uppercase characters. Hotfix for CQ-4252477</li>
  <li>When an annotation is created in an asset like PDF, the UI starts an infinite page refresh loop. NPR-27052: Hotfix for CQ-4255396</li>
</ul>
<h3>DAM - DM Services</h3>
<ul>
  <li>Dynamic Media does not use the configured proxy for some types of assets. NPR-10727; Hotfix for CQ-4244871</li>
</ul>
<h3>Platform</h3>
<ul>
  <li>Performance issues with org.apache.sling.i18n. NPR-26812: Hotfix for SLING-7543</li>
  <li>Unable to see the node properties when the input XML is formatted and deployed. NPR-26198: Hotfix for CQ-4250448</li>
  <li>IndexOutOfBoundsException in ResourceProviderTracker. NPR-26968: Hotfix for GRANITE-23310</li>
  <li>JMX console accumulates numerous admin sessions and a new session is opened every 5 minutes. NPR-26958: Hotfix for CQ-4251090</li>
  <li>After upgrading from 6.2 to 6.4, the log file shows stack trace for unclosed resource resolver com.adobe.granite.repository.hc.impl.content.sling.SlingContentHealthCheck. NPR-26176: Hotfix for Granite-21734</li>
  <li>When an out-of-the-box dispatcher flush agent is configured to update aliases, the operation fails with a StackOverflowError. NPR-26373: Hotfix for CQ-4242928</li>
  <li>Replication uses expired OAuth token until it fails. NPR-25894</li>
  <li>Restricted page (Closed User Group page) with sling: alias does not redirect the user to the login page. NPR-25715: Hotfix for Granite=22263</li>
  <li>On publishing tags, no activity is displayed on the UI. Hotfix for CQ-4255961</li>
  <li>Unable to edit tags in classic UI. Hotfix for CQ-4258697</li>
  <li>Updated org.apache.felix.http.bridge to version 4.0.4. NPR-27038: Backport for Granite - 23334</li>
  <li>Package manager activity logs should be extracted in a separate log file. NPR-27323: Hotfix for Granite-14866</li>
  <li>Package validator does not report overlays in CFP. NPR-27119: Hotfix for GRANITE-22825</li>
</ul>
<h3>Projects</h3>
<ul>
  <li>ACP API mishandles paging with only subdirectory children. NPR-27617: Hotfix for CQ-4258639</li>
</ul>
<h3>OAK</h3>
<ul>
  <li>Unable to login to the repository after installing AEM 6.4 Service Pack 2. NPR-27171: Hotfix for Granite-23317</li>
</ul>
<h3>Replication</h3>
<ul>
  <li>Audit Log remains open with active sessions which keep on constantly increasing with ~750 each day. NPR-27062: Hotfix for CQ-4241350</li>
</ul>
<h3>Communities</h3>
<ul>
  <li>Forum posts and replies are added on top of the second page and when refreshed, the post moves to the correct location on top of the first page. NPR-27342: Hotfix for CQ-4247338</li>
  <li>Links to all the resources drop the context path (/aempublish) after scrolling. NPR-26982: Hotfix for CQ-4254345</li>
  <li>Added groups are not visible in Community Managers, Community Moderators and Privileged Member drop-down on editing a published site. NPR-27190: Hotfix for CQ-4258574</li>
  <li>Only 10 groups are listed in enablement resources page even if pagination is enabled for group listing. NPR-26934: Hotfix for CQ-4252985</li>
  <li>Option to enable/disable search for Scheduled Post in journal component is provided in ConfigMgr, and SearchScheduledPosts job is optimized. NPR-26923: Hotfix for CQ-4250463</li>
  <li>Search by keywords in address does not work in calendar component page when AEM community is set to work with DSRP. NPR-26737: Hotfix for CQ-4258493</li>
  <li>Implemented direct link to the comment instead of the main post in a comment's detail, for moderation UI & enablement resources. NPR-26704: Hotfix for CQ-4251381</li>
  <li>Content moderated through multi-selection on moderation console does not appear on Activity Stream. NPR-26695: Hotfix for CQ-4253244</li>
  <li>Search with First Name and Last Name in To field of Communities Messaging does not return the expected result. NPR-26385: Hotfix for CQ-4248673</li>
  <li>Error observed when uploading an attachment other than image (for example .pdf) in Forum. NPR-27360: Hotfix for CQ-4257753</li>
  <li>Unpin or unfeature a forum post does not work if Author-Publish is set with MySQL DSRP. NPR-26125; Hotfix for CQ-4251520</li>
  <li>Collection components (forums, blogs, calendar, ideation, QnA) now have a property in the component dialog to enable/disable "Block UGC in Author Edit Mode", to allow/deny UGC load in WCM Edit mode. NPR-26978: Hotfix for CQ-4248161</li>
  <li>Tags Search does not work for localized search terms. NPR-26171: Hotfix for CQ-4249926</li>
  <li>Back button skips a page in the forum search. NPR-26950: Hotfix for CQ-4254804</li>
  <li>AEM instance running on default Http port (80) cannot reach the imsmanifest.xml. NPR-27173: Hotfix for CQ-4252211</li>
  <li>Unmark comment as an answer for QnA does not work if AEM Communities is set with DSRP. NPR-26247: Hotfix for CQ-4252232</li>
  <li>Cannot call Adobe Storage: 414 error - Long GET URI observed when users search /content/community-components/en/search.html and select author field as one of the filters for that search term. NPR-26643: Hotfix for CQ-4251303</li>
  <li>Dropdown value for DataCentreURL in ASRP configuration is changed from Dallas to Virginia (for VA6). NPR-26936: Hotfix for CQ-4254434</li>
  <li>Special characters in forum search return errors or no results. NPR-26930: Hotfix for CQ-4247744</li>
  <li>The number displayed for "Number of results" in forum search uses incorrect delimiter for English and German locales. NPR-27050: Hotfix for CQ-4248939</li>
  <li>Unread notifications do not increase beyond 21. NPR-26946, NPR-27480: Hotfix for CQ-4252829, CQ-4256939</li>
  <li>Pagination in the comments section of any component makes users scroll up to see the page content, on reaching a page through pagination. NPR-27032: Hotfix for CQ-4251228</li>
  <li>Community Site folder is not clickable on thumbnail image when viewing from admin console on AEM Author instance. NPR-26986: Hotfix for CQ-4254036</li>
  <li>The "mark all read" option marks only first 10 notifications as read and others remain unread until a page refresh. NPR-27037: Hotfix for CQ-4254058</li>
  <li>Pagination is not triggered for Ideation and the list of topics (or replies) gets longer unless it is reloaded. NPR-26193: Hotfix for CQ-4252104</li>
  <li>Other users' activities and deleted UGC visible on logging in with moderator credentials and adding "#social-activities" or "#tabs-2" at the end of the moderator's profile URL. Hotfix for CQ-4251355</li>
  <li>All the assigned tags cannot be removed from a blog article. NPR-26851: Hotfix for CQ-4253359 </li>
  <li>Relationships to UGC are not deleted on UGC deletion. NPR-27630: Hotfix for CQ-4258706</li>
  <li>Link for replies does not work on row click on Forum replies. NPR-27623: Hotfix for CQ-4256138</li>
  <li>User Subscription limit is limited to 1000. NPR-27614: Hotfix for CQ-4254689</li>
  <li>Editing a site and editing roles in the role settings throw Null Pointer Exception. NPR-27377; Hotfix for CQ-4255909</li>
</ul>
<h3>Translation</h3>
<ul>
<li>Translation preview does not work with the we.retail sample content. NPR-26727: Hotfix for CQ-4241179</li>
</ul>
<h3>UI - Foundation</h3>
<ul>
  <li>A NullPointerException is returned when attempting to download configurations after upgrading to AEM 6.4. NPR-27310: Hotfix for Granite-23573</li>
  <li>Proactive Backport for granite.platform.login fixes. NPR-26941</li>
  <li>Proactive Backport for granite.ui.content fixes. NPR-26294</li>
  <li>Number field component does not validate negative numbers on Internet Explorer 11. NPR-26701 </li>
  <li>Proactive Backport for granite.ui.coralui3 fixes. NPR-26662</li>
  <li>Proactive Backport for granite.ui.coralui3-aeon fixes. NPR-26666</li>
  <li>Proactive Backport for granite.ui.foundation.components fixes. NPR-27313</li>
  <li>Proactive Backport for granite.ui.commons fixes. NPR-26753</li>
  <li>Proactive Foundation UI Backports. NPR-26248</li>
</ul>
<h3>Integration</h3>
<ul>
<li>Modifications in AEM experiences created through the targeting engine are not published. NPR-24869: Hotfix for CQ-4247832</li>
<li>Cannot create multiple activities and experiences if their names include Japanese characters. NPR-27271: Hotfix for CQ-4256857</li>
<li>Update Launch API endpoint. NPR-26790: Hotfix for CQ-4254380</li>
<li>[Personalization] BrandsRetriever walks the entire tree. NPR-27060: Hotfix for CQ-4255790</li>
</ul>
<h3>WCM - Admin UI</h3>
<ul>
  <li>Added HTTP test for publishing/unpublishing a page with references and an UI test for Live Copy. Hotfix for CQ-4256894</li>
</ul>
<h3>WCM - Page Editor</h3>
<ul>
  <li>Edit toolbar gets disabled for components on the first edit. Hotfix for CQ-4253270</li>
</ul>
<h3>Forms</h3>
<p>The key highlights for AEM 6.4.3.0 forms are:</p>
<ul>
  <li>Enabled support for an array/list of objects with Dynamic Entity Substitution.</li>
  <li>Enabled FIPS compliance for Reader Extended workflow in Digital Signature, Reader Extensions, CryptoProvider, and TrustStore.</li>
  <li>Added PDF/UA support to XFA forms generated using Designer or Output Service.</li>
  <li>Enabled support for allowedPaths property on Adaptive forms templates.</li>
  <li>Added JBoss 7.1.4 support for AEM Forms 6.4.</li>
</ul>
<h3>Forms add-on package</h3>
<h4>Backend Integration</h4>
<ul>
  <li>Unable to populate form data model mappings based on dynamic entities in SOAP response. NPR-26428: Hotfix for CQ-4250639</li>
  <li>The value for _elementNamespace in form data model additional data, entered using Test UI, is not correctly reflected in the SOAP request. Hotfix for CQ-4255373</li>
  <li>A nullable property constraint is initialized with a default value and cannot be synced with FDM. Hotfix for CQ-4253873</li>
  <li>The default value for the nullable property is not set to True for OData data source. Hotfix for CQ-4253870</li>
</ul>
<h4>Adaptive Forms</h3>
<ul>
  <li>Unable to load sites and forms editor. NPR-26977; Hotfix for CQ-4249170</li>
  <li>Issues while adding an attachment to an adaptive form using the keyboard. NPR-25913; Hotfix for CQ-4249456</li>
</ul>
<h4>Forms - Interactive Communication</h4>
<ul>
  <li>Unable to move a panel that has been added using the Add child panel option in the content tree in Web channel of Interactive Communication and in adaptive forms. Hotfix for CQ-4253915</li>
  <li>Table names are displayed instead of the title of the FDM association in the Data Sources section of Print channel. Hotfix for CQ-4253669</li>
  <li>The isUseXFABullets() function is not disabled in PrintChannelRenderOptions class and is available in client SDK. Hotfix for CQ-4246583, CQ-4252700</li>
</ul>
<h4>Correspondence Management</h4>
<ul>
  <li>Javadocs for 6.4 does not contain the com.adobe.dbforms.* package and the corresponding classes. Hotfix for CQ-4253200</li>
  <li>CCR UI displays a default junk value for the date field in case there is no input from the test data XML. Hotfix for CQ-4252041</li>
  <li>If a letter contains a list module, the space between bullet and text is lost while generating PDF from the letter. Hotfix for CQ-4250588</li>
</ul>
<h4>Forms Manager</h4>
<ul>
  <li>Enabled support for allowedPaths property on Adaptive forms templates. NPR-26598: Hotfix for CQ-4255892</li>
</ul>
<h4>Forms - Workflow</h4>
<ul>
  <li>If braces are included in the task name while executing the Forms workflow, an exception is displayed in the logs. Hotfix for CQ-4256626</li>
  <li>Unable to open a Search template in AEM Forms workspace. Hotfix for CQ-4255651</li>
</ul>
<h4>Mobile Forms</h4>
<ul>
  <li>The exit notification does not display while exiting the date field in AEM Forms rendered as HTML in Internet Explorer or Chrome. NPR-26483: Hotfix for CQ-4239352</li>
  <li>Dates contained in the XML when processing begins causes the forms to throw up a validation error when the user tries to leave the form. NPR-26787: Hotfix for CQ-4251211</li>
</ul>
<h3>Forms JEE installer</h3>
<h4>PDF Generator Service</h4>
<ul>
  <li>Unable to display Standards Reporting and Compliance settings for PDF Generator. NPR-26715: Hotfix for CQ-4253384</li>
  <li>convertpdf binary file is missing in the AIX Forms add-on package, which causes failure while invoking the PDFA service. Hotfix for CQ-4257873</li>
</ul>
<h4>Document Services</h4>
<ul>
  <li>Add FIPS compliance for RE workflow in Digital Signature, Reader Extensions, CryptoProvider, and TrustStore. NPR-27495: Hotfix for CQ-4257572</li>
  <li>The conversion fails while running AssemblerService.toPDFA service in a loop. NPR-26354: Hotfix for CQ-4248656</li>
  <li>Unable to validate the PDFs compliance correctly based on PDF/A-1b standards. NPR-26286: Hotfix for CQ-4227539</li>
  <li>Out of memory issues while upgrading AEM Forms from 6.1 SP2 CFP5 to CFP13. NPR-26285: Hotfix for CQ-4244379</li>
  <li>Unable to validate the PDFs compliance correctly based on PDF/A standards. NPR-26272: Hotfix for CQ-4248823</li>
</ul>
<h4>Forms - Foundation JEE</h4>
<ul>
  <li>Added JBoss 7.1.4 support for AEM Forms 6.4. NPR-27331; Hotfix for CQ-4255601</li>
</ul>
 <h3>Feature Packs included</h3>
 <ul>
  <li>Enabled support for an array/list of objects with Dynamic Entity Substitution. NPR-26590: Hotfix for CQ-4254655</li>
  </ul>
   <h3>OSGI Bundles and Content Packages Included</h3> 
 <div> 
  <p>List of OSGi bundles included in AEM 6.4.3.0</p> 
  <p><a alt="bundle-list-6430.txt" href="assets/bundle-list-6430.txt" status="changing">Get File</a></p> 
  <p> List of Content Packages included in AEM 6.4.3.0</p> 
  <p><a alt="content-package-list-6430.txt" href="assets/content-package-list-6430.txt" status="changing">Get File</a></p> 
 </div> 
</div>

<div class="details"> 
 <h3 class="summary">AEM 6.4.2.0</h3> 
 <p>AEM 6.4.2.0 is an important update that includes performance, stability, security and key customer fixes and enhancements released since the general availability of AEM 6.4 in <strong>April 2018.</strong></p> 
 <p>It is also cumulative which means that 6.4.2.0 includes all AEM 6.4 service packs release before it.</p> 
 <p>Some of the key highlights of AEM 6.4.2.0 are:</p> 
 <ul> 
  <li>The built-in repository (Apache Jackrabbit Oak) is updated to version 1.8.7.</li> 
  <li>Added support for HTML Template Language (HTL) Specification 1.4 features</li> 
  <li>Added support for MongoDB Enterprise 3.6.</li> 
  <li>The Sites Page Editor adds support for in-context editing and composition with client-side components build in React or Angular in combination with <a href="/help/sites-developing/spa-walkthrough.md">AEM's SPA Editor JS SDK</a>. </li> 
  <li>Content Fragments enhancements: added the capability to annotate in text fields, and side-by-side comparison of versions.</li> 
  <li>Added <a href="/help/assets/aem-assets-adobe-stock.md" target="_blank">integration with Adobe Stock</a> so that users can search, preview, save and license Adobe Stock assets directly from AEM user interface. For more detailed information, see <a href="https://helpx.adobe.com/experience-manager/kt/assets/using/stock-assets-feature-video-use.html">https://helpx.adobe.com/experience-manager/kt/assets/using/stock-assets-feature-video-use.html</a>.</li> 
  <li>Assets added support for dynamic conditional 
   <code>
     metaschema and the a 
   </code>Ability to set a metadata schema for asset folders. </li> 
  <li>Added configuration in each component to enable/disable the folder thumbnail creation/update functionality.</li> 
  <li>Image Editor enhancements on page authoring.</li> 
  <li>Regression fix in Communities for 
   <code>
     scoring 
   </code> event not getting handled properly in case of selected answer getting deleted. </li> 
  <li>Revised the maximum search results limit for 
   <code>
     solr 
   </code> to MAX_INT-10000.</li> 
  <li>Transaction Flush job is started only on the first call to 
   <code>
     storeTransaction 
   </code>.</li> 
  <li>"Select All" button is now available in Card View and Column View.</li> 
  <li>Accessibility improvements in 
   <code>
     CoralUI 
   </code>.</li> 
  <li>Improved Coral.Keys handling.</li> 
  <li>Updated moment.js to 2.22.2</li> 
  <li>Updated jquery- 
   <code>
     ui 
   </code> to 1.12.1</li> 
  <li>Introduced foundation- 
    <code>
      workflowstatus 
    </code> 
   <code>
     component 
   </code>.</li> 
  <li>Updated GCC to 
   <code>
     latest 
   </code> version.</li> 
  <li>Move SAML to new external IDP synchronization.</li> 
 </ul> 
 <h3>Assets</h3> 
 <ul> 
  <li>Subassets generation for pptx file does not contain any images and thumbnails. NPR-24286: Hotfix for CQ-4217986</li> 
  <li>migrateAllAssets - Add support for batch processing and improve AEM method that adds UUID to old assets. NPR-24861: Hotfix for CQ-4242863 and CQ-4247874</li> 
  <li>Performance issue with thumbnail generation. NPR-24693: Hotfix for CQ-4246960</li> 
  <li>[Touch UI] The “options predicate” component remains blank when added to the Asset Share publisher page. NPR-24643: Hotfix for CQ-4245295</li> 
  <li>[Workflow] Smart Tag Assets doesn't process through the proxy configuration. NPR-25840: Hotfix for CQ-4248202</li> 
  <li>[Omnisearch] removing filetype:image from search criteria does not remove the image type. NPR-25232: Hotfix for CQ-4248280</li> 
  <li>When trying to move a file to a different folder, folders with apostrophe in their name are not displayed. NPR-25125: Hotfix for CQ-4248660</li> 
  <li>Slider in Subasset page does not work correctly when the language preference set to other than English. NPR-25274: Hotfix for CQ-4248489</li> 
  <li>Issue with metadata export csv file when opened on machines having European number format. NPR-26009: Hotfix for CQ-4250677</li> 
  <li>Create button is not available on asset folder selection without "delete" permission. NPR-25788: Hotfix for CQ-4250140</li> 
  <li>[Backport] Accessibility enhancements: Duplicate-id: id attribute value must be unique, Label: Form elements must have labels and Link-name: Links must have discernible text. NPR-24252: Hotfix for CQ-4250905, CQ-4250906, CQ-4250907</li> 
  <li>Uploading a csv with fields separated with "," fails for European countries. NPR-25549: Hotfix for CQ-4249931</li> 
  <li>[Brand Portal] Subassets of a multipage pdf file do not publish when an asset is published. NPR-25991: Hotfix for CQ-4245162</li> 
  <li>Publish later functionality for AEM to Brand Portal replication. NPR-25911: Hotfix for CQ-109139</li> 
  <li>Publishing and un-publishing the private collection by non-admin users results in a NPE. NPR-25906: Hotfix for CQ-4250594</li> 
  <li>Disable publish of content fragment and forms schemas to Brand Portal. NPR-24176, NPR-26004: Hotfix for CQ-4251592, CQ-4252026</li> 
  <li>[Dynamic Media] Updated DM viewers to 5.10.1 release which enables check for duplicate names on Image Preset page. Refer to <a href="/help/release-notes/sp-release-notes.md#update-dynamic-media-viewers">Update Dynamic Media Viewers (5.10.1)</a>. NPR-24403: Hotfix for CQ-4247554</li> 
  <li>Javascript error in browser console in column view on selecting an asset or folder. NPR-25939: Hotfix for CQ-4250228</li> 
  <li>[Column view] Unable to identify tasks as the key file shows up as blank white entry. NPR-25903: Hotfix for CQ-4246307</li> 
 </ul> 
 <h3>Sites</h3> 
 <ul> 
  <li>Query of 
   <code>
     datasource 
   </code>.jsp on AEM 6.2 is different from AEM 6.4. NPR-24968: Hotfix for CQ-4244235</li> 
  <li>[Classic UI] Unable to add tags to pages. NPR-25255, NPR-25612: Hotfix for CQ-4249615</li> 
  <li>HTML Template Language Specification 1.4 features backported to AEM 6.4.2.0 NPR-24585</li> 
  <li>Wrong inheritance on 
   <code>
     local 
   </code> component after copying a live copy page. NPR-25920: Hotfix for CQ-4236737, CQ-4248957</li> 
  <li>ON/OFF time is stored in crx/de but doesn't fetch the same in page properties UI console. NPR-25154: Hotfix for CQ-4243431</li> 
  <li>Styles System breaks dialog's initial properties values. NPR-25648: Hotfix for CQ-4250073</li> 
  <li>When defining a cq:tagName property in a cq:htmlTag node, the tag name is not considered if the component is included via JSP. NPR-24154: Hotfix for CQ-4244120</li> 
  <li>For a nested parsys components, always the first (with least nested path) satisfying design is applied from multiple available components. For more information, see <a href="/help/sites-developing/page-templates-static.md">Design Path Resolution</a>. NPR-24973: Hotfix for CQ-4246276</li> 
  <li>When pasting text into an RTE component, a pop-up dialog is displayed, but not rendered properly. NPR-24895: Hotfix for CQ-4245901</li> 
  <li>[RTE] Performance issues with mandatory field indicator. NPR-24894: Hotfix for CQ-4241895</li> 
  <li>[Page component] Adding a component to Parsys gets cropped off from right and comes out the device frame width. NPR-25536: Hotfix for CQ-4238224</li> 
  <li>Plaintext editor sends un-trimmed data and adds extra spaces. NPR-25312: Hotfix for CQ-4249006</li> 
  <li>While opening the component using inlide mode, plugins loaded previously are not visible the second time. NPR-24610: Hotfix for CQ-4236850</li> 
  <li>Loading an XF in editor view by copy/paste does not load the master variation automatically. NPR-24841: Hotfix for CQ-4248037</li> 
  <li>Wrong HTML structure in siteadmin / damadmin breaks IE11. NPR-24686: Hotfix for CQ-4246363, CQ-4248402</li> 
  <li>[Manage Publication Wizard] Calendar for activation date at Options step does not open after some actions at Scope step. NPR-25681: Hotfix for CQ-4250205</li> 
  <li>Classic UI does not work to edit CUG due to deprecation. NPR-25075: Hotfix for 4241823</li> 
  <li>Create option unavailable to create experience fragments. NPR-26053: Hotfix for CQ-4249923</li> 
  <li>XF variation is getting activated twice hence, generating duplicate IDs for the same item. NPR-24179: Hotfix for CQ-4245093</li> 
  <li>Foundation table is vulnerable to Stored Cross Site Scripting. NPR-25185: Hotfix for CQ-4240760</li> 
  <li>'Invalid recursion selector value' error while migrating a component from AEM 6.2.1.13 to AEM 6.4. NPR-24146</li> 
 </ul> 
 <h3>WCM - Page Editor</h3> 
 <ul> 
  <li>Multiple stacked Parsys due to long-running queries (more than 6) makes AEM sluggish. Hotfix for CQ-4240247</li> 
  <li>JS error when adding empty cq:tagName in cq:htmlTag node. Hotfix for CQ-4251852</li> 
  <li>Update EditableActions based on the columnClassNames relocation. Hotfix for CQ-4250781</li> 
  <li>Expose resource and model paths using a single property and attribute. Hotfix for CQ-4251255</li> 
  <li>Revert export.json API breaking changes. Hotfix for CQ-4251854</li> 
  <li>[Editable SPA] Release candidate for 1.0.0. Hotfix for CQ-4251991</li> 
  <li>Edit toolbar gets disabled for other components on editing any one component. Hotfix for CQ-4253270</li> 
 </ul> 
 <h3>Integration</h3> 
 <ul> 
  <li>Library and Download URL fields should be editable. NPR-24804: Hotfix for CQ-4246864</li> 
  <li>Issue with multiple DTM configurations. NPR-24685: Hotfix for CQ-4247293</li> 
  <li>Add support for asynchronous deployment for hosted client libraries. NPR-25716: Hotfix for CQ-4245745</li> 
  <li>Targeted component with missing corresponding offer renders the whole page and instead of an empty targeted component, another full rendition of the page is added. NPR-25273: Hotfix for CQ-4248003</li> 
  <li>Target engine (mbox.js, at.js) does not use mangled URLs and uses URLs containing colons which might fail with certain deployments. NPR-25339: Hotfix for CQ-4237854</li> 
  <li>[Launch] LibraryDownloadProcess stores wrong libraryUri value. NPR-25330: Hotfix for CQ-4250006</li> 
 </ul> 
 <h3>Platform</h3> 
 <ul> 
  <li>Reindexing loop | NPE while performing the BinaryTextExtraction during inplace upgrade from 6.3 to 6.4. Hotfix for Granite - 21677</li> 
  <li>Cross-boundary override of internal marked path /libs/cq/cloudserviceconfigs/templates/configpage/jcr:content - Issue while running pattern detector. NPR-25036: Hotfix for CQ-4248597</li> 
  <li>Log entries not written due to NPE in LogEntryImpl. NPR-25627: Hotfix for Granite-22383</li> 
  <li>Replication of delete event doesn't check for rights. NPR-25679: Hotfix for CQ-4241234</li> 
  <li>Add STARTTLS support in "Day CQ Mail Service.” NPR-25611: Hotfix for CQ-4249924</li> 
  <li>Proactive backport for granite.platform.login fixes to improve accessibility. NPR-25176: Hotfix for Granite 21746 and Granite-21309</li> 
  <li>[AEM 6.4] Error while re-building package and re-installing it. NPR-25173: Hotfix for CQ-4247939</li> 
  <li>Remove default MERGE_PRESERVE aclHandling. NPR-24593: Hotfix for Granite-21889</li> 
  <li>Content-Type is not propogated and missing in the response after applying the ContentDispositionFilter twice. NPR-24175: Hotfix for Sling-7525</li> 
  <li>Package Manager status wrong after upgrade to AEM 6.4 branch. NPR-24551: Hotfix for Granite-21750</li> 
  <li>AMS instance - Error logs analysis. Hotfix for CQ-4249567</li> 
 </ul> 
 <h3>Security</h3> 
 <ul> 
  <li>SAML re-login redirects to logout page using Okta IDP. NPR-25523: Hotfix for GRANITE-22364</li> 
  <li>IMS Authentication via OAK external IDP OAuth Provider configs disables the user created in AEM. NPR-25301: Hotfix for Granite-22363</li> 
 </ul> 
 <h3>MAC - Test &amp; Target Integration</h3> 
 <ul> 
  <li>[Targeting] Text component error during Targeting. Hotfix for CQ-4233343</li> 
 </ul> 
 <h3>Communities</h3> 
 <ul> 
  <li>[File Library] Downloading assets with blank spaces from causes format issues. NPR-24260: Hotfix for CQ-4245159</li> 
  <li>Fixes to several Adobe Social issues. NPR-24247: Hotfix for CQ-4245054, CQ-4245120, CQ-4245296</li> 
  <li>Infiinite scroll for members and groups console fail in case author publish run on different context paths. NPR-24437: Hotfix for CQ-4246013</li> 
  <li>The post does not return to the unanswered state even on removing from the answered state and the score does not decrement. NPR-24419: Hotfix for CQ-4245797, CQ-4245932 </li> 
  <li>Events added using calendar functionality in communities outputs wrong values. NPR-24883: Hotfix for CQ-4244056</li> 
  <li>[Communities Forum] Issues with Pagination click and Page load behavior. NPR-24880: Hotfix for CQ-4246109</li> 
  <li>[Chrome] Timezone conversions fail on communities events. NPR-24881: Hotfix for CQ-4247115</li> 
  <li>Unable to render embedded object in Email. NPR-24999: Hotfix for CQ-4248022</li> 
  <li>Automoderation sequence should be executed on UGC update in addition to UGC creation. NPR-25892: Hotfix for CQ-4251399</li> 
  <li>Modal dialog responsiveness on Groups. NPR-25623: Hotfix for CQ-4248805</li> 
  <li>Solr exception is thrown on content deletion. NPR-25869: Hotfix for CQ-4248908</li> 
  <li>Paginated links to threads with lots of posts does not work on Notifications. NPR-25678: Hotfix for CQ-4243038</li> 
  <li>Time values in search result display server time instead of the client's time zone. NPR-25594: Hotfix for CQ-4248986</li> 
  <li>[Forum comments] Browser back button is not working as expected. NPR-25205: Hotfix for CQ-4248573</li> 
  <li>[Search results] Browser back button is not working as expected. NPR-25214: Hotfix for CQ-4248574</li> 
  <li>Null is returned when overlaying communitygroupmemberlist component. NPR-25228: Hotfix for CQ-4248523</li> 
  <li>[Communities Calendar] ClassCastException is generated while saving the event with the new Cover image. NPR-25167: Hotfix for CQ-4248662</li> 
  <li>[Communities] Messages getting truncated. NPR-25326</li> 
  <li>[AEM Publish] Scorm Resource fails with context path and shows blank screen. NPR-26155: Hotfix for CQ-4251942</li> 
  <li>[MSRP] The newly created calendar is saved partially throwing NPE in the error log. NPR-26071: Hotfix for CQ-4250531</li> 
  <li>Forum/Topic pagination only gets updated when the page is refreshed. NPR-26070, NPR-25965: Hotfix for CQ-4249509</li> 
  <li>[Q&amp;A Forum] Unable to navigate to previous page on opening a direct link to a comment. NPR-26069: Hotfix for CQ-4251699</li> 
  <li>Upload image in Create group does not work on mobile. NPR-26172: Hotfix for CQ-4251703</li> 
  <li>[Messaging] When using DSRP, name of message receiver is always shown as "Unknown". NPR-26056: Hotfix for CQ-4251397</li> 
  <li>Enablement Scorm Resource completion status label appears empty in UI. NPR-26034: Hotfix for CQ-4249994</li> 
  <li>While creating a new community group, a duplicate community group is created on an active/active mongoMK cluster. NPR-26032: Hotfix for CQ-4245884</li> 
  <li>[Author] Group creation wizard takes too long to load/create a group within the wizard. NPR-26031: Hotfix for CQ-4244966</li> 
  <li>Parsys disappears on adding an include statement in the hbs script. NPR-25908: Hotfix for CQ-4250489</li> 
  <li>On enabling 'Allow privileged', the privileged members should only be able to compose for users who are community members. NPR-25877: Hotfix for CQ-4248450</li> 
  <li>Deeplinks blocked for enablement. NPR-25966: Hotfix for CQ-4251478</li> 
  <li>Forum pagination does not get updated dynamically on removal of replies. NPR-25970: Hotfix for CQ-4248975, CQ-4252843</li> 
  <li>Auto Scroll and highlighting does not work on calendar and filelib events in case of nested comments. NPR-25958: Hotfix for CQ-4251471</li> 
  <li>[DSRP] Direct/Deep Link performance degrading with high amounts of User Generated Content. NPR-25957: Hotfix for CQ-4251470</li> 
  <li>Unable to modify the properties of Allow Privileged Members and Privileged members. NPR-26014: Hotfix for CQ-4244592</li> 
  <li>Mark all as read resets the notification counters for all community pages. NPR-25931: Hotfix for CQ-4248612</li> 
  <li>Edit ITs failing for DSRP. NPR-25929: Hotfix for CQ-4251382</li> 
  <li>Email ITs failing due to NPE while building email templates. NPR-26039: Hotfix for CQ-4250962</li> 
  <li>Forum thread issues when embedding images with very high resolution. NPR-26037: Hotfix for CQ-4244453, CQ-4253099</li> 
  <li>Time displays switches when server time zone differs from the user time zone. NPR-26036: Hotfix for CQ-4248751</li> 
  <li>Attaching a file twice with same name to a forum post leads to server error. NPR-24172: Hotfix for CQ-4244367</li> 
  <li>Backport performance fixes - Group pagination on author and publish, Group search on author, Avoiding serialization of replies for journal,calendar and ideation and lazy loading for getting group membership (invite/uninvite) button for each group while viewing the group listing page. NPR-24538: Hotfix for CQ-4246515</li> 
  <li>Enablement Resources are not visible on author. Hotfix for CQ-4252618</li> 
  <li>Notifications do not get generated for thread from unknown user. Hotfix for CQ-4245132</li> 
  <li>Group search does not appear on left rail. Hotfix for CQ-4252621</li> 
  <li>[Author] Pagination is not working for Groups Console. Hotfix for CQ-4242786</li> 
  <li>jQuery UI upgrade. Hotfix for CQ-4248894</li> 
  <li>Upgrade to latest SCORM 2017.1 version. NPR-25675: Hotfix for CQ-4240671</li> 
  <li>The "Compose on Behalf" fields is visible to non-community users. NPR-25331: Hotfix for CQ-4247858</li> 
  <li>Post is still visible on UI even after deletion and gives error on console. NPR-26290: Hotfix for CQ-4252803</li> 
  <li>[Site settings] Umable to save changes done to Roles. NPR-26274: Hotfix for CQ-4252187</li> 
  <li>[Security Vulnerability] Account Takeover due to JSON Web Token Misconfiguration. NPR-26458: Hotfix for CQ-4253314</li> 
  <li>Pagination is not reset upon removal of replies. NPR-26326: Hotfix for CQ-4252997</li> 
  <li>Attachment image is not displayed in Drafts while editing. Hotfix for CQ-4253360</li> 
  <li>Page is not refreshing while attaching attachment in Relational Database (DSRP). Hotfix for CQ-4253084</li> 
  <li>Groups are not working inside Enablement site resource. Hotfix for CQ-4252975</li> 
  <li>Prerequisites Learning Paths are not persisted in Enablement. Hotfix for CQ-4252948</li> 
 </ul> 
 <h3>Workflow</h3> 
 <ul> 
  <li>Workflow launcher UI does not display past 41 launcher configurations and triggers a javascript error in the console. NPR-25028: Hotfix for CQ-4247604</li> 
  <li>Editing a legacy workflow without editing its launcher causes multiple workflows to get created on any workflow which contains an Activate Page/Asset step. NPR-25870: Hotfix for CQ-4250896</li> 
  <li>Incorrect link in workflow payload if page has a metadata node. NPR-25916: Hotfix for CQ-4250733</li> 
 </ul> 
 <h3>Translation</h3> 
 <ul> 
  <li>Fixed that importing translated project makes two concurrent POST requests, hence, causing error. NPR-24889: Hotfix for CQ-4247638</li> 
  <li>Fixed that when creating translation project for multiple languages, all the pages for the same language get added to the same job. NPR-25091: Hotfix for CQ-4246112</li> 
  <li>Fixed that in some cases, translation job only list the top 40 pages. NPR-25974: Hotfix for CQ-4248661</li> 
  <li>Fixed that DataPicker component (Coral2) not changing the year. NPR-24466: Hotfix for Granite-21893</li> 
 </ul> 
 <h3>UI - Foundation</h3> 
 <ul> 
  <li>Proactive Foundation UI Backports. NPR-24344, NPR-24345, NPR-25176, NPR-25095, NPR-24332, NPR-25653, NPR-25932, NPR-25935, NPR-25976 </li> 
  <li>[Design Importer] Importing a page does not import the js, 
   <code>
     css 
   </code>. NPR-25203: Hotfix for Granite-22236</li> 
  <li>Proactive Foundation UI Backports to improve the stability of the product. NPR-24334</li> 
 </ul> 
 <h3>MAC - Test &amp; Target Integration</h3> 
 <ul> 
  <li>Second page of PersonalizationWizard ( launched by "Start Targeting" ) is blank and throws console errors. Hotfix for CQ-4253277</li> 
 </ul> 
 <h3>Experience Fragments</h3> 
 <ul> 
  <li>Merged Experience Fragments/Target Integration to AEM 6.4.2.0. Hotfix for CQ-4248653</li> 
 </ul> 
 <h3>Content Fragment Management</h3> 
 <ul> 
  <li>Content Fragments annotations, and side-by-side comparison of Content Fragment versions. Hotfix for CQ-4247148</li> 
 </ul> 
 <h3>DAM - General</h3> 
 <ul> 
  <li>“Checked out by" filter not working correctly within search. Hotfix for CQ-4247070</li> 
  <li>On performing asset update workflow, the asset language copy and its thumbnail becomes blank. Hotfix for CQ-4250641</li> 
  <li>Duplicate-id: id attribute value must be unique. Hotfix for CQ-4250905</li> 
  <li>Label: Form elements must have labels. Hotfix for CQ-4250906</li> 
  <li>Link-name: Links must have discernible text. Hotfix for CQ-4250907</li> 
  <li>Port Folder Metadata Template Migration JMX and ServiceUserMapping. Hotfix for CQ-4252947</li> 
  <li>WebdriverIO Tests not running in release/640 branch of CQ/dam. Hotfix for CQ-4252749</li> 
  <li>Links to moved assets are not refactored if link is published. Hotfix for CQ-4245756</li> 
 </ul> 
 <h3>DAM - Viewers</h3> 
 <ul> 
  <li> Intermittent error on loading video with new viewers 5.10.1. Hotfix for CQ-4250562</li> 
 </ul> 
 <h3>DAM-Brand Portal</h3> 
 <ul> 
  <li>Unpublish collection from Brand Portal is failing with error. Hotfix for CQ-4245990</li> 
  <li>Unable to unpublish image presets from Brand Portal. Hotfix for CQ-4246140</li> 
  <li>Subassets of a multi page pdf file do not get published when an asset is published. Hotfix for CQ-4245162</li> 
 </ul> 
 <h3>DAM - DMClient</h3> 
 <ul> 
  <li>When publishing a video asset to YouTube, the tags that result in YouTube include the tag's full path. Hotfix for CQ-4245549</li> 
  <li>[Opt-out and Opt-In upgrades] Issue with Viewer CSS redirect. Hotfix for CQ-4247854</li> 
  <li>Unable to create/edit viewer preset as non-member of 'administrators' group. Hotfix for CQ-4247618</li> 
  <li>[6.4.1.0] Adding multiple videos in multiple parsys breaks the video player. Hotfix for CQ-4248517</li> 
  <li>Renaming &amp; moving asset within an Image Set renders editing impossible. Hotfix for CQ-4248434</li> 
  <li>Publish large videos to YouTube throws time out messages. Hotfix for CQ-4237831</li> 
  <li>[List View] The Asset Picker/Selector's user interface changes to all gray and is disabled for the user. Hotfix for CQ-4237817</li> 
  <li>[Vertical Zoom] Css fails to load with a 404 error. Hotfix for CQ-4236508</li> 
  <li>Trying to download an asset with percent (%) character in the asset name results in an empty archive. Hotfix for CQ-4250558</li> 
  <li>[Card View] No processing indicator is displayed when using Copy and Paste on a Video Asset. Hotfix for CQ-4249037</li> 
  <li>[Upgrade from 6.3.2 to 6.4] Pre-Upgrade Image Presets are shown as "Unpublished" on Renditions page but do not yield URL button when selected. Hotfix for CQ-4240406</li> 
  <li>Technical Debt/Minor Enhancements. Hotfix for CQ-4240648</li> 
  <li>The Asset Selector (or Asset Picker) does not show all Assets from the folders available. Hotfix for CQ-4218414</li> 
  <li>Image Preset with no height displays images with incorrect size. Hotfix for CQ-4246546</li> 
  <li>[Multi Page Assets] UI breaks on clicking on annotations. Hotfix for CQ-4251434</li> 
  <li>Upgrading from 6.3 to 6.4 and later the Analytics preset, a new report suite and analytics preset is created losing the user's older reporting data. Hotfix for CQ-4244529</li> 
  <li>[Manage Publication Wizard] List of Assets appear to be empty when trying to publish or unpublish. Hotfix for CQ-4251881</li> 
  <li>When choosing Viewers after viewing the Set Members, AVS videos fail to playback. Hotfix for CQ-4205308</li> 
  <li>Pre-Upgrade Video Processing Presets cannot have a new Video Encoding Preset added nor edit the existing Encoding Preset(s). Hotfix for CQ-4240407</li> 
  <li>Image presets are not applied to downloaded dynamic renditions. Hotfix for CQ-4249862</li> 
  <li>The select all button does not work correctly on Viewer Preset listing page. Hotfix for CQ-4252462</li> 
  <li>Video Profiles: Select All button is non-functional. Hotfix for CQ-4253076, CQ-4251447</li> 
  <li>SP2 Validation Pass - Smoke Pass. Hotfix for CQ-4251639</li> 
 </ul> 
 <h3>DAM - DMServices</h3> 
 <ul> 
  <li>Dynamic Media Renditions failed to generate for EPS file. Hotfix for CQ-4243688</li> 
 </ul> 
 <h3>Granite</h3> 
 <ul> 
  <li>Typo in bundle SymbolicName leads to duplicate bundle. Hotfix for Granite - 22155</li> 
  <li>CUGConfiguration may not pick up CugExclude. Hotfix for Granite - 21109</li> 
  <li>Restarting Adobe Granite Workflow Core re-runs the workflow steps from the middle creating unnecessary workflows. NPR-25057: Hotfix for Granite-22218</li> 
  <li>JcrResourceBundle does not correctly support multiple base names. NPR-25245: Hotfix for Granite-22317</li> 
  <li>On installation of content packages, the ACLs are grouped by principal, therefore, breaking the permission model. NPR-24583: Hotfix for Granite-21591</li> 
  <li>Update Jetty to 9.4.11 to fix vulnerabilities. NPR-25030: Hotfix for Granite-22120</li> 
 </ul> 
 <h3>Forms</h3> 
 <p>The key highlights for AEM 6.4.2.0 forms are:</p> 
 <ul> 
  <li>Added new property for Queues to be updated without refreshing the browser.</li> 
  <li>Added capability for the user to use the same WSDL file for multiple service.</li> 
  <li>Removed the unsupported timestamp pattern from the datepicker dropdown.</li> 
  <li>Added support for underlaying xfaf and pdf in OSGI.</li> 
  <li>Added support to use the <a href="/help/forms/using/transaction-reports-overview.md">transaction reports capability</a> at on-premise deployments.<br /> </li> 
  <li>Added code to not display child var in condition rule editor.</li> 
 </ul> 
 <h3>Forms add-on package</h3> 
 <h4>Transaction Reporting</h4> 
 <ul> 
  <li>Update Transaction Reporting configuration with the importance of reverse-replication configured on a Publish server. NPR-26050: Hotfix for CQ-4246650</li> 
  <li>Delayed initialization of Periodic Flush Job. NPR-25968: Hotfix for CQ-4245024</li> 
  <li>Transaction Recording fails with Null Pointer Exception. Hotfix for CQ-4247302</li> 
 </ul> 
 <h4>Forms - Workflow</h4> 
 <ul> 
  <li>[HTML Workspace] When a user claims a task, count of queue is refreshed for that particular user but not for other users unless the page is refreshed. This issue has been fixed by a new property. To configure this new property to your AEM instance, refer to <a href="/help/release-notes/sp-release-notes.md#configuration-settings-required-for-npr">Configuration Settings</a>. NPR-24536: Hotfix for CQ-4233665</li> 
  <li>Unable to load large form in the AEM Forms App on 6.4. NPR-24463: Hotfix for CQ-4245091</li> 
  <li>Issue in Mobile Workspace App when trying to view the shared task. NPR-25177: Hotfix for CQ-4248733</li> 
  <li>Inconsistent validation Behavior between Web and APK. NPR-25670: Hotfix for CQ-4248178</li> 
  <li>When a call to a web service is made an HTML5 form opened within the client, it fails and an error message is returned. NPR-26048: Hotfix for CQ-4244716</li> 
  <li>Issue while calling service in AEM forms Windows app 6.3. NPR-26468: Hotfix for CQ-4252341</li> 
 </ul> 
 <h4>Mobile Forms</h4> 
 <ul> 
  <li>[Formset] SSN and Mobile field validation issue when previewed. NPR-24458: Hotfix for CQ-4244983</li> 
  <li>Data is not shown with prefilling of multi-line fields in HTML preview. NPR-24549: Hotfix for CQ-4244212</li> 
  <li>Data gets lost when the script is evaluated on a multi-line field. NPR-25333, Hotfix for CQ-4249610</li> 
 </ul> 
 <h4>Forms - Interactive Communication &amp; Correspondence Management</h4> 
 <ul> 
  <li>Sync fails on IC with Basic Template and Reference IC Print Template. NPR-24912</li> 
  <li>[CCR] Validators don't work for fields/variables. Hotfix for CQ-4245047</li> 
  <li>Data Model Object icon disappears on Text Edit toolbar intermittently. Hotfix for CQ-4245122</li> 
  <li>Exception logs appear on copied IC if original IC is deleted. Hotfix for CQ-4249378</li> 
  <li>In the letter rendition, the condition does not evaluate to true even when the data is correct. Hotfix for CQ-4245944</li> 
  <li>Auto-generated components are not highlighted on selecting from Content tree. Hotfix for CQ-4246178</li> 
  <li>Issues while opening Web Channel Template editor. Hotfix for CQ-4248182</li> 
  <li>Unable to change the order of assets added as the up/down arrows remain disabled. Hotfix for CQ-4252042</li> 
  <li>Unable to update properties of Condition module. Hotfix for CQ-4247909</li> 
  <li>UX of "Cancel Inheritance" dialog when user re-arranges an Object in Web Channel needs to be improved. Hotfix for CQ-4241076</li> 
  <li>Data in the letter corresponding to bindings defined in XDP is not populated on using direct letter URL. Hotfix for CQ-4245833</li> 
  <li>[Caching issue] Synchronization of web channel does not reflect changes made to layout fragments, Text fragment of print channel. Hotfix for CQ-4251460</li> 
  <li>Unable to update Layout fargment and DD properties. Hotfix for CQ-4247830</li> 
  <li>[CCR] Draft reloading is failing due to XML parsing. Hotfix for CQ-4250950</li> 
  <li>[IC Editor] "Edit Fragment" button should be more discoverable. Hotfix for CQ-4244694</li> 
  <li>[XDP] A blank screen is displayed on adding a layout fragment in the new created subform. Hotfix for CQ-4248810</li> 
  <li>DocumentFragment-master-DeployWithServerSideTests test failure. Hotfix for CQ-4245496</li> 
  <li>Text module variable Instance duplicated in Condition module. Hotfix for CQ-4252128</li> 
  <li>PDF preview URL do not show transaction reporting on publish. Hotfix for CQ-4246158</li> 
  <li>IC Sync related issues with Print Channel to Web Channel Syncing. Hotfix for CQ-4251505</li> 
  <li>EXM Code clean up: Remove LocalFunctionMapper. Hotfix for CQ-4243265</li> 
  <li>To correct the resource type of TableHeader of IC's webChannel table component. Hotfix for CQ-4251821</li> 
  <li>[IC Editor] Usability issues. Hotfix for CQ-4241081</li> 
  <li>Print channel subform does not show insert functionality. Hotfix for CQ-4252994</li> 
  <li>Keep changes sync fails post removing FDM node or Variable placeholder. Hotfix for CQ-4253178</li> 
  <li>[Template Editor] Basic template shows header / footer additional drag drop areas and the screen flickers on opening Web Channel. Hotfix for CQ-4253323</li> 
  <li>Auto-generated components do not get highlighted on selecting from the Content tree. Hotfix for CQ-4246178</li> 
 </ul> 
 <h4>Document Services</h4> 
 <ul> 
  <li>[Form Service] OSGI lacks support for XFAF. NPR-25181, Hotfix for CQ-4251313</li> 
  <li>The characters in the heading of the assembled PDF file are coming to be garbled. NPR-25113: Hotfix for CQ-4244682</li> 
 </ul> 
 <h4>Adaptive Forms</h4> 
 <ul> 
  <li>Submit Action as Send Mail throws an exception with CC/BC fields blank. NPR-25019: Hotfix for CQ-4243039</li> 
  <li>Unable to use the OOTB AEM Form component due to inefficient query. NPR-25065: Hotfix for CQ-4247256</li> 
  <li>Remove sling:orderBefore from dialog nodes of guideImageChoiceComponent. Hotfix for CQ-4245013</li> 
  <li>[Date Picker] Edit Pattern does not support two types of timestamp pattern. Hotfix for CQ-4237982</li> 
  <li>Submit Action using 'Forms Workflow' Classic authoring issues. Hotfix for CQ-4236981</li> 
  <li>[Web Channel] IC Chart should inherit colspan property from AF chart. Hotfix for CQ-4252143</li> 
 </ul> 
 <h4>Backend Integration</h4> 
 <ul> 
  <li>[SOAP requests] Big decimals (more than 6 digits) are represented in exponential notation resulting in validation error. NPR-25283: Hotfix for CQ-4248100</li> 
  <li>Incorrect validation of optional parameters defined in complex types. NPR-25070: Hotfix for CQ-4247107</li> 
  <li>Added capability for the user to use the same WSDL file for multiple service. NPR-24604, Hotfix for CQ-4247756</li> 
  <li>FDM shuffles order of parameters in its SOAP calls. NPR-25069, Hotfix for CQ-4247180</li> 
  <li>FDM merges entities (in List/Array) in SOAP request. NPR-25284: Hotfix for CQ-4248375</li> 
 </ul> 
 <h3>Forms JEE Installer</h3> 
 <h4>PDFG Service</h4> 
 <ul> 
  <li>The create/modify function of security settings does not work. NPR-24769: Hotfix for CQ-4246927</li> 
  <li>Optimize PDFs by selectively unembedding fonts via single API call. NPR-23287</li> 
 </ul> 
 <h4>Document Services</h4> 
 <ul> 
  <li>Output Service does not provide the correct tags for accessibility Reader. NPR-24438, NPR-24439, NPR-24440, NPR-24441: Hotfix for CQ-4243849, CQ-4243845, CQ-4243852, CQ-4243853</li> 
 </ul> 
 <h4>Document Security</h4> 
 <ul> 
  <li>Issue with Policy creation using Document Security. NPR-25586, NPR-25547: Hotfix for CQ-4247086</li> 
 </ul> 
 <h4>Forms - Foundation JEE</h4> 
 <ul> 
  <li>Processes running as System Context Account intermittently. NPR-25289, NPR-25313: Hotfix for CQ-4249331</li> 
  <li>AEM Forms JEE impacted by Apache Struts and Jackson data binding security alert. NPR-25628: Hotfix for CQ-4242891</li> 
  <li>Email start point process does not work. NPR-25253: Hotfix for CQ-4248518</li> 
 </ul> 
 <h3>Feature Packs Included</h3> 
 <h4>Assets</h4> 
 <ul> 
  <li style="font-size: 16px;">Added <a href="/help/assets/aem-assets-adobe-stock.md">integration with Adobe Stock</a> so that users can search, preview, save and license Adobe Stock assets directly from AEM user interface. For more detailed information, see <a href="https://helpx.adobe.com/experience-manager/kt/assets/using/stock-assets-feature-video-use.html">https://helpx.adobe.com/experience-manager/kt/assets/using/stock-assets-feature-video-use.html</a>. NPR-15779: Hotfix for CQ-30857</li> 
  <li>Added support for dynamic conditional metaschema. For more information, see <a href="/help/assets/cascading-metadata.md">Cascading Metadata</a>. NPR-25189: Hotfix for CQ-4237413</li> 
  <li>Enabled "Asset Download" option on Content Fragments. For more information, see <a href="/help/assets/asset-reports.md">Asset Reports</a>. NPR-25186: Hotfix for CQ-4237410</li> 
  <li>Ability to set a metadata schema for asset folders. For more information, see <a href="/help/assets/folder-metadata-schema.md">Folder Metadata Schema</a> and refer to its <a href="/help/release-notes/sp-release-notes.md#configuration-settings-required-for-npr">Configuration Settings</a> post AEM 6.4.2.0 installation. NPR-21268: Hotfix for CQ-4221574</li> 
 </ul> 
 <h4>Sites</h4> 
 <ul> 
  <li>Allow editing a content fragment without delete permissions. For more information, see <a href="/help/sites-developing/customizing-content-fragments.md#asset-permissions">Customizing and Extending Content Fragments</a>. NPR-25793: Hotfix for CQ-4248750</li> 
  <li>Added the capability to annotate Content Fragments. For more information, see <a href="/help/assets/content-fragments-variations.md#annotating-a-content-fragment" target="_blank">Variations-Authoring Fragments</a>. NPR-25188: Hotfix for CQ-4235336</li> 
  <li>Versioning: Compare Content Fragments Side-by-Side. For more information, see <a href="/help/assets/content-fragments-managing.md#comparing-fragment-versions">Managing Content Fragments</a>. NPR-25187: Hotfix for CQ-4237412</li> 
  <li>Image Editor enhancements backported to AEM 6.4.2.0. For more information, see <a href="/help/sites-developing/image-editor.md">Image Editor</a>. NPR-24467</li> 
 </ul> 
 <h3>OSGI Bundles and Content Packages Included</h3> 
 <div> 
  <p>List of OSGi bundles included in AEM 6.4.2.0</p> 
  <p><a alt="bundle-list.txt" href="assets/bundle-list.txt" status="changing">Get File</a></p> 
  <p> List of Content Packages included in AEM 6.4.2.0</p> 
  <p><a alt="6_4_2_0content-package-list.txt" href="assets/6_4_2_0content-package-list.txt" status="changing">Get File</a></p> 
 </div> 
</div>

<div class="details"> 
 <h3 class="summary">AEM 6.4.1.0</h3> 
 <p>AEM 6.4.1.0 is an important update that includes performance, stability, security and key customer fixes and enhancements released since the general availability of AEM 6.4 in <strong>April 2018.</strong></p> 
 <p>AEM 6.4.1.0 can be installed on AEM 6.4 GA. Some of the key highlights of the service pack are:</p> 
 <ul> 
  <li>The built-in repository (Apache Jackrabbit Oak) is updated to version 1.8.3.</li> 
  <li>Introduced Enhanced Smart Tags.</li> 
  <li>Fixes in Design picker, Tag picker(change the source VM and target VM to auto.<strong>)</strong></li> 
  <li>Added support for typeHint to save values as string.</li> 
  <li>Added support for SMTP over TLS in Mail Service</li> 
  <li>Proxy handling fix for HTTP forwarder in DMS7.</li> 
  <li>Update to /etc/clientlibs/social/thirdparty/handlebars/source/handlebars.js version 1.3</li> 
  <li>Fixes in DMHybrid Opt-OUT and Opt-IN packages.</li> 
  <li>Fixes in Smart Crop.</li> 
  <li>Migrated OOTB configuration values to the new location ( from /etc to /conf).</li> 
  <li>Added color profiles to the customer settings on delivery servers.</li> 
  <li>Migration of Image Server settings from /etc --&amp;gt; /conf.</li> 
  <li>Added Source Content Fragment for translation.</li> 
  <li>Add ARIA support to Print and PrintDialog.</li> 
  <li>Added email validation ARIA support.</li> 
  <li>Proactive Backport for platform.clientlibs fixes.</li> 
 </ul> 
 <h3>Assets</h3> 
 <ul> 
  <li>Cascading dropdown value shows blank on reopening asset properties page. NPR-23042: Hotfix for CQ-4238761</li> 
  <li>Shared links on mylinkshare page and links to the page are not available for non-admin user NPR-23044: Hotfix for CQ-4239004</li> 
  <li>To prevent a Null Pointer Exception in the DAM Asset Update workflow in 6.4.0. NPR-24134: Hotfix for CQ-4244972</li> 
  <li>Published WCM page shows placeholder icons for hotspot, missing CSS files with 403 error for OOTB Viewers. NPR-23041: Hotfix for CQ-4233716</li> 
  <li>[Detail View] The Next/Back Navigation feature leaves a DIV overlay in Dynamic Rendition preview area blocking access to the viewer. NPR-23043: Hotfix for CQ-4238499</li> 
  <li>CMYK image rendition has incorrect saturation. NPR-23048: Hotfix for CQ-4235470</li> 
  <li>XMP metadata extraction by Scene7ListInfoProvider is resource intensive. NPR-23754</li> 
  <li>[dam-delivery] Http forwarder does not respect HTTP proxy settings. NPR-24002: Hotfix for CQ-4244140</li> 
 </ul> 
 <h3>Sites</h3> 
 <ul> 
  <li>When we rename the page while we move, the movement of page is successful but rename functionality does not work. NPR-22923: Hotfix for CQ-4235907</li> 
  <li>Error when publishing a Live Copy page that points to an Importer Page in Adobe Campaigns. NPR-23053: Hotfix for CQ-4237164</li> 
  <li>Move/Rename in Classic UI fails with error, “An error occured while moving page” and not renamed. NPR-23051: Hotfix for CQ-4235907</li> 
  <li>Switching content from Column view to list view renders a blank page and triggers a Null Pointer Exception for pages with OffTime set and OnTime as blank. NPR-22968, NPR-23052: Hotfix for CQ-4238940</li> 
 </ul> 
 <h3>Commerce</h3> 
 <ul> 
  <li>Fix Failing Core Hobbes Testcase (CQ/Commerce Module). Hotfix for CQ-4253494</li> 
 </ul> 
 <h3>Vulnerability</h3> 
 <ul> 
  <li>Salesforce integration is vulnerable to Server Side Request Forgery (SSRF). NPR-24289: Hotfix for CQ-4245277</li> 
  <li>Server Side Request Forgery (SSRF) and Cross-Site Scripting (XSS) in ReportingServicesProxyServlet. NPR-24657: Hotfix for CQ-4246880</li> 
  <li>Cross-Site Scripting (XSS): Reflected in commerce createcatalogwizard.html/content. NPR-24642: Hotfix for CQ-4237017</li> 
  <li>Cross-site scripting (XSS) in Admin UI Project links. NPR-23272: Hotfix for CQ-4241795</li> 
 </ul> 
 <h3>WCM - Foundation Components</h3> 
 <ul> 
  <li>Opening the Design picker results in a null pointer exception. NPR-23047: Hotfix for CQ-4238736</li> 
 </ul> 
 <h3>User Interface</h3> 
 <ul> 
  <li>[Coral3 Datepicker] Add support for typeHint to save values as "String." NPR-23398: Hotfix for Granite-21194</li> 
  <li>Internationalization translation does not work at the language level. NPR-22967, NPR-23046: Hotfix for Granite-21111</li> 
  <li>Proactive Backport for granite.ui.commons fixes. NPR-23537</li> 
  <li>Proactive Backport for granite.ui.content fixes. NPR-23535</li> 
  <li>Proactive Backport for granite.ui.coralui fixes. NPR-23538</li> 
  <li>Unable to remove multiple users from the group at once. NPR-23846</li> 
  <li>[OMEGA] Report "Feature" in english only. NPR-23989: Hotfix for Granite-21231</li> 
  <li>[Design Importer] Importing a page does not import the js, css. NPR-25203: Hotfix for Granite-22236</li> 
 </ul> 
 <h3>Integration</h3> 
 <ul> 
  <li>Unclosed ResourceResolver in com.day.cq.analytics.sitecatalyst. NPR-22340: Hotfix for CQ-4236515</li> 
  <li>TargetContentImpl makes AEM sluggish during long running queries. NPR-22359: Hotfix for CQ-4236907</li> 
  <li>Target engine (mbox.js, at.js) does not use mangled URLs and uses URLs containing colons which might fail with certain deployments. NPR-22434: Hotfix for CQ-4237854 </li> 
  <li>In Target mode, Authors can modify a component inherited from the blueprint without cancelling the inheritance. NPR-22865: Hotfix for CQ-4237907</li> 
  <li>[Personalization] Icons are deformed when switching to Card view. NPR-23373, NPR-23374: Hotfix for CQ-4240018, CQ-4240019</li> 
  <li>[Personalization] Audience console does not show nt:folder types. NPR-23375: Hotfix for CQ-4242293</li> 
  <li>When a component is targeted on publish instance, flickering appears showing the default experience before the targeted one. NPR-23415: Hotfix for CQ-4242038</li> 
  <li>[Adobe IMS Console] AccessTokenProvider OSGi service configuration reappears after deletion. NPR-23520: Hotfix for CQ-4208250</li> 
  <li>Configuration reference replication fails with intermediate folder structure. NPR-23485: Hotfix for CQ-4242751</li> 
  <li>[Personalization] clientlib blocked by the proxy servlet. NPR-23521: Hotfix for CQ-4240995</li> 
  <li>[Adobe IMS Console] Registered Cloud Solutions do not get picked up in configuration wizard. NPR-23977: Hotfix for CQ-4244549</li> 
  <li>Infinite loop when loading targeted content on pages without an HTML extension. NPR-23522: Hotfix for CQ-4223600</li> 
  <li>Activation fails for a page with inherited Dynamic Tag Management configuration references. NPR-23485: Hotfix for CQ-4242751</li> 
 </ul> 
 <h3>Platform</h3> 
 <ul> 
  <li>[Classic UI][Touch UI] The tag picker does not display and throws an exception when trying to browse for tags via a tags predicate in the Asset Search schema. NPR-23049: Hotfix for CQ-4239371</li> 
  <li>[Classic UI] Components using xtype=tags return null and cannot be selected from eth list of tags. NPR-23050: Hotfix for CQ-4239937</li> 
  <li>[Branding] Opt-in dialog mentions Adobe Marketing Cloud instead of Adobe Experience Cloud. NPR-23210: Hotfix for CQ-4237799</li> 
  <li>Filter option makes AEM sluggish after upgrading from 6.3 to 6.4. NPR-23260: Hotfix for CQ-4239847 (to check)</li> 
  <li>Proactive Backport for granite.omnisearch.core fixes. NPR-23536</li> 
  <li>Proactive Backport for platform.clientlibs fixes. NPR-23569</li> 
  <li>Cloud Service Config inheritance broken when editing other page properties. NPR-23216: Hotfix for CQ-4239782</li> 
  <li>Enabled STARTTLS support in Day CQ Mail Service. NPR-23941: Hotfix for CQ-4240397</li> 
 </ul> 
 <h3>Projects</h3> 
 <ul> 
  <li>[Content Fragment] Language copy for embedded asset is not created while English asset is added to translation. Hotfix for CQ-4243477<strong></strong></li> 
  <li>The msft config dropdown is showing config from /libs(6.4 configs) instead of from /etc(6.3 configs) in legacy mode. Hotfix for CQ-4243475</li> 
  <li>Automatically promote and delete translation launches in Translation projects. Hotfix for CQ-4243474</li> 
  <li>Content fragment inside sites not getting translated. Hotfix for CQ-4243482, CQ-4243483, CQ-4245687</li> 
  <li>Server error on opening translation job search filter. Hotfix for CQ-4236813</li> 
  <li>Credential config dropdown is blank even after tif is present inside /conf/we-retail. Hotfix for CQ-4236315</li> 
  <li>Open Project KPI: performance degradation as more projects are created. NPR-23840: Hotfix for CQ-4238392</li> 
  <li>Workflow Starter not able to accept TypeHint value of String. NPR-23863: Hotfix for CQ-4238356</li> 
 </ul> 
 <h3>Communities</h3> 
 <ul> 
  <li>Security vulnerabilities in Version 1.0 of Handlebars. NPR-23636: Hotfix for CQ-4243055</li> 
  <li>Bulk Allow of flagged messages is not working. NPR-23867: Hotfix for CQ-4243962</li> 
  <li>Default value is not showing on sorting button in forum component. NPR-23882: Hotfix for CQ-4243375</li> 
  <li>Issues with message delivery from Community sites to groups. NPR-23935</li> 
 </ul> 
 <h3>Workflow</h3> 
 <ul> 
  <li>The Day CQ Workflow Email Notification Service triggers one e-mail per Mongo node for WorkflowCompleted and WorkflowAborted notifications. NPR-22515: Hotfix for CQ-4238172</li> 
  <li>Running the DAM update asset workflow throws a NullPointerException. NPR-23010: Hotfix for Granite-21096</li> 
  <li>Workflow Process step does not display scripts from /etc/workflow/scripts. NPR-23263: Hotfix for Granite-20775</li> 
  <li>Workflow Dynamic Participant Step does not display scripts from /apps/workflow/scripts. NPR-23464: Hotfix for Granite-21276</li> 
  <li>Unable to edit any workflow after editing it once. NPR-23742: Hotfix for CQ-4238526</li> 
  <li>[Classic UI] Upon editing the workflow launchers, the conditions disappear causing the workflows to launch without any conditions. NPR-23835: Hotfix for CQ-4239153</li> 
  <li>Project inbox: switching to calendar view shows main inbox content. NPR-23947: Hotfix for CQ-4241236</li> 
  <li>Need to expose payload details in the bundle so the HTL component can display the value in the list view. NPR-23948: Hotfix for CQ-4240953</li> 
  <li>Unable to store dialog data in Dialog Participant step. NPR-23965: Hotfix for CQ-4234123</li> 
  <li>[Touch UI] When saving a workflow model, the 'Sync' button changes to 'Synched' resulting to spelling mistake. Hotfix for CQ-4244843</li> 
  <li>Project inbox: switching to calendar view shows main inbox content. Hotfix for CQ-4244436</li> 
  <li>Unable to select Dialogs in Dialog Participant step. Hotfix for CQ-4244532</li> 
  <li>Proactive Backport for granite.omnisearch.core fixes. NPR-23536</li> 
  <li>Issue in Mobile Workspace App 6.4 with Shared Task. NPR-26383</li> 
 </ul> 
 <h3>WCM - Translation</h3> 
 <ul> 
  <li>[Reference Panel] Translation jobs are not getting executed during project creation. Hotfix for CQ-4245327</li> 
 </ul> 
 <h3>WCM - MSM</h3> 
 <ul> 
  <li>[MSM] Rollout performance improvement. Hotfix for CQ-4231488</li> 
  <li>[MSM] Timing gap in Event Listening between event actually happening and event handling. Hotfix for CQ-4227766</li> 
 </ul> 
 <h3>Screens</h3> 
 <ul> 
  <li>Screen page fails with error due to missing dependencies for screens-core-pkg:1.4.42. Hotfix for CQ-4245918</li> 
 </ul> 
 <h3>Projects - Translation</h3> 
 <ul> 
  <li>[Content Fragment] Language copy for embedded asset is not created while English asset is added to translation. Hotfix for CQ-4243477<strong></strong></li> 
  <li>The msft config dropdown is showing config from /libs(6.4 configs) instead of from /etc(6.3 configs) in legacy mode. Hotfix for CQ-4243475</li> 
  <li>Automatically promote and delete translation launches in Translation projects. Hotfix for CQ-4243474</li> 
  <li>Content fragment inside sites not getting translated. Hotfix for CQ-4243482, CQ-4243483, CQ-4245687</li> 
  <li>Server error on opening translation job search filter. Hotfix for CQ-4236813</li> 
  <li>Credential config dropdown is blank even after tif is present inside /conf/we-retail. Hotfix for CQ-4236315</li> 
 </ul> 
 <h3>Content Fragment Management</h3> 
 <ul> 
  <li>Deleting component fills logs with stack traces. Hotfix for CQ-4242315</li> 
 </ul> 
 <h3>DAM - General</h3> 
 <ul> 
  <li>Closing the detail view of an asset returns to incorrect search result page. Hotfix for CQ-4240960</li> 
  <li>[Camera Raw] Image adjust option is missing. Hotfix for CQ-4246121</li> 
  <li>IndexOutOfBoundsException: OOTB Asset Modification report. Hotfix for CQ-4239744</li> 
  <li>Remove confidence score from report csv. Hotfix for CQ-4241491</li> 
  <li>Link share email delivery broken for non "admin" sender. Hotfix for CQ-4240357</li> 
  <li>Fixing IT failures. Hotfix for CQ-4249891</li> 
 </ul> 
 <h3>DAM - Brand Portal</h3> 
 <ul> 
  <li>Asset properties list only 3 properties on first tab, rest all the tabs look empty. Hotfix for CQ-4242503</li> 
  <li>File type and file size predicates are not avaliable in published search form. Hotfix for CQ-4242026</li> 
  <li>Search in directory predicate should be filtered out/not shown in search filters. Hotfix for CQ-4241386</li> 
  <li>Default search from should exist after unpublish. Hotfix for CQ-4241383, CQ-4241113</li> 
  <li>Publish to brand portal gesture doesn't work for image presets. Hotfix for CQ-4241074</li> 
  <li>Publish to Brand Portal is not working for collections. Hotfix for CQ-4241122, CQ-4246558</li> 
 </ul> 
 <h3>DAM - DM Client</h3> 
 <ul> 
  <li>Upgrading to 6.4 removes previously created video encoding profiles. Hotfix for CQ-4244067</li> 
  <li>Alt Text attribute is broken in Dynamic Media component. Hotfix for CQ-4244081</li> 
  <li>[DMS7] Editing remote sets in AEM are not overwritten in Scene7. Hotfix for CQ-4243430</li> 
  <li>Verification of 6.4 SP1 build on DM Hybrid. Hotfix for CQ-4244623</li> 
  <li>[DMS7-UA] When clicking the Embed button for a published Video Asset, nothing appears to happen. The Embed dialog is expected to display with HTML code. Hotfix for CQ-4245237</li> 
  <li>[DM Hybrid] Copy URL for published Video Assets or Mixed Media Sets gets “[[object Object]” in the URL dialog. Hotfix for CQ-4245236, CQ-4245451</li> 
  <li>[DMHybrid][REGR] Video's Details View page does not contain the preview of the Video Asset show and outputs an error message to the console. Hotfix for CQ-4244320</li> 
  <li>Automatic S7 Encoding of we.retail content. Hotfix for CQ-4242253</li> 
  <li>Pre-Upgrade Video Processing Presets cannot have a new Video Encoding Preset added nor edit the existing Encoding Presets. Hotfix for CQ-4240407</li> 
  <li>Pre-Upgrade Image Presets are shown as Unpublished on Renditions page and does not yield URL. Hotfix for CQ-4240406</li> 
  <li>[CSS] Assets are shown - but viewers used are default and not the OOTB Viewers. Hotfix for CQ-4239839</li> 
  <li>Disabled clean up step hang manual execution &amp; used of private coral classes. Hotfix for CQ-4239729</li> 
  <li>Image viewer is generating an error and fails to display the correct smart crop. Hotfix for CQ-4237564</li> 
  <li>Legacy preset under /etc appears to be broken and not migrated to location under /conf upon save. Hotfix for CQ-4237416</li> 
  <li>Regression in OOB VideoViewer 5.8.x - the viewer expands iframe to the right, hence breaking page layout. Hotfix for CQ-4235465</li> 
  <li>[DMS7] Smart Crop rendition URL and Embed buttons are active for images that have not been published. Hotfix for CQ-4233696</li> 
  <li>[DMHybrid] Restore previous crop/rotate feature. Hotfix for CQ-4239489</li> 
  <li>When previewing a video in card view, the play button does not toggle to pause. Hotfix for CQ-4238592</li> 
  <li>When performing an Opt-In upgrade, the YouTube configuration is not moved/copied from its old location to the new location. Hotfix for CQ-4238590</li> 
  <li>DropTwo OOTB AVS Video Processing Profiles are listed under Folder properties and only one contains defined encodings. Hotfix for CQ-4238096</li> 
  <li>[DMS7] Smart Crop: Detail View: URL button is labeled Copy button for renditons. Hotfix for CQ-4237804</li> 
  <li>Viewer Preset listing page remains blank even after executing the curl commands. Hotfix for CQ-4243246</li> 
  <li>Disabled clean up step hang manual execution &amp; use of private coral classes. Hotfix for CQ-4239729</li> 
  <li>Video Report Details page does not show video asset. Hotfix for CQ-4246208</li> 
 </ul> 
 <h3>DAM - DMServices</h3> 
 <ul> 
  <li>[DMS7] Cloud Configuration: Unable to sync new content with Scene7 after updating to SP1. Hotfix for CQ-4244437</li> 
  <li>[DMHybrid] Color profiles and catalog settings are not registering in a debug_info=catalog call. Hotfix for CQ-4242346</li> 
  <li>Add color profiles to the customer settings on delivery servers. Hotfix for CQ-4241818, CQ-4241819</li> 
  <li>[DMHybrid][0dt] After 6.3 &amp;gt; 6.4 upgrade, catalog settings are moved to the incorrect node. Hotfix for CQ-4239974, CQ-4239975</li> 
  <li>[DMHybrid] pushviewerpresets script does not create the nodes needed to modify catalog settings. Hotfix for CQ-4240076</li> 
  <li>When using the “Format” drop-down selection and selecting either PNG or JPG formats, the downloaded file is shown as oversaturated and darker than the original asset. Hotfix for CQ-4240073</li> 
  <li>[DMS7] Remove the MIME Type mapping: image_x-eps. Hotfix for CQ-4240394</li> 
  <li>[DMS7] Upload parameters for knockout background do not pass the ipsApiService.log and hence, do not work. Hotfix for CQ-4240686</li> 
  <li>Upgrading Image Processing Profiles created in a 6.3 to 6.4 instance breaks the “Crop-type” property. Hotfix for CQ-4237739</li> 
  <li>[Dynamic Media] Regular Asset upload outside the smartcrop folder fails. Hotfix for CQ-4237670</li> 
  <li>Adjust profile fallback code for "Adaptive Video Encoding" profile name to "Adaptive_Video_Encoding". Hotfix for CQ-4237666</li> 
  <li>EmbedXMP data is always set to “active” for Ptiff generation process. Hotfix for CQ-4234498</li> 
  <li>CMYK image rendition has incorrect saturation. Hotfix for CQ-4235470</li> 
  <li>Image Server settings are not replicated to delivery while the replication logs mark them successful. Hotfix for CQ-4239480, CQ-4239046</li> 
  <li>[DMS7] Unable to create sets using old/new references to Cloud Configuration. Hotfix for CQ-4238078</li> 
  <li>Scene7 workflow step only reads Scene7 in the name and the description but does not clarify the workflow step in DAM Update workflow. Hotfix for CQ-4237865</li> 
 </ul> 
 <h3>DAM - Smart Tags</h3> 
 <ul> 
  <li>Introduced Enhanced Smart Tags. NPR-21951</li> 
 </ul> 
 <h2>Forms</h2> 
 <p>AEM Forms fixes are delivered through add-on packages and other patch installers provided with the release. For details, see AEM Forms Releases.</p> 
 <p>The key highlights for AEM Forms are:</p> 
 <ul> 
  <li>AEM Forms introduces <a href="/help/forms/using/transaction-reports-overview.md" target="_blank">transaction reports capability</a> to track and keep count of transactions like submitted forms, processed documents, and rendered documents on your AEM Forms deployment. It provides insights about product usage and helps business users understand digital processing volumes.<br /> </li> 
  <li>Enabled PDF/UA support to XML forms.</li> 
  <li>Added allowProxy = true for Clientlib <strong>aemfd.ccm.channel.contentpage</strong></li> 
  <li>Updated code to make advanced title search as contains rather than equal.</li> 
  <li>Update to new version of Node Package Manager (NPM) on Continuous Integration Machine.</li> 
 </ul> 
 <h3>Forms add-on package</h3> 
 <h4>Backend Integration</h4> 
 <ul> 
  <li>An error is generated when providing null as a value to an optional field. NPR-24397</li> 
  <li>WSDL invoking is failing when element has different namespace other than global namespace. NPR-24281</li> 
  <li>[FDM WSDL] Getting DermisException: Excepted list data in case of property type array. NPR-24265</li> 
  <li>[FDM WSDL] Getting DermisException: java.lang.Exception: createSOAPParam: Invalid Params. NPR-24264</li> 
  <li>[FDM Client SDK] Unable to do testing of pre/post preprocessor and custom submit action. Hotfix for CQ-4238469</li> 
  <li>Fixes for Javadoc issues in Dermis. Hotfix for CQ-4244250</li> 
  <li>Enhanced input in Web Services Description Language (WSDL). Hotfix for CQ-4244133</li> 
  <li>Basic authentication testing for WSDL results in different error for same configuration in AEM 6.3 and AEM 6.4. Hotfix for CQ-4244132</li> 
  <li>Request to include ValueUtil in client- 
   <code>
     sdk 
   </code> and 
   <code>
     javadocs 
   </code>. Hotfix for CQ-4242803</li> 
  <li>[FDM Cloud Config] Unable to configure 
   <code>
     SOAP based 
   </code> Authentication from cloud configuration. Hotfix for CQ-4238462</li> 
  <li>Dermis - Add missing packages in Javadocs. Hotfix for CQ-4242815</li> 
  <li>WSDLInvokerParams to be included in Forms Add-On client 
   <code>
     sdk 
   </code>. NPR-23381: Hotfix for CQ-4240233</li> 
 </ul> 
 <h4>Adaptive Forms</h4> 
 <ul> 
  <li>Document (IC) rendition should be logged as a transaction using Transaction Recording Service. Hotfix for CQ-4245333</li> 
  <li>While executing UAT5, pdf generated at verify stage is missing an entry. Hotfix for CQ-4243184</li> 
  <li>Test case for deep copy of guideContext. Hotfix for CQ-4242924</li> 
  <li>Proof type field is missing on executing the UAT3 on latest upgraded server. Hotfix for CQ-4243120</li> 
  <li>On upgraded server, the submitted form is missing the State/Province/Region and Country values that were present on pre-upgrade server. Hotfix for CQ-4241444</li> 
  <li>[ExpressionEditor] Error while navigating to Verify stage during form submission. Hotfix for CQ-4241384</li> 
  <li>Values are missing in verify stage on pre-upgrade and upgraded server for submitted form. Hotfix for CQ-4241896</li> 
  <li>Quit and save button at the bottom of the page are not working. Hotfix for CQ-4240112</li> 
  <li>Contact number missing on the upgraded set-up. Hotfix for CQ-4239870</li> 
  <li>Under “ACTION TAKEN” section in Dispute Type tab , “Additional documents to support my claim” has additional field Proof Type Saved “in it. Hotfix for CQ-4239873</li> 
  <li>"Error in getDataAPI" erorr encountered at verifyPdf stage. Hotfix for CQ-4239865</li> 
  <li>Errors in migration logs for author and publish instance. Hotfix for CQ-4239365</li> 
  <li>Errors in migration logs for author and publish instance. Hotfix for CQ-4239635</li> 
  <li>Deserialization error like "Deserialization not allowed for class sun.util.calendar.ZoneInfo" in error logs post submission of an Adaptive Form. Hotfix for CQ-4240419</li> 
  <li>State field is not being populated in Mobile form rendition. Hotfix for CQ-4240597</li> 
  <li>Remove reference usage of components in templates from anti-pattern list. Hotfix for CQ-4239217</li> 
  <li>HTML5 Numeric Box set as a Float or Decimal gives different validation results in different browsers. NPR-23528: Hotfix for CQ-4244097</li> 
  <li>[Image upload] Image not getting displayed in DOR preview. Hotfix for CQ-4243178</li> 
  <li>JEE server throws an error on trying to submit the Adaptive Form with ‘Email PDF’ and ‘Include attachments’. Hotfix for CQ-4239894</li> 
  <li>Chart is not plotted at runtime using table/panel. Hotfix for CQ-4240010</li> 
  <li>Adaptive Form submission is not working and no change in transaction count due to failure of submission. Hotfix for CQ-4246125</li> 
  <li>[Image choice] Document of record options are not visible. Hotfix for CQ-4236976</li> 
  <li>Template editor UI is not stable. Hotfix for CQ-4241497</li> 
  <li>AFs are not shown using assets tab of side panel while is shown using browse option for AEM form component property dialog. Hotfix for CQ-4236751</li> 
  <li>Workflow ID generated for form conversion should be available in generated Adaptive Form. Hotfix for CQ-4240014</li> 
  <li>Unable to select template to create a page in sites on Direct Upgrade: Livecycle to 6.4 server. Hotfix for CQ-4241300</li> 
 </ul> 
 <h4>Assembler Service</h4> 
 <ul> 
  <li>Transaction logging in Assembler Services. Hotfix for CQ-4245018, CQ-4245017, CQ-4245016.</li> 
  <li>Transaction is not reported when PDF/A conversion is done using DDX. Hotfix for CQ-4246039</li> 
 </ul> 
 <h4>Form Manager</h4> 
 <ul> 
  <li>FM CREATE button list to be alphabetically sorted. Hotfix for CQ-4242307</li> 
 </ul> 
 <h4>Form Portal</h4> 
 <ul> 
  <li>Drafts saved on pre-upgrade server do not open correctly on upgraded server. Hotfix for CQ-4243303</li> 
  <li>Version update to 7.1 for adobe-formsmanager-core-module. Hotfix for CQ-4245753</li> 
  <li>Drafts saved on pre-upgrade server do not open correctly on upgraded server. Hotfix for CQ-4243303</li> 
  <li>Attachment scenarios are breaking on replacing/adding/removing attachments in new instance/same instance of draft. Hotfix for CQ-4243165</li> 
  <li>The count of draft retrieved from querying the database is more than the count of drafts present in portal. Hotfix for CQ-4241489</li> 
  <li>Forms submitted on pre upgrade server are not present on upgraded server. Hotfix for CQ-4241490</li> 
  <li>The form displayed in UI in submissions tab is in Unsubmitted state despite successful submission message. Hotfix for CQ-4241487</li> 
  <li>The guideContext should be formed by deep copying the fields as guideContext contains customPropertyMap that itself is an object. Hotfix for CQ-4240126</li> 
  <li>Error when trying to save a form. Hotfix for CQ-4240763</li> 
  <li>The entry for saved and submitted forms is getting populated in crx/de despite we have DB configuration given in Forms Portal Draft and Submission Configuration. Hotfix for CQ-4240726</li> 
  <li>[Search &amp; Lister] Advanced search title fixed value should work as contain rather than equal. Hotfix for CQ-4245499</li> 
 </ul> 
 <h4>Mobile Forms</h4> 
 <ul> 
  <li>Date Field is overlapping in Mobile Forms. Hotfix for CQ-4242256</li> 
  <li>Form submission for Mobile Forms should be logged as a transaction using Transaction recording Service. Hotfix for CQ-4246166</li> 
  <li>Form submission in Formset should be logged as a transaction using Transaction recording Service. Hotfix for CQ-4246165</li> 
 </ul> 
 <h4>AEM Forms App</h4> 
 <ul> 
  <li>[Windows App] Unable to render the form. Hotfix for CQ-4238005</li> 
 </ul> 
 <h4>WorkflowOSGI</h4> 
 <ul> 
  <li>Transaction logging in Workflow Assign Task. Hotfix for CQ-4244440</li> 
  <li>[FDM Step] Unable to use values from workflow metadata when an Assign Task step is inserted between the process step and fdm step. Hotfix for CQ-4241472</li> 
  <li>Delegation of assign task does not work in Forms Integration in OSGI Workflows. NPR-23709: Hotfix for CQ-4243700</li> 
  <li>[Workflow Model Editor] Some Workflow Models are not editable via the ClassicUI WF model editor. Hotfix for CQ-4241151</li> 
 </ul> 
 <h4>MultiChannel Document</h4> 
 <ul> 
  <li>Date field in Template is overlapping the subform in the IC authoring. Hotfix for CQ-4240110</li> 
  <li>Header should not be allowed to be deleted or to be moved up and down in IC web channel authoring. Hotfix for CQ-4243358</li> 
  <li>[IC Editor] Default rows to be set to 1 for Table components. Hotfix for CQ-4244848</li> 
  <li>Target Area to remain visible even after the content has been dragged and dropped on it. Hotfix for CQ-4244534</li> 
  <li>Web channel do not recognize tabs space in Text Document Fragments. Hotfix for CQ-4244481</li> 
  <li>[Print channel] Document (IC) rendition should be logged as a transaction using Transaction Recording Service. Hotfix for CQ-4245335</li> 
  <li>[Web channel] Document (IC) rendition should be logged as a transaction using Transaction Recording Service. Hotfix for CQ-4245334</li> 
  <li>Document Container Search or the Data Model Tree search must be unified to the Asset filter search. Hotfix for CQ-4242305</li> 
  <li>[Document Fragment] The indentation property indents the text by how much units cannot be comprehended. Hotfix for CQ-4241082, CQ-4240643</li> 
  <li>[IC Editor] The Edit Fragment icon on document fragment's tile listed under Assets tab is not very easily discoverable and understandable. Hotfix for CQ-4241047</li> 
  <li>Allow anonymous access to IC Anonymous inaccessible client library. Hotfix for CQ-4245588</li> 
  <li>[Web channel] Data does not resolve in any of the table in web preview and is shown as blank. Hotfix for CQ-4244476</li> 
  <li>Table headers are shown as variables in web channel on auto-generation. Hotfix for CQ-4244242</li> 
  <li>[IC Editor] Content of a Document Fragment used in an IC should get automatically re-sized to fit the width of the Target Area. Hotfix for CQ-4244094</li> 
  <li>The channel name shown in the center top must be consistent either IC title for WEB / PRINT. Hotfix for CQ-4242498</li> 
  <li>Text editor Data object panel should list only top level entities, Hotfix for CQ-4244121</li> 
  <li>Default name is not assigned when adding a new component in editor. Hotfix for CQ-4244691</li> 
  <li>Adding Colspan configuration in all the web channel components. Hotfix for CQ-4244946</li> 
  <li>Layout Fragment Table Width property is not getting reset and honored in Letter or Customer Communication Print Channel. Hotfix for CQ-4241574</li> 
 </ul> 
 <h4>Correspondence Management</h4> 
 <ul> 
  <li>Captions removed from letter template after editing a text asset that contains placeholders. NPR-24196</li> 
  <li>The XDP file, when uploaded and used as a layout for letter templates, fails to preview or edit the templates. NPR-24143: Hotfix for CQ-4244407</li> 
  <li>Assignment selection is selected by default in list fragment. Hotfix for CQ-4240097</li> 
  <li>Condition editor - Multiple result evaluation should be enabled by default. Hotfix for CQ-4240096</li> 
  <li>Image when deleted from List still shows image in preview. Hotfix for CQ-4239909</li> 
  <li>The rule set on the condition module is set as 'Default' for all the module(s). Hotfix for CQ-4239878</li> 
  <li>Data Dictionary creation fails with “Unknown JCR exception” error. Hotfix for CQ-4244122</li> 
  <li>Gaps in 6.3 Content JavaDocs. Hotfix for CQ-4213586</li> 
 </ul> 
 <h3>Forms JEE installer</h3> 
 <h4>Core</h4> 
 <ul> 
  <li>[HTML Workspace] Tracking details missing for applications with parentheses symbol in the name. NPR-23402</li> 
 </ul> 
 <h4>PDFG Service</h4> 
 <ul> 
  <li>Transaction logging in PDFG services. Hotfix for CQ-4244951, CQ-4244586</li> 
  <li>Reducing PDFs by selectively unembedding fonts via single API call. NPR-23287</li> 
  <li>PDFG configurations update issue on AEM upgrade. Hotfix for CQ-4241176</li> 
  <li>Transaction logging in PDFUtility Service. Hotfix for CQ-4245014</li> 
 </ul> 
 <h4>Process Management</h4> 
 <ul> 
  <li>[HTML Workspace] Process Startpoints are not sorted in alphanumerical order. Hotfix for CQ-4239629</li> 
  <li>[HTML workspace] Prepare data call coming up twice when draft is opened the first time. Hotfix for CQ-4243280</li> 
  <li>[HTML Workspace] Prepare Data process gets triggered while closing a form. Hotfix for CQ-4239456</li> 
  <li>Work space hangs when traversed between two tasks. Hotfix for CQ-4237125</li> 
 </ul> 
 <h4>Workbench</h4> 
 <ul> 
  <li>Manage Action Profile Prepare data process fails when default render process configuration is set to HTML. Hotfix for CQ-4244292</li> 
 </ul> 
 <h4>Forms Designer</h4> 
 <ul> 
  <li>Add PDF/UA support to XML forms generated via Designer and Output Service. NPR-23022</li> 
  <li>inline Hyperlinks defined in Designer do not get tagged nor they have alternate text when saved as PDF from Designer. NPR-23023</li> 
 </ul> 
 <h3>Feature Packs Included</h3> 
 <h4>Assets</h4> 
 <ul> 
  <li>Added the capability for Enhanced Smart Tags. For more information, see <a href="https://helpx.adobe.com/experience-manager/6-4/assets/using/enhanced-smart-tags.html">Enhanced Smart Tags</a>. NPR-21951: Hotfix for CQ-4234883</li> 
  <li>Introduced AEM Assets References in InDesign. For more information, see <a href="/help/assets/managing-linked-subassets.md">AEM Assets References in InDesign</a>. NPR-23386</li> 
 </ul> 
 <h4>Sites</h4> 
 <ul> 
  <li>[Page Authoring] Image Editor enhancements. For more information, see <a href="/help/sites-developing/image-editor.md">Image Editor</a>. NPR-24267: Hotfix for CQ-4245502</li> 
 </ul> 
 <h3>OSGI bundles and content packages included</h3> 
 <p>The following text documents the list of OSGI bundles and content packages included in the CFP.</p> 
 <div> 
  <p> List of OSGi bundles included in AEM 6.4.1.0</p> 
  <p><a alt="6_4_1_0_bundle-list.txt" href="assets/6_4_1_0_bundle-list.txt" status="changing">Get File</a></p> 
  <p> List of Content Packages included in AEM 6.4.1.0</p> 
  <p><a alt="6_4_1_0_content-package-list.txt" href="assets/6_4_1_0_content-package-list.txt" status="changing">Get File</a></p> 
 </div> 
</div>

## Install 6.4.4.0 {#install}

### Setup requirements {#setup-requirements}

>[!NOTE]
>
>For successful installation of AEM 6.4.4.0 on the instance, it is strongly recommended to upgrade the version of com.adobe.granite.oak.s3connector to 1.8.3 for the customers who are on the older version of s3 connector.
>The process of upgrading the com.adobe.granite.oak.s3connector is available at [https://helpx.adobe.com/in/experience-manager/6-4/sites-deploying/data-store-config.html](https://helpx.adobe.com/in/experience-manager/6-4/sites-deploying/data-store-config.html).
>Download the latest version of com.adobe.granite.oak.s3connector from: [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/)

>[!CAUTION]
>
>For customers with Feature Packs installed on AEM 6.4. Optional Feature Packs provided by Adobe have dependencies on the release version and service pack. If you have any Feature Pack installed, please contact the AEM Customer Care team to validate the compatibility of those feature packs with this service pack for AEM 6.4.

* AEM 6.4.4.0 requires AEM 6.4. Please visit [upgrade documentation](/help/sites-deploying/upgrade.md) for detailed instructions. 
* The Service Pack download is available on Adobe Package Share, which you can access directly from the AEM 6.4 instance.
* On a deployment with MongoDB and multiple instances, AEM 6.4.4.0 has to be installed on one of the Author instances using the Package Manager.
* Before installing the service pack, ensure to:

    1. Have a snapshot or fresh backup of your AEM instance. **Uninstalling the AEM 6.4.4.0 package is not supported**.

* Restart the instance before installation. While that is only needed when the instance is still in update mode (and this is the case when the instance was just updated from an earlier version), it's generally recommended if the instance was running for longer period of time.

### Install the Service Pack via Package Share {#install-the-service-pack-via-package-share}

Perform the following steps to install the Service Pack on an existing AEM 6.4 instance:

1. Login to Package Share within AEM or directly from your browser and download the [AEM 6.4.4.0 package](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/servicepack/AEM-6.4.4.0).  
   (search for "AEM-6.4.3.0" to find it)  

1. Install the downloaded package using Package Manager.

>[!NOTE]
>
>**Dialog on Package Manager UI sometimes exits immaturely during installation of 6.4.4.0**
>
>Therefore, it is recommended to wait for error logs to stabilize before accessing the instance. The user has to wait for specific logs related to uninstallation of updater bundle before being ensured that the installations is successful. It generally happens on Safari but can intermittently happen on any browser.

### Automatic installation {#automatic-installation}

There are two ways to automatically install AEM 6.4.4.0 into a running instance:

A. Place the package into ..*/crx-quickstart/install* folder while the server is running. The package gets installed automatically.

B. Use the [HTTP API from Package Manager](https://docs.adobe.com/content/docs/en/crx/2-3/how_to/package_manager.html) - make sure you use cmd=install&recursive=true - so the nested package  are  installed.

>[!NOTE]
>
>AEM 6.4.4.0 does not support Bootstrap installation.

### Validate installation {#validate-installation}

1. The Product Information page (*/system/console/  productinfo *) should now show the updated version string "Adobe Experience Manager, Version 6.4.4.0" under Installed Products.
1. All  OSGI  bundles are either ACTIVE or FRAGMENT in the OSGI Console (Use Web Console: /system/console/bundles).
1. The OSGI bundle org.apache.jackrabbit.oak-core is on version 1.8.11 or higher (Use Web Console: /system/console/bundles).

To determine the certified platform for running with this release of AEM Sites and Assets, see [Technical Requirements](/help/sites-deploying/technical-requirements.md).

>[!Note]
>On successful installation of the package, an >informational message appears indicating that the content >package has installed successfully,  such as **"Content Package AEM-6.4-Service-Pack-4 Installed successfully."**

### Update Dynamic Media Viewers (5.10.1) {#update-dynamic-media-viewers}

AEM 6.4.4.0 contains new version of Dynamic Media viewers (5.10.1) which enables check for duplicate names on Image Preset page. Dynamic Media customers are advised to run the following command to bring out of the box viewer presets to an up-to-date state.

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

which will copy new viewer presets to /conf location.

### Install AEM forms add-on package {#install-aem-forms-add-on-package}

#### Install AEM forms add-on {##installaemformsaddon}

>[!NOTE]
>
>Skip if you are not using AEM Forms. Fixes in AEM Forms are delivered through a separate add-on package.

>[!NOTE]
>
>AEM 6.4.4.0 includes a new version of [AEM Forms compatibility package](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/servicepack/fd/AEM-FORMS-6.4.2.0-COMPAT). If you are using an older version of AEM Forms Compatibility Package and updating to AEM 6.4.4.0, install the latest version of AEM Forms compatibility package post installation of Forms Add-On Package.

1. Ensure that you have installed the AEM Service Pack. 
1. Download the corresponding forms add-on package listed at [AEM Forms releases](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) for your operating system.
1. Install the forms add-on package as described in [Installing AEM forms add-on packages](https://helpx.adobe.com/experience-manager/6-4/forms/using/installing-configuring-aem-forms-osgi.html#InstallAEMFormsaddonpackage).

### Install AEM Forms JEE installer {#install-aem-forms-jee-installer}

>[!NOTE]
>
>Skip if you are not using AEM Forms on JEE. Fixes in AEM Forms JEE are delivered through a separate installer.

For information about installing the cumulative installer for AEM Forms JEE and post-deployment configuration, see [AEM Forms JEE Patch Installer 0004](https://helpx.adobe.com/aem-forms/quick-fixes/6-4/jee-patch-0003.html).

## Configuration settings required for NPR-21268 {#configuration-settings-required-for-npr}

If you are using Classic (old) UI and have created metadata templates using it, follow the steps to run the JMX script to preserve them -

1. Go to /system/console/jmx.
1. Click on "Migrate Metadata Templates."
1. Click on "migrateMetadataTemplatesAtPath" and supply the folder path under which you want the metadata templates to be preserved.

## Configuration settings required for NPR-24536 {#configuration-settings-required-for-npr-1}

The count for shared Queue doesnot refresh, by default, for other users when a user claims a task . For this, we have introduced a new property. Follow the steps below to configure this property on your AEM instance:

1. Go to Admin UI -&gt; Services -&gt; Workspace -&gt; Global administration.
1. Export Global settings.
1. In the downloaded XML file, add the tag &lt;client_tasksPollingInterval&gt;10&lt;/client_tasksPollingInterval&gt; Here, 10 is the example value in seconds. You can modify it accordingly.
1. Save the file.
1. Go back to Admin UI -&gt; Services -&gt; Workspace -&gt; Global administration.
1. Import the xml file in the Import Global Settings section.
1. You can now logout of the system and log in again.
1. The count for shared queue starts refreshing for other users in the workspace.
1. To turn off the polling, change the value to 0 and import the XML file again.

## Uber Jar {#uber-jar}

The Uber Jar for AEM 6.4.4.0 is available in the [Adobe Public Maven repository](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.4.3/).

To use Uber Jar in a Maven project, refer to the article, [How to use Uber jar](/help/sites-developing/ht-projects-maven.md) and include the following dependency in your project POM:

```shell
<dependency>
      <code>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.4.4</version>
      <classifier>apis</classifier>
      <scope>provided</scope>
</dependency>
```

## Removed/Deprecated Features {#removed-deprecated-features}

This section lists features and capabilities that have been removed or deprecated from AEM 6.4. 

| Area |Feature |Replacement |Version |
|---|---|---|---|
| Assets |Manage Tag Action for Subassets |No Replacement |AEM 6.4.2.0 |

## Known Issues {#known-issues}

The following errors & warning may occur during installation of AEM 6.4.4.0 and can be safely ignored as they do not impact your AEM instance :

* Errors as create component instance and Service factory returned null occurs due to repository restart:

    * com.day.cq.cq-personalization [com.day.cq.personalization.impl.DefaultProfileProvider(938)] Cannot create component instance due to failure to bind reference profileManager
    * org.apache.sling.commons.scheduler FrameworkEvent ERROR (org.osgi.framework.ServiceException: Service factory returned null. (Component: com.day.cq.tagging.impl.TagGarbageCollector (1687)))

* `com.adobe.cq.social.cq-social-jcr-provider bundle com.adobe.cq.social.cq-social-jcr-provider:1.3.5 (395)[com.adobe.cq.social.provider.jcr.impl.SpiSocialJcrResourceProviderImpl(2302)] : Timeout waiting for reg change to complete unregistered`
* `com.adobe.granite.maintenance.impl.TaskScheduler No maintenance windows found at granite/operations/maintenance`
* `com.adobe.cq.com.adobe.cq.ui.commons bundle com.adobe.cq.com.adobe.cq.ui.commons:1.2.28 (204)[com.adobe.cq.ui.wcm.commons.internal.servlets.rte.RTEFilterServletFactory(573)] : The unbindAmendment method has thrown an exception (java.lang.IllegalStateException: Service already unregistered).`

## OSGi bundles and Content Packages included {#osgi-bundles-and-content-packages-included}

The following text documents list the OSGi bundles and Content Packages included in AEM 6.4.4.0

List of OSGi bundles included in AEM 6.4.4.0

[Get File](assets/bundle-list.txt)

List of Content Packages included in AEM 6.4.4.0

[Get File](assets/content-package-list.txt)

## Helpful resources {#helpful-resources}

* [AEM 6.4 release notes](/help/release-notes/release-notes.md)
* [AEM product page](https://www.adobe.com/solutions/web-experience-management.html)
* [AEM developer support](https://docs.adobe.com/content/ddc/en.html)
* [AEM 6.4 documentation](https://helpx.adobe.com/support/experience-manager/6-4.html)
* Subscribe to [Adobe Priority Product Updates](https://www.adobe.com/subscription/priority-product-update.html)

## Restricted Sites {#restricted-sites}

These sites are only available to customers. If you are a customer and need access, please contact your Adobe account manager.

* [Product download at licensing.adobe.com](https://licensing.adobe.com/)
* [Contact customer support](https://daycare.day.com/)

