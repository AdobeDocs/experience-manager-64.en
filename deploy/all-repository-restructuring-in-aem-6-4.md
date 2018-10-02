---
uuid: b0eb07c3-287f-42f6-9434-5e947b0dca2b
index: y
internal: n
snippet: y
translate: y
---

# Common Repository Restructuring in AEM 6.4

As described on the parent [Repository Restructuring in AEM 6.4](repository-restructuring.md) page, customers upgrading to AEM 6.4 should use this page to assess the work effort associated with repository changes potentially impacting all solutions. Some changes require work effort during the AEM 6.4 upgrade process, while others can be deferred until a 6.5 upgrade.

**With 6.4 Upgrade**

* [Workflow Instances](all-repository-restructuring-in-aem-6-4.md#WorkflowInstances)
* [Workflow Models](all-repository-restructuring-in-aem-6-4.md#WorkflowModels)
* [Workflow Launchers](all-repository-restructuring-in-aem-6-4.md#WorkflowLaunchers)
* [Workflow Scripts](all-repository-restructuring-in-aem-6-4.md#WorkflowScripts)

**Prior to 6.5 Upgrade**

* [ContextHub Configurations](all-repository-restructuring-in-aem-6-4.md#ContextHubConfigurations)
* [Classic Cloud Services Designs](all-repository-restructuring-in-aem-6-4.md#ClassicCloudServicesDesigns)
* [Classic Dashboards Designs](all-repository-restructuring-in-aem-6-4.md#ClassicDashboardsDesigns)
* [Classic Reports Designs](all-repository-restructuring-in-aem-6-4.md#ClassicReportsDesigns)
* [Default Designs](all-repository-restructuring-in-aem-6-4.md#DefaultDesigns)
* [Adobe DTM JavaScript Endpoint](all-repository-restructuring-in-aem-6-4.md#AdobeDTMJavaScriptEndpoint)
* [Adobe DTM Web-Hook Endpoint](all-repository-restructuring-in-aem-6-4.md#AdobeDTMWebHookEndpoint)
* [Inbox Tasks](all-repository-restructuring-in-aem-6-4.md#InboxTasks)
* [Multi-site Manager Blueprint Configurations](all-repository-restructuring-in-aem-6-4.md#MultisiteManagerBlueprintConfigurations)
* [AEM Projects Dashboard Gadget Configurations](all-repository-restructuring-in-aem-6-4.md#AEMProjectsDashboardGadgetConfigurations)
* [Replication Notification E-mail Template](all-repository-restructuring-in-aem-6-4.md#ReplicationNotificationEmailTemplate)
* [Tags](all-repository-restructuring-in-aem-6-4.md#Tags)
* [Translation Cloud Services](all-repository-restructuring-in-aem-6-4.md#TranslationCloudServices)
* [Translation Languages](all-repository-restructuring-in-aem-6-4.md#TranslationLanguages)
* [Translation Rules](all-repository-restructuring-in-aem-6-4.md#TranslationRules)
* [Translation Widget Client Library](all-repository-restructuring-in-aem-6-4.md#TranslationWidgetClientLibrary)
* [Tree Activation Web Console](all-repository-restructuring-in-aem-6-4.md#TreeActivationWebConsole)
* [Vendor Translation Connector Cloud Services](all-repository-restructuring-in-aem-6-4.md#VendorTranslationConnectorCloudServices)
* [Workflow Notification Email Templates](all-repository-restructuring-in-aem-6-4.md#WorkflowNotificationEmailTemplates)

---

## With 6.4 Upgrade

### Workflow Models

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/models</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/workflow/models</span></p> <p><span class="code">/conf/global/settings/workflow/models</span></p> <p><span class="code">/var/workflow/models</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Workflow Models must be migrated to /conf/global/workflow/models.</p> 
    <ol> 
     <li>Deploy the modified Workflow Models into a local AEM 6.4 development instance, such that they exist in the Previous location.</li> 
     <li>Edit the Workflow Model using AEM's Workflow Model Editor at AEM &amp;gt; Tools &amp;gt; Workflow &amp;gt; Models.</li> 
     <li>When migrating modified AEM-provided Workflow Models 
      <ol> 
       <li>With the Workflow Model Editor open, modify the browser's address URL, and replace the path segment /libs/settings/workflow/models with /etc/workflow/models. 
        <ul> 
         <li>For example, change: <em>http://localhost:4502/editor.html<strong>/libs/settings/workflow/models</strong>/dam/update_asset.html</em> to <em>http://localhost:4502/editor.html<strong>/etc/workflow/models</strong>/dam/update_asset.html</em></li> 
        </ul> </li> 
      </ol> </li> 
     <li>Enable Edit mode in the Workflow Model Editor which will copy the Workflow Model definition to /conf/global/workflow/models.</li> 
     <li>Tap the Sync button to sync the changes to the Runtime Workflow Model under /var/workflow/models.</li> 
     <li>Export both the Workflow Model (/conf/global/workflow/models/&amp;lt;workflow-model&amp;gt;) and Runtime Workflow Model (/var/workflow/models/&amp;lt;workflow-model&amp;gt;) and integrate into the AEM project. 
      <ol> 
       <li>For example, export: 
        <ul> 
         <li><span class="code">/config/settings/workflow/models/dam/my_workflow_model</span><br /> and </li> 
         <li><span class="code">/var/workflow/models/dam/my_workflow_model</span></li> 
        </ul> </li> 
      </ol> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Workflow Model resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/conf/global/settings/workflow/models</span></li> 
     <li><span class="code">/libs/settings/workflow/models</span></li> 
     <li><span class="code">/etc/workflow/models</span></li> 
    </ol> <p>Thus, any customizations of AEM-provided Workflow Models persisted in the Previous location must be moved to /conf/global/settings/workflow/models if they are to be retained, otherwise they will be superseded by the AEM-provided Workflow Model definition in /libs/settings/workflow/models.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Workflow Instances

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/instances</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/var/workflow/instances</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>No action is required to align with the New Location.</p> <p>Historical Workflow Instances can safely continue residing in the Previous Location, and new Workflow Instances will be created in the New Location.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>Any explicit path references in 
    <g class="gr_ gr_26 gr-alert gr_gramm gr_inline_cards gr_run_anim Grammar only-ins replaceWithoutSep" data-gr-id="26" id="26">
      custom 
    </g> code to the Previous Location should also take into account the New Location. It is recommended that this code is refactored to use the AEM Workflow APIs.</td> 
  </tr> 
 </tbody> 
</table>

### Workflow Launchers

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/launcher/config</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/workflow/launcher/config</span></p> <p><span class="code">/conf/global/settings/workflow/launcher/config</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Workflow Launchers must be migrated to <span class="code">/conf/global/workflow/launcher/config</span>.</p> 
    <ol> 
     <li>Copy any new or modified Workflow Launcher configurations from the Previous Location to New Location (<span class="code">/conf/global</span>).</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Workflow Launcher resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/conf/global/settings/workflow/launcher</span></li> 
     <li><span class="code">/libs/settings/workflow/launcher</span></li> 
     <li><span class="code">/etc/workflow/launcher</span></li> 
    </ol> <p>Thus, any customizations of AEM-provided Workflow Launcher persisted in the Previous location must be moved to the New Location (<span class="code">/conf/global/settings/workflow/launcher</span> if they are to be retained, otherwise they will be superseded by the AEM-provided Workflow Launcher definition in <span class="code">/libs/settings/workflow/launcher</span>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Workflow Scripts

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/scripts</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/workflow/scripts</span></p> <p><span class="code">/apps/workflow/scripts</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Workflow Scripts must be migrated to the New Location and the referencing Workflow Models updated to reflect the New Location.</p> 
    <ol> 
     <li>Copy any new or modified Workflow Scripts from the Previous Location to the New Location.<br /> 
      <ul> 
       <li><span class="code">/apps/workflow/scripts</span> should be maintained in SCM.</li> 
      </ul> </li> 
     <li>Update any references to the Workflow Scripts at the Previous Location in Workflow Models to point to the New Locations.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>AEM 6.4 SP1, when it is released, makes it so this restructuring can be deferred until 6.5 
     <g class="gr_ gr_18 gr-alert gr_gramm gr_inline_cards gr_run_anim Grammar multiReplace" data-gr-id="18" id="18">
       upgrade 
     </g>.</p> <p>If upgrading to AEM 6.4 prior to AEM 6.4 SP1 being released, this restructuring should be performed as part of the upgrade project. Without doing so, editing and saving Workflow Steps referencing scripts in the Previous Location will remove the Workflow Script reference from the Workflow Step entirely, and only Workflow Scripts in New Locations will be available in the script selection drop-down.</p> </td> 
  </tr> 
 </tbody> 
</table>

---

## Prior to 6.5 Upgrade

### ContextHub Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/cloudsettings</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/cloudsettings</span></p> <p><span class="code">/conf/global/settings/cloudsettings</span></p> <p><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/cloudsettings</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified ContextHub Configurations must be migrated to the new location and the referencing AEM Sites pages must be updated to reflect the new location.</p> 
    <ol> 
     <li>Copy any new or modified ContextHub Configurations from the previous location to the new location.</li> 
     <li>Associate the applicable AEM configurations with the AEM content hierarchies. 
      <ol> 
       <li><strong>AEM Sites page hierarchies via AEM Sites &amp;gt; Page &amp;gt; Page Properties &amp;gt; Advanced Tab &amp;gt; Cloud Configuration</strong>.</li> 
      </ol> </li> 
     <li>Disassociate any migrated legacy ContextHub Configurations from the aforementioned AEM content hierarchies.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Classic Cloud Services Designs

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/cloudservices</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/wcm/designs/cloudservices</span></p> <p><span class="code">/apps/settings/wcm/designs/cloudservices</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs.</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location (<span class="code">/apps</span>).</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the <span class="code"> 
       <g class="gr_ gr_18 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="18" id="18">
         cq 
       </g>: 
       <g class="gr_ gr_19 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="19" id="19">
         designPath 
       </g></span> property.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category (this requires updating Page implementation code).</li> 
     <li>Update AEM Dispatcher rules to allow the serving of Client Libraries via the /etc.clientlibs/.. proxy servlet.</li> 
    </ol> <p>For any Designs that NOT managed in SCM, and modified run-time via Design Dialogs.</p> 
    <ul> 
     <li>Do not move author-able Designs out of <span class="code">/etc</span>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Classic Dashboards Designs

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/dashboards</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/wcm/designs/dashboards</span></p> <p><span class="code">/apps/settings/wcm/designs/dashboards</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs.</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location (/apps).</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the 
      <g class="gr_ gr_18 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="18" id="18">
        cq 
      </g>: 
      <g class="gr_ gr_19 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="19" id="19">
        designPath 
      </g> property.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category (this requires updating Page implementation code).</li> 
     <li>Update AEM Dispatcher rules to allow the serving of Client Libraries via the /etc.clientlibs/.. proxy servlet.</li> 
    </ol> <p>For any Designs that NOT managed in SCM, and modified run-time via Design Dialogs.</p> 
    <ul> 
     <li>Do not move author-able Designs out of <span class="code">/etc</span>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Classic Reports Designs

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/reports</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/wcm/designs/reports</span></p> <p><span class="code">/apps/settings/wcm/designs/reports</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs.</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location (/apps).</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the 
      <g class="gr_ gr_19 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="19" id="19">
        cq 
      </g>: 
      <g class="gr_ gr_20 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="20" id="20">
        designPath 
      </g> property.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category (this requires updating Page implementation code).</li> 
     <li>Update AEM Dispatcher rules to allow the serving of Client Libraries via the /etc.clientlibs/.. proxy servlet.</li> 
    </ol> <p>For any Designs that NOT managed in SCM, and modified run-time via Design Dialogs.</p> 
    <ul> 
     <li>Do not move author-able Designs out of <span class="code">/etc</span>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Default Designs

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/default</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/wcm/designs/default</span></p> <p><span class="code">/apps/settings/wcm/designs/default</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs.</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location (/apps).</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the 
      <g class="gr_ gr_18 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="18" id="18">
        cq 
      </g>: 
      <g class="gr_ gr_20 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="20" id="20">
        designPath 
      </g> property.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category (this requires updating Page implementation code).</li> 
     <li>Update AEM Dispatcher rules to allow the serving of Client Libraries via the /etc.clientlibs/.. proxy servlet.</li> 
    </ol> <p>For any Designs that NOT managed in SCM, and modified run-time via Design Dialogs.</p> 
    <ul> 
     <li>Do not move author-able Designs out of <span class="code">/etc</span>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Adobe DTM JavaScript Endpoint

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/clientlibs/dtm</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/var/cq/dtm/clientlibs</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>No action required.</p> <p>The public previous location acts as a proxy endpoint for the private new location.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Adobe DTM Web-Hook Endpoint

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dtm-hook</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/var/cq/dtm/web-hook</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>No action required.</p> <p>The public previous location acts as a proxy endpoint for the private new location.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Inbox Tasks

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/taskmanagement</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/var/taskmanagement</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td>Use the <strong>Inbox Purge Maintenance Task</strong> to remove old tasks from the previous location as needed.</td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>No action is required to migration Tasks to the new location.</p> 
    <ul> 
     <li>Tasks present in the Previous Location continue to be available and function.</li> 
     <li>New Tasks are created in the New Location.</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Multi-site Manager Blueprint Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong><em></em>Previous location</strong></td> 
   <td><span class="code">/etc/blueprints</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/msm</span></p> <p><span class="code">/apps/msm</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td> 
    <ol> 
     <li>Copy custom configurations from <span class="code">/etc/blueprints</span> to <span class="code">/apps/msm</span>.</li> 
     <li>Remove <span class="code">/etc/blueprints</span>.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### AEM Projects Dashboard Gadget Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/projects/dashboard/gadgets</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/cq/core/content/projects/dashboard/gadgets</span></p> <p><span class="code">/apps/cq/core/content/projects/dashboard/gadgets</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified AEM Projects Dashboard Gadget Configurations must be migrated to the new location (<span class="code">/apps</span>).</p> 
    <ol> 
     <li>Copy any new or modified AEM Projects Dashboard Gadget Configurations from the previous location to the new location (<span class="code">/apps</span>). 
      <ol> 
       <li>Do not copy unmodified AEM Projects Dashboard Gadget Configurations as these now exist in the new location (<span class="code">/libs</span>).</li> 
      </ol> </li> 
     <li>Update any AEM Projects templates that reference the Previous Location to point to the appropriate new location.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>If the AEM 6.4 compatibility package is applied, it will be necessary to perform the repository alignment activities at the time of the compatibility package's removal.</td> 
  </tr> 
 </tbody> 
</table>

### Replication Notification E-mail Template

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/notification/email/default/com.day.cq.replication</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/notification-templates/com.day.cq.replication</span></p> <p><span class="code">/apps/settings/notification-templates/com.day.cq.replication</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Replication Notification E-mail Templates must be migrated to the new location (<span class="code">/apps</span>)</p> 
    <ol> 
     <li>Copy any new or modified Replication Notification E-mail Templates from the previous location to new location (<span class="code">/apps</span>).</li> 
     <li>Remove any migrated Replication Notification E-mail Templates from the previous location.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>The only supported new Replication Notification E-mail Templates are to support new locales.</p> <p>Replication Notification E-mail Template resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/etc/notification/email/default/com.day.cq.replication</span></li> 
     <li><span class="code">/apps/settings/notification-templates/com.day.cq.replication<br /> </span></li> 
     <li><span class="code">/libs/settings/notification-templates/com.day.cq.replication</span></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Tags

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/tags</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/content/cq:tags</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>All Tags must be migrated to <span class="code">/content/cq:tags</span>.</p> 
    <ol> 
     <li>Copy all Tags from the Previous Location to the New Location.</li> 
     <li>Remove all Tags from the Previous Location.</li> 
     <li>Via the AEM Web Console, restart the Day Communique 5 Tagging OSGi bundle at <em>http://serveraddress:serverport/system/console/bundles/com.day.cq.cq-tagging</em> for AEM to recognize the New Location contains content and should be used.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Restarting the Day Communique Tagging OSGi bundle will only register the New Location as the tag root if the Previous Location is empty.</p> <p>References to the Previous Location will continue to work after migrating to New Location for all functionality that leverages AEM's TagManager API for tag resolution.</p> <p>Any custom code that explicitly references the path <span class="code">/etc/tags</span> must be updated to <span class="code">/content/ 
      <g class="gr_ gr_14 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="14" id="14">
        cq 
      </g> 
      <g class="gr_ gr_16 gr-alert gr_gramm gr_inline_cards gr_run_anim Style replaceWithoutSep" data-gr-id="16" id="16">
        :tags 
      </g></span>, or preferably rewritten to leverage the TagManager Java API, in tandem with this migration.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Translation Cloud Services

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/cloudservices/translation</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/cloudconfigs/translation/translationcfg</span></p> <p><span class="code">/apps/settings/cloudconfigs/translation/translationcfg</span></p> <p><span class="code">/conf/global/settings/cloudconfigs/translation/translationcfg</span></p> <p><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/cloudconfigs/translation/translationcfg</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new Translation Cloud Services must be migrated to the new location (<span class="code">/apps</span>, <span class="code">/conf/global</span> or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>).</p> 
    <ol> 
     <li>Migrate existing configurations in the previous location to the new location. 
      <ul> 
       <li>Manually recreate new Translation Cloud Services configurations via the AEM authoring UI at <strong>Tools &amp;gt; Cloud Services &amp;gt; Translation Cloud Services</strong>.<br /> OR </li> 
       <li>Copy any new Translation Cloud Services configurations from the Previous Location to the New Location (<span class="code">/apps</span>, <span class="code">/conf/global</span> or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>).</li> 
      </ul> </li> 
     <li>Associate the applicable AEM configurations with the AEM content hierarchies. 
      <ol> 
       <li>AEM Sites page hierarchies via <strong>AEM Sites &amp;gt; Page &amp;gt; Page Properties &amp;gt; Advanced Tab &amp;gt; Cloud Configuration</strong>.</li> 
       <li>AEM Experience Fragment hierarchies via <strong>AEM Experience Fragments &amp;gt; Experience Fragment &amp;gt; Properties &amp;gt; Cloud Services Tab &amp;gt; Cloud Configuration</strong>.</li> 
       <li>AEM Experience Fragment Folder hierarchies via <strong>AEM Experience Fragments &amp;gt; Folder &amp;gt; Properties &amp;gt; Cloud Services Tab &amp;gt; Cloud Configuration</strong>.<br /> </li> 
       <li>AEM Assets folder hierarchies via <strong>AEM Assets &amp;gt; Folder &amp;gt; Folder Properties &amp;gt; Cloud Services Tab &amp;gt; Configuration</strong>.</li> 
       <li>AEM Projects via <strong>AEM Projects &amp;gt; Project &amp;gt; Project Properties &amp;gt; Advanced Tab &amp;gt; Cloud Configuration</strong>.</li> 
      </ol> </li> 
     <li>Disassociate any migrated legacy Translation Cloud Services from the aforementioned AEM content hierarchies.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Translation Cloud Services resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/cloudconfigs/translations/translationcfg</span></li> 
     <li><span class="code">/conf/global/settings/cloudconfigs/translations/translationcfg</span></li> 
     <li><span class="code">/apps/settings/cloudconfigs/translations/translationcfg</span></li> 
     <li><span class="code">/libs/settings/cloudconfigs/translations/translationcfg</span></li> 
    </ol> <p>Migrated Translation Cloud Services must be compatible with AEM 6.4.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Translation Languages

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/translation/supportedLanguages</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/translation/supportedLanguages</span></p> <p><span class="code">/apps/settings/translation/supportedLanguages</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new or modified Translation Language definitions require a migration of all Translation Language definitions to the new location (<span class="code">/apps</span>).</p> 
    <ol> 
     <li>If any additions or modifications have been made to the Translation Language definitions, then copy all Translation Language definitions from the previous location to the new location (<span class="code">/apps</span>).</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Translation Language path resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/etc/translation/supportedLanguages</span></li> 
     <li><span class="code">/apps/settings/translation/supportedLanguage</span></li> 
     <li><span class="code">/libs/settings/translation/supportedLanguages</span></li> 
    </ol> <p>This resolution does not support a merging overlay, meaning the resolved path must contain all Supported Languages, and will not inherit Supported Languages from higher-order resolutions.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Translation Rules

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/models/translation/translation_rules.xml</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/translation/rules/translation_rules.xml</span></p> <p><span class="code">/apps/settings/translation/rules/translation_rules.xml</span></p> <p><span class="code">/conf/global/settings/translation/rules/translation_rules.xml</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>A modified Translation Rules XML file must be migrated to the new location (<span class="code">/apps</span>, or <span class="code">/conf/global</span>).</p> <p>1. Copy the modified Translation Rules XML file from the previous location to the new location.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Replication Translation Rules XML resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/conf/global/settings/translation/rules/translation_rules.xml</span></li> 
     <li><span class="code">/apps/settings/translation/rules/translation_rules.xml<br /> </span></li> 
     <li><span class="code">/etc/workflow/models/translation/translation_rules.xml<br /> </span></li> 
     <li><span class="code">/libs/settings/translation/rules/translation_rules.xml</span></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Translation Widget Client Library

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/translation/translationwidget</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/wcm/designs/translation/translationwidget</span></p> <p><span class="code">/apps/settings/wcm/designs/translation/translationwidget</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs.</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location (/apps).</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the 
      <g class="gr_ gr_18 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="18" id="18">
        cq 
      </g>: 
      <g class="gr_ gr_19 gr-alert gr_spell gr_inline_cards gr_run_anim ContextualSpelling ins-del multiReplace" data-gr-id="19" id="19">
        designPath 
      </g> property.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category (this requires updating Page implementation code).</li> 
     <li>Update AEM Dispatcher rules to allow the serving of Client Libraries via the /etc.clientlibs/.. proxy servlet.</li> 
    </ol> <p>For any Designs that NOT managed in SCM, and modified run-time via Design Dialogs.</p> 
    <ul> 
     <li>Do not move author-able Designs out of <span class="code">/etc</span>.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Tree Activation Web Console

| **Previous location** | `/etc/replication/treeactivation` |
|---|---|
| **New location(s)** | `/libs/replication/treeactivation` |
| **Restructuring guidance** |No action required. |
| **Notes** |The Tree Activation Web Console is now available via **Tools &gt; Deployment &gt; Replication &gt; Activate Tree**. |

### Vendor Translation Connector Cloud Services

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/cloudservices/&amp;lt;vendor&amp;gt;</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/cloudconfigs/translation/&amp;lt;vendor&amp;gt;</span></p> <p><span class="code">/apps/settings/cloudconfigs/translation/&amp;lt;vendor&amp;gt;<br /> </span></p> <p><span class="code">/conf/global/settings/cloudconfigs/translation/&amp;lt;vendor&amp;gt;<br /> </span></p> <p><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/cloudconfigs/translation/&amp;lt;vendor&amp;gt;</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any new Vendor Translation Connector Cloud Services must be migrated to the new location (<span class="code">/apps</span>, <span class="code">/conf/global</span> or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>).</p> 
    <ol> 
     <li>Migrate existing configurations in the Previous Location to the New Location. 
      <ul> 
       <li>Manually create net-new Vendor Translation Connector Cloud Services configurations via the <strong>AEM authoring UI at Tools &amp;gt; Cloud Services &amp;gt; Translation Cloud Services</strong>.<br /> OR </li> 
       <li>Copy any new Vendor Translation Connector Cloud Services configurations from previous location to the new location (<span class="code">/apps</span>, <span class="code">/conf/global </span>or <span class="code">/conf/&amp;lt;tenant&amp;gt;</span>).</li> 
      </ul> </li> 
     <li>Associate the applicable AEM configurations with the AEM content hierarchies. 
      <ol> 
       <li>AEM Sites page hierarchies via <strong>AEM Sites &amp;gt; Page &amp;gt; Page Properties &amp;gt; Advanced Tab &amp;gt; Cloud Configuration</strong>.</li> 
       <li>AEM Experience Fragment hierarchies via <strong>AEM Experience Fragments &amp;gt; Experience Fragment &amp;gt; Properties &amp;gt; Cloud Services Tab &amp;gt; Cloud Configuration</strong>.</li> 
       <li>AEM Experience Fragment Folder hierarchies via <strong>AEM Experience Fragments &amp;gt; Folder &amp;gt; Properties &amp;gt; Cloud Services Tab &amp;gt; Cloud Configuration</strong>.</li> 
       <li>AEM Assets folder hierarchies via <strong>AEM Assets &amp;gt; Folder &amp;gt; Folder Properties &amp;gt; Cloud Services Tab &amp;gt; Configuration</strong>.</li> 
       <li>AEM Projects via <strong>AEM Projects &amp;gt; Project &amp;gt; Project Properties &amp;gt; Advanced Tab &amp;gt; Cloud Configuration</strong>.</li> 
      </ol> </li> 
     <li>Disassociate any migrated legacy Translation Cloud Services from the aforementioned AEM content hierarchies.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Translation Cloud Services resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/conf/&amp;lt;tenant&amp;gt;/settings/cloudconfigs/translations/&amp;lt;vendor&amp;gt;</span></li> 
     <li><span class="code">/conf/global/settings/cloudconfigs/translations/&amp;lt;vendor&amp;gt;</span></li> 
     <li><span class="code">/apps/settings/cloudconfigs/translations/&amp;lt;vendor&amp;gt;</span></li> 
     <li><span class="code">/libs/settings/cloudconfigs/translations/&amp;lt;vendor&amp;gt;</span></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Workflow Notification Email Templates

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/notification</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/workflow/notification</span></p> <p><span class="code">/conf/global/settings/workflow/notification</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Any modified Workflow Notification Email Templates must be migrated to the New Location (<span class="code">/conf/global</span>).</p> 
    <ol> 
     <li>Copy any modified Workflow Notification Email Templates from the previous location to the new location.</li> 
     <li>Remove migrated Workflow Notification Email Templates from the previous location.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Workflow Notification Email Template resolution occurs in the following order:</p> 
    <ol> 
     <li><span class="code">/etc/workflow/notification</span></li> 
     <li><span class="code">/conf/global/settings/workflow/notification</span></li> 
     <li><span class="code">/libs/settings/workflow/notification</span></li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

### Workflow Packages

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/workflow/packages</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/var/workflow/packages</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Existing Workflow Packages in the previous location should be migrated to the new location.</p> 
    <ol> 
     <li>Remove any Workflow Packages in the previous location that are not referenced by other content and are otherwise not required.</li> 
     <li>Move any Workflow Packages in the previous location that are not referenced by other content but otherwise required in the new location.</li> 
     <li>Leave any Workflow Packages that are referenced by other content in the previous location.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td><p>Workflow Packages created via the Classic UI Miscadmin console are persisted in the previous location, while all others are persisted to the new location.</p> <p>Workflow Packages stored in either the previous or lew locations can be managed via the Classic UI Miscadmin console.</p> </td> 
  </tr> 
 </tbody> 
</table>

