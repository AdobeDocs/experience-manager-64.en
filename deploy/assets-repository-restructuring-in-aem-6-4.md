---
uuid: a4255c37-89c3-4db4-b41c-4d80f3ffd9a3
index: y
internal: n
snippet: y
translate: y
---

# Assets Repository Restructuring in AEM 6.4

As described on the parent [Repository Restructuring in AEM 6.4](repository-restructuring.md) page, customers upgrading to AEM 6.4 should use this page to assess the work effort associated with repository changes impacting the AEM Assets Solution. Some changes require work effort during the AEM 6.4 upgrade process, while others can be deferred until a 6.5 upgrade.

**With 6.4 Upgrade**

* [Misc](assets-repository-restructuring-in-aem-6-4.md#main-pars_header_366115091)

**Prior to 6.5 Upgrade**

* [Asset/Collection Event E-mail Notification Template](assets-repository-restructuring-in-aem-6-4.md#main-pars_header_1292890708)
* [Classic Asset Share Designs](assets-repository-restructuring-in-aem-6-4.md#ClassicAssetShareDesigns)
* [Download Asset E-mail Notification Template](assets-repository-restructuring-in-aem-6-4.md#DownloadAssetEmailNotificationTemplate)
* [Example DRM Licenses](assets-repository-restructuring-in-aem-6-4.md#ExampleDRMLicenses)
* [Link Share E-mail Notification Template](assets-repository-restructuring-in-aem-6-4.md#LinkShareEmailNotificationTemplate)
* [InDesign Workflow Scripts](assets-repository-restructuring-in-aem-6-4.md#InDesignWorkflowScripts)
* [Video Transcoding Configurations](assets-repository-restructuring-in-aem-6-4.md#VideoTranscodingConfigurations)
* [Misc](assets-repository-restructuring-in-aem-6-4.md#main-pars_header_284561465)

---

## With 6.4 Upgrade

### Misc

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td>/etc/dam/jobs</td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span style="color: rgb(0,0,0);">/var/dam/jobs</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>If any custom code is dependent on this location (ie. the code explicitly relies on this path) then the code must be updated to use the new location prior to upgrade; Ideally Java APIs are used when available to reduce dependencies on any specific path in the JCR.</p> <p>Temp location to hold zip file for client to download. There is no need to update since when the client requests to download the asset. It will generate file in the new location.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

---

## Prior to 6.5 Upgrade

### Asset/Collection Event E-mail Notification Template

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/notification/email/default</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/dam/notification</span></p> <p><span class="code">/apps/settings/dam/notification</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>If the e-mail templates were modified by the customer, then perform the following actions in order to align with the new repository structure:</p> 
    <ol> 
     <li>The <span class="code"><strong>/libs/settings/dam/notification</strong></span> e-mail template should be copied from <strong><span class="code">/etc/notification/email/default</span></strong> to <strong><span class="code">/apps/settings/notification/email/default</span></strong> 
      <ol> 
       <li>Because the destination is in<strong> <span class="code">/apps</span></strong> this change should be persisted in SCM.</li> 
      </ol> </li> 
     <li>Remove the folder: <strong><span class="code">/etc/dam/notification/email/default</span></strong> after the e-mail templates within it have been moved.<br /> 
      <ol> 
       <li>If no updates were made to the e-mail template under<strong> <span class="code">/etc/notification/email/default</span></strong>, the folder can be removed as the orginal e-mail template exists under <strong><span class="code">/libs/settings/notification/email/default</span></strong> as part of AEM 6.4 install.</li> 
      </ol> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Classic Asset Share Designs

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/designs/assetshare</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/wcm/designs/assetshare</span></p> <p><span class="code">/apps/settings/wcm/designs/assetshare</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For any Designs that are managed in SCM, and not written to at run-time via Design Dialogs, perform the following actions to align to the latest model:</p> 
    <ol> 
     <li>Copy the designs from the Previous Location to the New Location under <span class="code">/apps</span>.</li> 
     <li>Convert any CSS, JavaScript and static resources in the Design to a <a href="/content/help/en/experience-manager/6-4/sites/developing/using/clientlibs#main-pars_title_0" target="_blank">Client Library</a> with <span class="code">allowProxy = true</span>.</li> 
     <li>Update references to the Previous Location in the <span class="code">cq:designPath</span> property via <strong>AEM &amp;gt; DAM Admin &amp;gt; Asset Share Page &amp;gt; Page Properties &amp;gt; Advanced Tab &amp;gt; Design Field</strong>.</li> 
     <li>Update any Pages referencing the Previous Location to use the new Client Library category. This requires updating Page implementation code.</li> 
     <li>Update the Dispatcher rules to allow serving of Client Libraries via the <span class="code">/etc.clientlibs/</span> proxy servlet.</li> 
    </ol> <p>For any Designs that are not managed in SCM, and modified run-time via Design Dialogs, do not move authorable designs out of <span class="code">/etc</span>.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Download Asset E-mail Notification Template

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/workflow/notification/email/downloadasset</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/dam/workflownotification/email/downloadasset</span></p> <p><span class="code">/apps/settings/dam/workflownotification/email/downloadasset</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>If the e-mail templates (<strong>downloadasset</strong> or <strong>transientworkflowcompleted</strong>) have been modified, then follow the below procedure in order to align to the new structure:</p> 
    <ol> 
     <li>The updated e-mail template should be copied from <strong><span class="code">/etc/dam/workflow/notification/email/downloadasset</span></strong> to <strong><span class="code">/apps/settings/dam/workflow/notification/email/downloadasset</span></strong> 
      <ol> 
       <li>Because the destination is in<strong> <span class="code">/apps</span></strong> this change should be persisted in SCM.</li> 
      </ol> </li> 
     <li>Remove the folder: <span class="code"><strong>/etc/dam/workflow/notification/email/downloadasset</strong> </span>after the e-mail templates within it have been moved.<br /> 
      <ol> 
       <li>If no updates were made to the e-mail template under<strong> <span class="code">/etc</span></strong>, the folder can be removed as the orginal e-mail template exists under <strong><span class="code">/libs/settings/dam/workflownotification/email/downloadasset</span></strong> as part of AEM 6.4 install.</li> 
      </ol> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>While <span class="code">/conf/global/settings/dam/workflownotification/email/downloadasset</span> is technically supported for look-up (takes precedence before /apps via usual Sling CAConfig lookup, but after <span class="code">/etc</span>) the template could be placed in <span class="code">/conf/global/settings/dam/workflownotification/email/downloadasset</span>. However, this is not recommended as there is no runtime UI to facilitate the editting of the e-mail template.</td> 
  </tr> 
 </tbody> 
</table>

### Example DRM Licenses

| **Previous location** | `/etc/dam/drm/licenses/` |
|---|---|
| **New location(s)** | `/libs/settings/dam/drm` |
| **Restructuring guidance** |N/A |
| **Notes** |N/A |

###  Link Share E-mail Notification Template

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/adhocassetshare</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/dam/adhocassetshare</span></p> <p><span class="code">/apps/settings/dam/adhocassetshare</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>If the e-mail template was modified by the customer, then to align with the new repository structure:</p> 
    <ol> 
     <li>The updated e-mail template should be copied from <strong><span class="code">/etc/dam/adhocassetshare</span></strong> to <strong><span class="code">/apps/settings/dam/adhocassetshare</span></strong> 
      <ol> 
       <li>Because the destination is in<strong> <span class="code">/apps</span></strong> this change should be persisted in SCM.</li> 
      </ol> </li> 
     <li>Remove the folder: <strong><span class="code">/etc/dam/adhocassetshare</span></strong> after the e-mail templates within it have been moved.<br /> 
      <ol> 
       <li>If no updates were made to the e-mail template under<strong> <span class="code">/etc</span></strong>, the folder can be removed as the orginal e-mail template exists under <strong><span class="code">/libs/settings/dam/adhocassetshare</span></strong> as part of AEM 6.4 install.</li> 
      </ol> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>While <span class="code">/conf/global/settings/dam/adhocassetshare</span> is technically supported for look-up (it takes precedence before <span class="code">/apps</span> via usual Sling CAConfig lookup, but after <span class="code">/etc</span>), the template can be placed in <span class="code">/conf/global/settings/dam/adhocassetshare</span>. However, this is not recommended as there is no runtime UI to facilitate the editting of the e-mail template</td> 
  </tr> 
 </tbody> 
</table>

### InDesign Workflow Scripts

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/indesign/scripts</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/dam/indesign</span></p> <p><span class="code">/apps/settings/dam/indesign</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>To Align with the new repository structure:</p> 
    <ol> 
     <li>Copy all custom or modified scripts from <strong><span class="code">/etc/dam/indesign/scripts</span></strong> to <strong><span class="code">/apps/settings/dam/indesign/scripts</span></strong><br /> 
      <ol> 
       <li>Only copy new or modified scripts as unmodified scripts provided by AEM will be available via <strong><span class="code">/libs/settings</span></strong> in AEM 6.4</li> 
      </ol> </li> 
     <li>Locate all Workflow Models that use the Media Extraction Process WF Step and 
      <ol> 
       <li>For each instance of the Workflow Step, update the paths in config to point explicitly at the proper scripts under<strong> <span class="code">/apps/settings/dam/indesign/scripts</span></strong> or <strong><span class="code">/libs/settings/dam/indesign/scripts</span></strong> as appropriate.</li> 
      </ol> </li> 
     <li>Remove<strong> <span class="code">/etc/dam/indesign/scripts</span></strong> entirely.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>It is recommended customized scripts be stored under <span class="code">/apps</span>, since that is the location where code should be stored.</td> 
  </tr> 
 </tbody> 
</table>

### Video Transcoding Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/video</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/dam/video</span></p> <p><span class="code">/apps/settings/dam/video</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Project level customizations need to be cut and pasted under equivalent <span class="code">/apps</span> or <span class="code">/conf</span> paths as applicable.</p> <p>To align with the AEM 6.4 repository structure:</p> 
    <ol> 
     <li>Copy any modified video configurations from <span class="code">/etc/dam/video</span> to <span class="code">/apps/settings/dam/video</span></li> 
     <li>Remove <span class="code">/etc/dam/video</span></li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Viewer Preset Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/presets/viewer</span></td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/libs/settings/dam/dm/presets/viewer</span></p> <p><span class="code">/conf/global/settings/dam/dm/presets/viewer</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>For the out of the box Viewer Preset, it will only available in the new location.</p> <p>For the Custom Viewer preset:</p> 
    <ul> 
     <li>you will have to run a migration script to move the node from <span class="code">/etc</span> to <span class="code">/conf</span>. The script is located at <em>http://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></li> 
     <li>or you can edit the configuration and they will be auto-saved to the new location.</li> 
    </ul> <p>Note that you do not have to adjust their copyURL/embed code to point to <span class="code">/conf</span>. The existing request to <span class="code">/etc</span> will be re-routed to the correct content from <span class="code">/conf</span>.</p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr> 
 </tbody> 
</table>

### Misc

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/clientlibs/foundation/asseteditor</span></p> <p><span class="code">/etc/clientlibs/foundation/assetshare</span></p> <p><span class="code">/etc/clientlibs/foundation/assetinsights</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/dam/clientlibs</span></td> 
  </tr> 
  <tr> 
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>Adjust any references to point to the new resources under <span class="code">/libs</span> using the <span class="code">/etc.clientlibs/</span> allow proxy prefix.</p> <p>Finally, clean up by removing the folders for the migrated clientlibs from <span class="code">/etc/clientlibs/foundation/</span></p> </td> 
  </tr> 
  <tr> 
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr> 
 </tbody> 
</table>

