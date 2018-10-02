---
uuid: 9568e329-7762-443f-97c6-69a4afe4c409
index: y
internal: n
snippet: y
translate: y
---

# Sites Repository Restructuring in AEM 6.4

As described on the parent [Repository Restructuring in AEM 6.4](repository-restructuring.md) page, customers upgrading to AEM 6.4 should use this page to assess the work effort associated with repository changes impacting the AEM Sites Solution. Some changes require work effort during the AEM 6.4 upgrade process, while others can be deferred until a 6.5 upgrade.

**With 6.4 Upgrade**

* [ContextHub Segments](sites-repository-restructuring-in-aem-6-4.md#ContextHubSegments)

**Prior to 6.5 Upgrade**

* [Adobe Analytics Client Libraries](sites-repository-restructuring-in-aem-6-4.md#AdobeAnalyticsClientLibraries)
* [Classic Microsoft Word to Web Page Designs](sites-repository-restructuring-in-aem-6-4.md#ClassicMicrosoftWordtoWebPageDesigns)
* [Mobile Device Emulator Configurations](sites-repository-restructuring-in-aem-6-4.md#MobileDeviceEmulatorConfigurations)
* [Multi-site Manager Blueprint Configurations](sites-repository-restructuring-in-aem-6-4.md#MultisiteManagerBlueprintConfigurations)
* [Multi-site Manager Rollout Configurations](sites-repository-restructuring-in-aem-6-4.md#MultisiteManagerRolloutConfigurations)
* [Page Event Notification E-mail Template](sites-repository-restructuring-in-aem-6-4.md#PageEventNotificationEmailTemplate)
* [Page Scaffolding](sites-repository-restructuring-in-aem-6-4.md#PageScaffolding)
* [Responsive Grid LESS](sites-repository-restructuring-in-aem-6-4.md#ResponsiveGridLESS)
* [Static Template Designs](sites-repository-restructuring-in-aem-6-4.md#StaticTemplateDesigns)
* [Adobe Search and Promote Integration Client Libraries](sites-repository-restructuring-in-aem-6-4.md#AdobeSearchandPromoteIntegrationClientLibraries)
* [Adobe Target Integration Client Libraries](sites-repository-restructuring-in-aem-6-4.md#AdobeTargetIntegrationClientLibraries)
* [WCM Foundation Client Libraries](sites-repository-restructuring-in-aem-6-4.md#WCMFoundationClientLibraries)

---

## With 6.4 Upgrade

### ContextHub Segments

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/segmentation/contexthub</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/apps/settings/wcm/segments</span><br /> </p> <p><span class="code">/conf/settings/settings/wcm/segments</span><br /> </p> <p><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/wcm/segments</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>If any new or modified ContextHub Segments are intended to be edited in source control rather than being edited in AEM, they must be migrated to the new location:</p> 
    <ol> 
     <li>Copy any new or modified ContextHub Segments from the previous location to the appropriate new location (/<span class="code">apps</span>, <span class="code">/conf/global</span> or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>)</li> 
     <li>Update references to ContextHub Segments in the previous location to the migrated ContextHub Segments in the new locations (<span class="code">/apps</span>, <span class="code">/conf/global</span>, <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>).</li> 
    </ol> <p>The following QueryBuilder query locates all references to ContextHub Segments in the Previous Locations.<br /> <br /> <span class="code">path=/content<br /> property=cq:segments<br /> property.operation=like<br /> property.value=/etc/segmentation/contexthub/%</span><br /> <br /> This can be executed via <a href="/content/help/en/experience-manager/6-4/sites/developing/using/querybuilder-api" target="_blank">AEM QueryBuilder Debugger UI</a>. Note that this is a traversing query, so do not run it against production, and ensure traversal limits adjusted as needed.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>ContextHub Segments persisted to the previous location display as read-only in <strong>AEM &amp;gt; Personalization &amp;gt; Audiences</strong>.</p> <p>If ContextHub Segments are to be editable in AEM, they must be migrated to the new location (<span class="code">/conf/global</span> or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>). Any new ContentHub Segments segments created in AEM are persisted to the new location (<span class="code">/conf/global</span> or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>).</p> <p>AEM Sites Page Properties only allow either the Previous Location (<span class="code">/etc</span>) or a single new location (<span class="code">/apps</span>, <span class="code">/conf/global</span> or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>) to be selected, thus ContextHub Segments must be migrated accordingly.</p> <p>Any unused ContextHub Segments from AEM reference sites can be removed and not migrated to the New Location:</p> 
    <ul> 
     <li>/etc/segmentation/geometrixx/</li> 
     <li>/etc/segmentation/geometrixx-outdoors</li> 
    </ul> <p>Note: If ClientContext is in use, it is recommended to convert to ContextHub.</p> </td> 
  </tr> 
 </tbody> 
</table>

---

## Prior to 6.5 Upgrade

### Adobe Analytics Client Libraries

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/clientlibs/foundation/sitecatalyst</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/cq/analytics/clientlibs/analytics</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any custom use of these Client Libraries should reference the Client Library by category, and not by path:</p> 
    <ol> 
     <li>Any references to the Client Library by path at the Previous Location should be updated to use <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#ReferencingClientSideLibraries" target="_blank">AEM's Client Library referencing framework</a>.</li> 
     <li>If AEM's Client Library referencing framework cannot be used, the absolute path of the Client Libraries can be referenced via AEM's Client Library Proxy servlet. 
      <ul> 
       <li><span class="code">/etc.clientlibs/cq/analytics/clientlibs/sitecatalyst/appmeasurement.js</span></li> 
       <li><span class="code">/etc.clientlibs/cq/analytics/clientlibs/sitecatalyst/plugins.js</span></li> 
       <li><span class="code">/etc.clientlibs/cq/analytics/clientlibs/sitecatalyst/sitecatalyst.js</span></li> 
       <li><span class="code">/etc.clientlibs/cq/analytics/clientlibs/sitecatalyst/tracking.js</span></li> 
       <li><span class="code">/etc.clientlibs/cq/analytics/clientlibs/sitecatalyst/util.js</span></li> 
      </ul> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Editing of these Client Libraries was never supported.</p> <p>To obtain the Client Library categories, visit each <span class="code">cq:ClientLIbraryFolder</span> node via CRXDELite and inspect the categories property.</p> 
    <ul> 
     <li><span class="code">/libs/cq/analytics/clientlibs/sitecatalyst/appmeasurement</span></li> 
     <li><span class="code">/libs/cq/analytics/clientlibs/sitecatalyst/plugins</span></li> 
     <li><span class="code">/libs/cq/analytics/clientlibs/sitecatalyst/sitecatalyst</span></li> 
     <li><span class="code">/libs/cq/analytics/clientlibs/sitecatalyst/tracking</span></li> 
     <li><span class="code">/libs/cq/analytics/clientlibs/sitecatalyst/util</span></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Classic Microsoft Word to Web Page Designs

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/wordDesign</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/wcm/designs/wordDesign</span></p> <p><span class="code">/apps/settings/wcm/designs/wordDesign</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs.</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location (<span class="code">/apps</span>).</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the cq:designPath property.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category (this requires updating Page implementation code).</li> 
     <li>Update AEM Dispatcher rules to allow serving of Client Libraries via the <span class="code">/etc.clientlibs/</span> proxy servlet.</li> 
    </ol> <p>For any Designs that NOT managed in SCM, and modified run-time via Design Dialogs:</p> 
    <ul> 
     <li>Do not move author-able Designs out of <span class="code">/etc</span>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mobile Device Emulator Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/mobile</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/mobile</span></p> <p><span class="code">/apps/settings/mobile</span></p> <p><span class="code">/conf/global/settings/mobile</span></p> <p><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/mobile</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td>Any new Mobile Device Emulator Configurations must be migrated to the New Location. 
    <ol> 
     <li>Copy any new Mobile Device Emulator Configurations from the Previous Location to the new location (<span class="code">/apps</span>, <span class="code">/conf/global</span>, <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>).</li> 
     <li>For any AEM Sites Pages that depend on these Mobile Device Emulator Configurations, update the Page's <span class="code"> 
       <g class="gr_ gr_26 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="26" id="26">
         jcr 
       </g> 
       <g class="gr_ gr_34 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="34" id="34">
         :content 
       </g></span> node: <br /> <span class="code">[cq:Page]/jcr:content@cq: 
       <g class="gr_ gr_24 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="24" id="24">
         deviceGroups 
       </g> = String[ mobile/groups/responsive ]</span></li> 
     <li>For any Editable Templates that depend on these Mobile Device Emulator Configurations, update the Editable Templates, pointing the <span class="code"> 
       <g class="gr_ gr_27 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="27" id="27">
         cq 
       </g>: 
       <g class="gr_ gr_25 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="25" id="25">
         deviceGroups 
       </g></span> to the New Location.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Mobile Device Emulator Configurations resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/mobile</span></li> 
     <li><span class="code">/conf/global/settings/mobile</span></li> 
     <li><span class="code">/apps/settings/mobile</span></li> 
     <li><span class="code">/libs/settings/mobile</span></li> 
     <li><span class="code">/etc/mobile</span></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Multi-site Manager Blueprint Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/blueprints</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/apps/msm</span> (Customer Blueprint configurations)</p> <p><span style="color: rgb(0,0,0);"><span class="code">/libs/msm</span> (Out Of the Box Blueprint configurations for Screens, Commerce)</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Multi-site Manager Blueprint Configurations must be migrated to the New Location (<span class="code">/apps</span>).</p> 
    <ol> 
     <li>Copy any new or modified Multi-site Manager Blueprint Configurations from the Previous Location to the New Location (<span class="code">/apps</span>).</li> 
     <li>Remove any migrated Multi-site Manager Blueprint Configurations from the Previous Location.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>All AEM provided Multi-site Manager Blueprint Configurations exist in the New Location in <span class="code">/libs</span>.</p> <p>Content does not reference the Multi-site Manager Blue Configurations therefore there are not content references to adjust.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Multi-site Manager Rollout Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/msm/rolloutConfigs</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/msm/wcm/rolloutconfigs</span></p> <p><span class="code">/apps/msm/wcm/rolloutconfigs</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Multi-site Manager Rollout Configurations must be migrated to the New Location.</p> 
    <ol> 
     <li>Copy any new or modified Multi-site Manager Rollout Configurations from the Previous Location to the new location (<span class="code">/apps</span>).</li> 
     <li>Update any references on AEM Pages to Multi-site Manager Rollout Configurations in the Previous Location, to point to their counterparts in the New Locations (<span class="code">/libs</span> or <span class="code">/apps</span>).</li> 
    </ol> <p>Remove migrated Multi-site Manager Rollout Configurations from the Previous Location.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>Failing to remove migrated Multi-site Manager Rollout Configurations from the Previous Location results in duplicate rollout options displayed to AEM authors.</td> 
  </tr> 
 </tbody> 
</table>

### Page Event Notification E-mail Template

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/notification/email/default/com.day.cq.wcm.core.page</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/notification-templates/com.day.cq.wcm.core.page</span></p> <p><span class="code">/apps/settings/notification-templates/com.day.cq.wcm.core.page</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>The only supported new Page Event Notification E-mail Templates are to support new locales.</p> <p>Page Event E-mail Template resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/etc/notification/email/default/com.day.cq.wcm.core.page</span></li> 
     <li><span class="code">/apps/settings/notification-templates/com.day.cq.wcm.core.page</span></li> 
     <li><span class="code">/libs/settings/notification-templates/com.day.cq.wcm.core.page</span></li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Any new or modified Page Event Notification E-mail Templates must be migrated to the new location under <span class="code">/apps</span>:</p> 
    <ol> 
     <li>Copy any new or modified Page Event Notification E-mail Templates from the Previous Location to the new location (<span class="code">/apps</span>).</li> 
     <li>Remove any migrated Page Event Notification E-mail Templates from the Previous Location.</li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Page Scaffolding

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/scaffolding</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/ 
      <g class="gr_ gr_8 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="8" id="8">
        wcm 
      </g>/template-types/scaffolding/scaffolding</span></p> <p><span class="code">/apps/settings/ 
      <g class="gr_ gr_9 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling" data-gr-id="9" id="9">
        wcm 
      </g>/template-types/scaffolding/scaffolding</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td>Scaffolding created under the Previous Location uses the legacy Scaffolding framework and cannot be migrated to the New Location. To align with the New Location any legacy Scaffolding must be re-developed using the supported Scaffolding framework.</td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Responsive Grid LESS

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/clientlibs/wcm/foundation/grid/grid_base.less</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/wcm/foundation/clientlibs/grid/grid_base.less</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any references to the Previous Location in custom LESS files must be updated to import from the New Location.</p> 
    <ul> 
     <li>Update any referencing custom LESS files that reference grid_base.less in the Previous Location to reference the new location.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>Referencing a non-existing <span class="code">grid_base.less</span> file results in the Layout Mode of the Page and Template Editor not working, and a disruption of page layout.</td> 
  </tr> 
 </tbody> 
</table>

### Static Template Designs

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/&amp;lt;custom-site&amp;gt;</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/apps/settings/wcm/designs/&amp;lt;custom-site&amp;gt;</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs.</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location (<span class="code">/apps</span>).</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a class="external-link" data-ext-link-init="true" target="_blank"></a><a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the <span class="code">cq:designPath</span> property via <strong>AEM &amp;gt; Sites &amp;gt; Custom Site Pages &amp;gt; Page Properties &amp;gt; Advanced Tab &amp;gt; Design Field</strong>.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category (this requires updating Page implementation code).</li> 
     <li>Update AEM Dispatcher rules to allow the serving of Client Libraries via the <span class="code">/etc.clientlibs/</span> proxy servlet.</li> 
    </ol> <p>For any Designs that NOT managed in SCM, and modified run-time via Design Dialogs:</p> 
    <ul> 
     <li>Do not move author-able Designs out of <span class="code">/etc</span>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>The recommended approach is to build AEM Sites and Pages using Editable Templates which use Structure Content and Policies in lieu of Designs.</td> 
  </tr> 
 </tbody> 
</table>

### Adobe Search and Promote Integration Client Libraries

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/clientlibs/foundation/searchpromote</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/cq/searchpromote/clientlibs/searchpromote</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any custom use of these Client Libraries should reference the Client Library by category, and not by path.</p> 
    <ol> 
     <li>Any references to the Client Library by path at the Previous Location should be updated to use <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#ReferencingClientSideLibraries" target="_blank">AEM's Client Library referencing framework</a>.</li> 
     <li>If AEM's Client Library referencing framework cannot be used, the absolute path of the Client Libraries can be referenced via AEM's Client Library Proxy servlet:</li> 
    </ol> 
    <ul> 
     <li><span class="code">/etc.clientlibs/cq/searchpromote/clientlibs/searchpromotei.js</span></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Editing of these Client Libraries was never supported.</p> <p>To obtain the Client Library categories, visit each cq:ClientLIbraryFolder node via CRXDELite and inspect the categories property:</p> 
    <ul> 
     <li><span class="code">/libs/cq/searchpromote/clientlibs/searchpromote</span></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Adobe Target Integration Client Libraries

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/clientlibs/foundation/target</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any custom use of these Client Libraries should reference the Client Library by category, and not by path.</p> 
    <ol> 
     <li>Any references to the Client Library by path at the Previous Location should be updated to use <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#ReferencingClientSideLibraries" target="_blank">AEM's Client Library referencing framework</a>.</li> 
     <li>If AEM's Client Library referencing framework cannot be used, the absolute path of the Client Libraries can be referenced via AEM's Client Library Proxy servlet:</li> 
    </ol> 
    <ul> 
     <li><span class="code">/etc.clientlibs/cq/testandtarget/clientlibs/testandtarget/testandtarget.js</span></li> 
     <li><span class="code">/etc.clientlibs/cq/testandtarget/clientlibs/testandtarget/atjs.js</span></li> 
     <li><span class="code">/etc.clientlibs/cq/testandtarget/clientlibs/testandtarget/atjs-integration.js</span></li> 
     <li><span class="code">/etc.clientlibs/cq/testandtarget/clientlibs/testandtarget/init.js</span></li> 
     <li><span class="code">/etc.clientlibs/cq/testandtarget/clientlibs/testandtarget/mbox.js</span></li> 
     <li><span class="code">/etc.clientlibs/cq/testandtarget/clientlibs/testandtarget/parameters.js</span></li> 
     <li><span class="code">/etc.clientlibs/cq/testandtarget/clientlibs/testandtarget/util.js</span></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Editing of these Client Libraries was never supported.</p> <p>To obtain the Client Library categories, visit each cq:ClientLIbraryFolder node via CRXDELite and inspect the categories property:</p> 
    <ul> 
     <li><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget/testandtarget</span></li> 
     <li><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget/atjs</span></li> 
     <li><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget/atjs-integration</span></li> 
     <li><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget/init</span></li> 
     <li><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget/mbox</span></li> 
     <li><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget/parameters</span></li> 
     <li><span class="code">/libs/cq/testandtarget/clientlibs/testandtarget/util</span></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### WCM Foundation Client Libraries

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/clientlibs/wcm/foundation</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/wcm/foundation/clientlibs</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any custom use of these Client Libraries should reference the Client Library by category, and not by path.</p> 
    <ol> 
     <li>Any references to the Client Library by path at the Previous Location should be updated to use <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#ReferencingClientSideLibraries" target="_blank">AEM's Client Library referencing framework</a>.</li> 
     <li>If AEM's Client Library referencing framework cannot be used, the absolute path of the Client Libraries can be referenced via AEM's Client Library Proxy servlet.</li> 
    </ol> 
    <ul> 
     <li><span class="code">/etc.clientlibs/wcm/foundation/clientlibs/accessibility.css</span></li> 
     <li><span class="code">/etc.clientlibs/wcm/foundation/clientlibs/main.css</span></li> 
     <li><span class="code">/etc.clientlibs/wcm/foundation/clientlibs/main.js</span></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Editing of these Client Libraries was never supported.</p> <p>To obtain the Client Library categories, visit each <span class="code">cq:ClientLIbraryFolder</span> node via CRXDELite and inspect the categories property:</p> 
    <ul> 
     <li><span class="code">/libs/wcm/foundation/clientlibs/accessibility</span></li> 
     <li><span class="code">/libs/wcm/foundation/clientlibs/main</span></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

