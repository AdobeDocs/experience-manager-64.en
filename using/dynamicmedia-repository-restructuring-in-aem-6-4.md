---
title: Dynamic Media Repository Restructuring in AEM 6.4
seo-title: Dynamic Media Repository Restructuring in AEM 6.4
description: null
seo-description: Learn how to make the necessary changes in order to migrate to the new repository structure in AEM 6.4 for Dynamic Media.
uuid: 68b6cdf5-aaa3-48f6-acac-fcffd5f79327
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/dynamicmedia-repository-restructuring-in-aem-6-4
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-07-27T04 43 06.364-0400
cq-lastmodifiedby: sarchiz
cq-lastreplicated: 2018-07-27T04 43 06.838-0400
cq-lastreplicatedby: sarchiz
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
cq-template: /apps/help/templates/article-3
discoiquuid: 565c3754-3b9a-4501-be8c-773b78d9c4ab
firstPublishExternalDate: 2018-07-27T04:43:06.329-0400
jcr-created: 2018-07-12T07 29 36.653-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-07-27T04:43:06.329-0400
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/repo_restructuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/repo_restructuring
pagecreatedat: en
publishexternaldate: 2018-07-27T04 43 06.329-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/dynamicmedia-repository-restructuring-in-aem-6-4.html
sha1: f44d7eff25077f9291a721fb6189a65cb5c3c15b
topicBrowsingSortDate: 2018-07-27T04:43:06.329-0400
index: y
internal: n
snippet: y
translate: y
---

# Dynamic Media Repository Restructuring in AEM 6.4

As described on the parent [Repository Restructuring in AEM 6.4](repository-restructuring.md) page, customers upgrading to AEM 6.4 should use this page to assess the work effort associated with repository changes impacting the Dynamic Media Solution. Some changes require work effort during the AEM 6.4 upgrade process, while others can be deferred until a 6.5 upgrade.

**Prior to 6.5 Upgrade**

* [Custom Adaptive Video Encoding Configurations](dynamicmedia-repository-restructuring-in-aem-6-4.md#main-pars_header_1871878606)
* [Dynamic Media (DMS7) Cloud Configuration](dynamicmedia-repository-restructuring-in-aem-6-4.md#main-pars_header_682844765)
* [Dynamic Media (DM Hybrid) Cloud Service Configuration](dynamicmedia-repository-restructuring-in-aem-6-4.md#main-pars_header_501711721)
* [Dynamic Media - YouTube Cloud Service Configuration](dynamicmedia-repository-restructuring-in-aem-6-4.md#main-pars_header_1269596831)
* [Misc](dynamicmedia-repository-restructuring-in-aem-6-4.md#Misc)

## Prior to 6.5 Upgrade

### Custom Adaptive Video Encoding Configurations

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/video/dynamicmedia</span></td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/conf/global/settings/dam/dm/presets/video/jcr:content</span></td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>You can run the following migration script to migrate to the new location:</p> <p><em>http://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> <p>Alternatively, you can edit the configuration in AEM UI, and the changes will be saved to the new location.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamic Media (DMS7) Cloud Configuration

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/cloudservices/dmscene7</span></td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/conf/global/settings/cloudservices/dmscene7</span></td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>The customer can run a migration script at this location:<br /> </p> 
    <ul> 
     <li><em>http://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></li> 
     <li>Restart Dynamic Media OSGi bundle.</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr>
 </tbody>
</table>

### Dynamic Media (DM Hybrid) Cloud Service Configuration

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/cloudservices/dynamicmediaservices</span></td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/conf/global/settings/dam/dm/cloudservices/dynamicmediaservices</span></td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>You can run the migration script below in order to align to the latest model:</p> <p><em>http://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.jso</em></p> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamic Media - YouTube Cloud Service Configuration

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/cloudservices/youtube</span></td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/settings/dam/dm/youtube</span></td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>1. Unpublish all videos from YouTube<br /> 2. Create the YouTube Configuration using the new TouchUI (from <span class="code">/conf</span>) including copying all the Channels from the old location<br /> 3. Publish all videos back to YouTube.</p> <p>This will result in new YouTube URLs. If you do not unpublish prior to creating a new TouchUI YouTube config, then you will have multiple YouTube URLs listed under Properties because the recreated Channels will publish again if given the chance. This means you'll have useless URLs listed under Properties.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr>
 </tbody>
</table>

### Misc

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/imageserver/macros</span></td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/conf/global/settings/dam/dm/presets/macro</span></td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>The customer can run the below migration script.</p> <p><em>http://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> <p>Alternatively, you can edit the configuration in AEM UI, and the changes will be saved to the new location.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr>
 </tbody>
</table>

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><span class="code">/etc/dam/presets/analytics</span></td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><span class="code">/libs/settings/dam/dm/analytics</span></td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>The customer can run the below migration script.</p> <p><em>http://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A</td> 
  </tr>
 </tbody>
</table>

