---
title: Content changes and Backwards Compatibility in AEM 6.4
seo-title: Content changes and Backwards Compatibility in AEM 6.4
description: null
seo-description: null
uuid: c5d1f692-1b91-4dcb-8f83-f71d65df3e16
content-encoding: ISO-8859-1
acrolinxstatus: not_checked
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/content-changes-in-aem64
contentOwner: sarchiz
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-02T05 38 39.802-0400
cq-lastmodifiedby: sarchiz
cq-lastreplicated: 2018-03-30T04 56 10.245-0400
cq-lastreplicatedby: sarchiz
cq-lastreplicationaction: Deactivate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: configuring
cq-template: /apps/help/templates/article-3
discoiquuid: 603ea10c-9fce-4920-98e3-77e178fdfcd4
donotlocalize: false
herogradient: light
jcr-created: 2018-03-28T07 28 59.014-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
pagecreatedat: en
pagelayout: video
preview: true
sha1: 8a0dd2f4a7625216027ada0a2c269ba719399d0d
sidecolumn: left
unpublishexternaldate: 2018-03-30T04 56 10.170-0400
unpublishinternaldate: 2018-03-30T04 56 10.170-0400
index: y
internal: n
snippet: y
translate: y
---

# Content changes and Backwards Compatibility in AEM 6.4

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous Location</strong><br /> </td> 
   <td><strong>New Location</strong></td> 
   <td><p><strong>Type of config</strong></p> <p><strong><em>Options are 1) absolute path, 2) only global 3) tenant-aware. </em></strong></p> </td> 
   <td><strong>Backwards Compatibility Approach</strong></td> 
   <td><strong>Requirements to align to latest model</strong></td> 
   <td><strong>Additional commentary</strong></td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/clientlibs/fd/fp</span></td> 
   <td><span class="code">/libs/fd/fp/components</span></td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an instance that has been upgraded via an inplace upgrade. New clientlibs have the same category names along with the "<strong><span class="code">replaces</span></strong>" property to avoid merging of old and new clientlibs.</td> 
   <td>None</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/clientlibs/fd/rte</span></td> 
   <td><span class="code">/libs/fd/rte</span></td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an instance that has been upgraded via an inplace upgrade. New clientlibs have the same category names along with the "<strong><span class="code">replaces</span></strong>" property to avoid merging of old and new clientlibs.</td> 
   <td>None</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/clientlibs/fd/af</span></td> 
   <td><span class="code">/libs/fd/af/authoring/clientlibs</span></td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an instance that has been upgraded via an inplace upgrade. New clientlibs have the same category names along with the "<strong><span class="code">replaces</span></strong>" property to avoid merging of old and new clientlibs.</td> 
   <td>None</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/clientlibs/fd/themes/themeLibrary</span></td> 
   <td>This no longer features as part of the AEM 6.4 out of the box package.</td> 
   <td>N/A</td> 
   <td>Out of the box themes in Adaptive Forms. Will be persisted on an inplace upgraded set up.</td> 
   <td>This is partly user generated content. This will be delivered as a reference content package with the <span class="code">aem-forms-reference-themes</span> name.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/clientlibs/fd/expeditor</span></td> 
   <td><span class="code">/libs/fd/expeditor/clientlibs</span></td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an instance that has been upgraded via an inplace upgrade. New clientlibs have the same category names along with the "<strong><span class="code">replaces</span></strong>" property to avoid merging of old and new clientlibs.</td> 
   <td>None<p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/designs/fd/fp</span></td> 
   <td><span class="code">/libs/fd/fp</span></td> 
   <td>N/A</td> 
   <td>Legacy Forms Portal out of the box templates. They will be persisted on an inplace upgraded setup.</td> 
   <td>In the listing of templates, the word<em> "deprecated</em>" will be added to the title In order to differentiate them with the newer templates.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/clientlibs/fd/fmaddon</span></td> 
   <td><span class="code">/libs/fd/fmaddon</span></td> 
   <td>N/A</td> 
   <td>Legacy Analytics and Target clientlibs which are not meant to be directly consumed. Will be cleaned up after upgrade using a clean up filter.</td> 
   <td>None</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/aep</span></td> 
   <td><span class="code">/var/fd/content/annotations</span></td> 
   <td>N/A</td> 
   <td>Legacy Correspondence Management annotation files. Not meant to be directly consumed. Will be cleaned up after upgrade using a clean up filter.</td> 
   <td>These will be cleaned up after upgrade using a clean up filter.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p><span class="code">/etc/cloudservices/typekit</span></p> <p><span class="code">/etc/cloudservices/recaptcha</span></p> <p><span class="code">/etc/cloudservices/echosign</span></p> </td> 
   <td><p><span class="code">/conf/&lt;tenantid&gt;/settings/cloudconfigs/typekit</span></p> <p><span class="code">/conf/&lt;tenantid&gt;/settings/cloudconfigs/recaptcha</span></p> <p><span class="code">/conf/&lt;tenantid&gt;/settings/cloudconfigs/echosign</span></p> </td> 
   <td>tenant-aware</td> 
   <td>Legacy cloudservices. Will be persisted on an inplace upgraded setup. Code to list and read them is still present in the product as a fallback.</td> 
   <td>Lazy content migration utility can be triggered from Forms Migration UI, in order to automatically convert to the new path.<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/cloudservices/fdm</span></td> 
   <td><span class="code">/conf/&lt;tenantid&gt;/settings/cloudconfigs/fdm</span></td> 
   <td>tenant-aware</td> 
   <td>Legacy cloudservices. Will be persisted on an inplace upgraded setup. Code to list and read them is still present in the product as a fallback.</td> 
   <td>Lazy content migration utility can be triggered from Forms Migration UI, in order to automatically convert to the new path.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/dam/adhocassetshare</span></td> 
   <td><span class="code">/libs/settings/dam/adhocassetshare</span></td> 
   <td>tenant-aware</td> 
   <td>Legacy content structures are honored with a higher priority than new, out of the box ones.</td> 
   <td>Project level customizations need to be cut and pasted under the equivalent <span class="code">/apps</span> or <span class="code">/conf</span> paths as applicable.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/dam/workflow/notification/email/downloadasset</span></td> 
   <td><span class="code">/libs/settings/dam/workflow</span></td> 
   <td>tenant-aware</td> 
   <td>Legacy content structures are honored with a higher priority than new, out of the box ones.</td> 
   <td>Project level customizations need to be cut and pasted under the equivalent <span class="code">/apps</span> or <span class="code">/conf</span> paths as applicable.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/dam/drm/licenses/</span></td> 
   <td><span class="code">/libs/settings/dam/drm</span></td> 
   <td>absolute path</td> 
   <td>Legacy content structures are honored with a higher priority than new, out of the box ones.</td> 
   <td>Project level customizations need to be cut and pasted under the equivalent <span class="code">/apps</span> or <span class="code">/conf</span> paths as applicable.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/dam/indesign/scripts</span></td> 
   <td><span class="code">/libs/settings/dam/indesign</span></td> 
   <td>tenant-aware</td> 
   <td>Legacy content structures are honored with a higher priority than new, out of the box ones.</td> 
   <td><p>Project level customizations need to be cut and pasted under the equivalent <span class="code">/apps</span> or <span class="code">/conf</span> paths as applicable.</p> <p>If you are running a customized Asset Ingestion workflow references to the old location in /etc wold still exist in the Media Extraction Process Configuration. Along with moving the scripts out of /etc to the equivalent /apps and /conf paths, customized Media Extraction process arguments need to be changed from absolute to relative paths, to accomodate for the changes.</p> <p>For more info, see <a href="/content/help/en/experience-manager/6-2/assets/using/indesign">this page</a>.</p> <p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/dam/video</span></td> 
   <td><span class="code">/libs/settings/dam/video</span></td> 
   <td>tenant-aware</td> 
   <td>Legacy content structures are honored with a higher priority than new, out of the box ones.</td> 
   <td>Project level customizations need to be cut and pasted under the equivalent <span class="code">/apps</span> or <span class="code">/conf</span> paths as applicable.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/notification/email/default</span></td> 
   <td><span class="code">/libs/settings/dam/notification</span></td> 
   <td>tenant-aware</td> 
   <td>Legacy content structures are honored with a higher priority than new, out of the box ones.</td> 
   <td>None</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/designs</span><br /> </td> 
   <td><span class="code">/libs/settings/wcm/designs</span></td> 
   <td>Absolute Path</td> 
   <td><p>Consuming Services are aware of old location.</p> <p>Configurations from legacy location are considered</p> </td> 
   <td><br /> Move custom content from <span class="code">/etc/design</span> to <span class="code">/apps/settings/wcm/design</span> for alingment with the new repository structure. In the future, consider upgrading your sites to use editable templates functionality, which replaces the need for design mode and thus this content.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p><span class="code">/etc/clientlibs/foundation/asseteditor</span></p> <p><span class="code">/etc/clientlibs/foundation/assetshare</span></p> <p><span class="code">/etc/clientlibs/foundation/assetinsights</span></p> </td> 
   <td><span class="code">/libs/dam/clientlibs</span></td> 
   <td>N/A</td> 
   <td>Legacy clientlibs have different client category names.</td> 
   <td>None</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/tags</span></td> 
   <td><span class="code">/content/cq:tags</span></td> 
   <td>N/A</td> 
   <td>The Tag Manager API supports both the legacy and the new location. When the component starts, it will detect if it is running on a upgraded instance or a legacy one, and uses the appropiate location.<br /> </td> 
   <td><p>In order to properly align to the new model, you need to:</p> 
    <ol> 
     <li>First, replace the references to the old model (<span class="code">/etc/tags</span>) with the new one (<span class="code">/content/cq:tags</span>) by using <span class="code">tagID</span></li> 
     <li>Log in to CRXDE Lite</li> 
     <li>Move the tags from <span class="code">/etc/tags</span> to <span class="code">/content/cq:tags</span></li> 
     <li>Restart the component<span class="code">.<br /> </span></li> 
    </ol> <p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/scaffolding</span></td> 
   <td><p><span class="code">/libs/settings/wcm/template-types/scaffolding/scaffolding</span></p> <p><span class="code">/apps/settings/wcm/template-types/scaffolding/scaffolding</span></p> </td> 
   <td>absolute path</td> 
   <td>The components in the old location under <span class="code">/etc/scaffolding</span> will continue to function, but have been deprecated.</td> 
   <td>Adobe recommends you use the new scaffold components under the new location.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/blueprints</span></td> 
   <td><p><span class="code">/apps/msm</span> for customer blueprint configurations</p> <p><span class="code">/libs/msm</span> for out of the box Screens and Commerce blueprint configurations</p> </td> 
   <td>absolute path</td> 
   <td><p>Consuming Services are aware of the old location.</p> <p>Configurations from legacy location are considered.</p> </td> 
   <td>The configurations need to be copied over to the new locations.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/mobile</span></td> 
   <td><span class="code">/libs/settings/mobile</span></td> 
   <td>tenant-aware</td> 
   <td>The feature leverages the Configuration Manager and still supports the old location as fallback.</td> 
   <td>
    <ol> 
     <li>Relocate the configurations from <span class="code">/etc</span> to <span class="code">/conf/&lt;tenant&gt;/settings/mobile</span></li> 
     <li>Then, update the reference in the content as follows:</li> 
    </ol> <p><span class="code">/content/&lt;tenant&gt;/jcr:content/cq:deviceGroups{String[]}=mobile/groups/responsive</span></p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/msm/rolloutConfigs</span></td> 
   <td><span class="code">/libs/msm/wcm/rolloutconfigs</span></td> 
   <td>N/A</td> 
   <td><p>Consuming Services are aware of the old location.</p> <p>If configurations are detected in the legacy location, they will be used.</p> </td> 
   <td>To align with the new model, configurations need to be created in the new locations, and the old ones under <span class="code">/etc</span> must be deleted.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/segmentation/contexthub</span></td> 
   <td><span class="code">/conf/we-retail/settings/wcm/segments</span></td> 
   <td>tenant-aware</td> 
   <td><p>Segments from the old location:</p> 
    <ul> 
     <li>stay in read-only mode in audience console</li> 
     <li>can be still loaded on page (if the given path is selected in <strong>Page Properties &gt; Personalization &gt; Segments Path</strong>)</li> 
     <li>can be used for content targetting</li> 
    </ul> </td> 
   <td>You can use the <a href="/upgrading-code-and-customizations.html?#MigrateConfigurations" target="_blank">Segments Migration Tool</a> to migrate to the new location.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/social/config/languageOpts</span></td> 
   <td><span class="code">/libs/social/translation/languageOpts</span></td> 
   <td>N/A</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/community/templates</span></td> 
   <td><span class="code">/libs/settings/community/templates</span></td> 
   <td> </td> 
   <td><p>The code is aware of the old templates location. If customers have existing templates, then they would be referred and read/write will be done from <span class="code">/etc</span>.</p> <p><br /> For email templates, if the customer was already having his custom templates at another path by configuring <strong>Templates root</strong> path in <strong>AEM Communities Email Reply Configuration</strong> then it would stay as it is.</p> </td> 
   <td><p>A migration untility to align to the latest model can be found at <a href="https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/master/bundles/communities-template-migration" target="_blank">this location</a>.</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><span class="code">/etc/community/badging</span></td> 
   <td><p><strong>Badge Rules:</strong></p> <p><span class="code">/libs/settings/community/badging</span></p> <p><strong>Badge Images:</strong></p> <p>The out of the box images in the old location at <span class="code">/etc/community/badging/images</span> are moved to <span class="code">/libs/community/badging/images </span> </p> <p> </p> <p>Custom images are moved to <span class="code">/content/community/badging/images</span>.</p> <p> </p> </td> 
   <td>tenant-aware</td> 
   <td><p>The code is aware of the old badging paths.</p> <p><br /> It will check the existence of older paths<br /> first. If they are not present, it will use the new paths.</p> </td> 
   <td><p>Manual Migration is required in order to align to the latest model. Follow the steps below in order to achieve this:</p> 
    <ol> 
     <li>Create a site context bucket using the configuration browser under <strong>Tools</strong></li> 
     <li>Go to the site root</li> 
     <li>Set the <span class="code">cq:conf</span> property to the bucket path where you want to store all the configurations. The same can be set via the <strong>Site Edit Wizard - Set Cloud Config Input</strong>, and then saving the changes</li> 
     <li>Move the relevant badging rules and scoring rules from <span class="code">etc/community/*</span> to the site context bucket created in the previous step</li> 
     <li>Adjust the <span class="code">badgingRules</span> and <span class="code">scoringRules</span> properties on the site root to have relative references to the new rule locations. As an example, if <span class="code">cq:conf</span> is set to <span class="code">/conf/we-retail</span>, the value for <span class="code">badgingRules</span> will be <span class="code">community/badging/rules</span> if rules are now moved to this new bucket</li> 
     <li>Similarly, adjust the references to scoring rules in a badging rule node to have a relative path.</li> 
    </ol> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>/etc/cloudservices/facebookconnect</p> <p>/etc/cloudservices/twitterconnect</p> <p>/etc/cloudservices/pinterestconnect</p> </td> 
   <td><p>/conf/&lt;tenant&gt;/settings/cloudconfigs/facebookconnect</p> <p>/conf/&lt;tenant&gt;/settings/cloudconfigs/twitterconnect</p> <p>/conf/&lt;tenant&gt;/settings/cloudconfigs/pinterestconnect</p> </td> 
   <td>tenant-aware</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/community/scoring</td> 
   <td>/libs/settings/community/scoring</td> 
   <td> </td> 
   <td>The code is aware of the old badging paths.<br /> It always checks the existence of older paths<br /> first, if not present then it will fall back to new paths.</td> 
   <td><p>Manual Migration is Required</p> <p>Same as Badging rules above</p> </td> 
   <td><p>Custom Rules can go into /apps/settings/community/scoring/rules at deploy time as a package. OR can be created in conf/&lt;site-context&gt;/settings/community/scoring/rules via crxde.</p> <p>To use/consume rules from /conf , communities site must have cq:conf property set. If no cq:conf set, scoringrules would be directly read from the given path for property 'scoringRules' at site's root node e.g./content/we-retail/us/en/community/jcr:content</p> <p> </p> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/community/notifications</td> 
   <td>/libs/settings/community/notifications</td> 
   <td>Absolute Path</td> 
   <td><p>No Backward compatibility handling done in code to keep reading preferences from etc.</p> <p><strong>REASONS:</strong></p> 
    <ul> 
     <li>No UI to edit these preferences.</li> 
     <li>No Documentation to explain usage of these configs.</li> 
     <li>No instance/customer who reported customization for these.</li> 
    </ul> <p>Given to above points,No migration needed. Movement of OOTB preferences from etc to libs was sufficient</p> </td> 
   <td><p>manual migration needed if customer want to move to new paths under "/apps/settings". We are using granite conf manager.</p> <p>So, in that case they need to set the property mergeList = true on "/libs/settings/community/subscriptions" node and add an nt:unstructred child node.</p> <p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/community/subscriptions</td> 
   <td>/libs/settings/community/subscriptions</td> 
   <td>Absolute Path</td> 
   <td><p>No Backward compatibility handling done in code to keep reading preferences from etc.</p> <p><strong>REASONS:</strong></p> 
    <ul> 
     <li>No UI to edit these preferences.</li> 
     <li>No Documentation to explain usage of these configs.</li> 
     <li>No instance/customer who reported customization for these.</li> 
    </ul> <p>Given to above points,No migration needed. Movement of OOTB preferences from etc to libs was sufficient</p> </td> 
   <td><p>manual migration needed if customer want to move to new paths under</p> <p>"/apps/settings". We are using granite conf manager.</p> <p>So, in that case they need to set the property mergeList = true on "/libs/settings/community/subscriptions" node and add an nt:unstructred child node.</p> <p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>/etc/enablement/reporting/config</p> <p>/libs/social/config/reporting</p> </td> 
   <td>-</td> 
   <td>N/A</td> 
   <td><p>Internal path changes. No customer impact.</p> <p>Both of these paths are cleaned up and no more used.</p> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/notification</td> 
   <td>/libs/community/notifications</td> 
   <td>N/A</td> 
   <td>Internal path changes. No customer impact.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/social/notification/emailtemplates/enrollment</td> 
   <td>-</td> 
   <td>N/A</td> 
   <td>These paths were not used in 6.3. Removed.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/socialconfig/srpc/defaultconfiguration</td> 
   <td>/conf/global/settings/community/srpc/defaultconfiguration</td> 
   <td>global</td> 
   <td>Code is BC. It looks up for old path and then falls back to new path if former doesn't exist</td> 
   <td>Lazy Content Migration Task available at<br /> <a href="https://git.corp.adobe.com/CQ/compat/blob/master/bundles/codeupgrade/src/main/java/com/day/cq/compat/codeupgrade/impl/cq64/CQ64CommunitiesConfigsCleanupTask.java">CQ64CommunitiesConfigsCleanupTask.java</a></td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/watchwords</td> 
   <td>/libs/community/watchwords</td> 
   <td>N/A</td> 
   <td>Code is BC. It looks up for old path and then falls back to new path if former doesn't exist</td> 
   <td><p>Lazy Content Migration Task available at<br /> <a href="https://git.corp.adobe.com/CQ/compat/blob/master/bundles/codeupgrade/src/main/java/com/day/cq/compat/codeupgrade/impl/cq64/CQ64CommunitiesConfigsCleanupTask.java">CQ64CommunitiesConfigsCleanupTask.java</a></p> <p>Move watchwords from etc/watchwords to conf/global/settings/community/watchwords</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/cloudservices/socialdatastore</td> 
   <td>-</td> 
   <td>N/A</td> 
   <td>This in internal implementation.<br /> No more required. No customer impact</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/community/assets/images/siteblueprint</td> 
   <td>/libs/community/assets/images/siteblueprint</td> 
   <td>N/A</td> 
   <td>Internal path to store default images.<br /> No customer impact</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/scorm<br /> </td> 
   <td>/libs/dam/scorm</td> 
   <td>N/A</td> 
   <td>Internal path to store default images.<br /> No customer impact.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/forms/social</td> 
   <td>-</td> 
   <td>N/A</td> 
   <td>This in internal implementation.<br /> No more required. No customer impact</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/community/tenants</td> 
   <td>-</td> 
   <td>N/A</td> 
   <td>Multi Tenancy was not being used by any customer. Also, there were code issues seen<br /> in the existing implementation.<br /> It was decided to remove this as of now.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/clientlibs/ckeditor</td> 
   <td>/libs/clientlibs/ckeditor</td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an inplace upgraded set up. New clientlibs have the same category names along with the "<strong>replaces</strong>" property to avoid merging of old and new clientlibs.</td> 
   <td>Editing of these clientlibs was never supported and/or documented.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/instances</td> 
   <td>/var/workflow/instances</td> 
   <td>N/A</td> 
   <td>Legacy location used in processing in<br /> in-flight workflows. New workflows use new location.</td> 
   <td><p>All nelwly started workflows have instance information in<br /> the new /var location.</p> <p>Doc review issuse: <a href="https://jira.corp.adobe.com/browse/CQ-4226255"><img src="https://jira.corp.adobe.com/secure/viewavatar?size=xsmall&amp;avatarId=18818&amp;avatarType=issuetype" />CQ-4226255</a> - Review Documentation for workflow and workflow Editor In Progress</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/models</td> 
   <td><p>/libs/settings/workflow/models</p> <p>/conf/global/settings/workflow/models<br /> </p> <p>/var/workflow/models</p> </td> 
   <td>Absolute Path</td> 
   <td><p>Legacy location used if present and not existing in /libs or /conf. For OOTB models, customers will have to create override.</p> <p>Pacakge export needs to inlude the model in /libs or /conf and the run time model in /var/workflow/models</p> </td> 
   <td><p>All newly created models are created in /conf/global/settings location<br /> Any edits in /etc or /libs require user to conciously create an override in /cong/global/settings before editing can be done. The Edit button has to be selected, and it will cause the override in /conf to be created and editing allowed.</p> <p>Doc review issuse: <a href="https://jira.corp.adobe.com/browse/CQ-4226255"><img src="https://jira.corp.adobe.com/secure/viewavatar?size=xsmall&amp;avatarId=18818&amp;avatarType=issuetype" />CQ-4226255</a> - Review Documentation for workflow and workflow Editor In Progress</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/launcher</td> 
   <td><p>/libs/settings/workflow/launcher</p> <p>/conf/global/settings/workflow/launcher</p> </td> 
   <td>Absolute Path</td> 
   <td>Legacy location used if existing and not<br /> existing in /libs or /conf locations (so custom launchers are preserverd). For modified OOTB launchers, customer will need to create override.</td> 
   <td><p>Newly created/edited launcher configurations are in /conf location.</p> <p>Doc review issuse: <a href="https://jira.corp.adobe.com/browse/CQ-4226255"><img src="https://jira.corp.adobe.com/secure/viewavatar?size=xsmall&amp;avatarId=18818&amp;avatarType=issuetype" />CQ-4226255</a> - Review Documentation for workflow and workflow Editor In Progress</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/projects/dashboard/gadgets</td> 
   <td><p>/libs/cq/core/content/projects/dashboard/gadgets</p> <p>/apps/cq/core/content/projects/dashboard/gadgets</p> </td> 
   <td>N/A</td> 
   <td>For BC, the compat package needs to be installed to get the /etc/projects/dashboard/gadgets<br /> installed.</td> 
   <td>By default the legacy location gadgets not installed.<br /> Doc review issuse: <a href="https://jira.corp.adobe.com/browse/CQ-4226255"><img src="https://jira.corp.adobe.com/secure/viewavatar?size=xsmall&amp;avatarId=18818&amp;avatarType=issuetype" />CQ-4226255</a> - Review Documentation for workflow and workflow Editor In Progress</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/content/projects/translationjobs</td> 
   <td><p>/libs/cq/core/content/projects/dashboard/gadgets/translationjob</p> <p>/libs/cq/core/content/projects/dashboard/gadgets/translationsummary</p> </td> 
   <td>N/A</td> 
   <td>Same as /etc/projects/dashboard/gadgets</td> 
   <td>Same as /etc/projects/dashboard/gadgets</td> 
   <td>Same as /etc/projects/dashboard/gadgets</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/models</td> 
   <td><p>/libs/settings/workflow/models</p> <p>/conf/global/settings/workflow/models</p> </td> 
   <td>Absolute Path (as above)</td> 
   <td>See: <a href="https://jira.corp.adobe.com/browse/GRANITE-13884">GRANITE-13884</a> above</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/notification</td> 
   <td><p>/libs/settings/workflow/notification</p> <p>/conf/global/settings/workflow/notification</p> </td> 
   <td>Absolute Path</td> 
   <td><p>For BC, legacy location used if present.<br /> Previously, customers had to override OOTB templates by editing them in /etc. Now override should be stored in /conf/global.</p> <p>There is no UI to copy OOTB to override location.</p> </td> 
   <td>Doc review issuse: <a href="https://jira.corp.adobe.com/browse/CQ-4226255"><img src="https://jira.corp.adobe.com/secure/viewavatar?size=xsmall&amp;avatarId=18818&amp;avatarType=issuetype" />CQ-4226255</a> - Review Documentation for workflow and workflow Editor In Progress</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/scripts</td> 
   <td><p>/libs/workflow/scripts</p> <p>/apps/workflow/scripts</p> </td> 
   <td>Absolute Path</td> 
   <td><p>Strategy:</p> 
    <ul> 
     <li>Existing Workflow Model Steps that reference WF scripts in the legacy (/etc/workflow/scripts) location will continue to point to these scripts after upgrade, and execute properly.</li> 
    </ul> <p>Caveats:</p> 
    <ul> 
     <li>However, the AEM WebUI for authoring the WF Steps’ (Process, Splits, etc.) no longer lists scripts under `/etc/workflow/scripts` in the dropdown used select Workflow scripts <a href="https://jira.corp.adobe.com/browse/GRANITE-20775"><img src="https://jira.corp.adobe.com/secure/viewavatar?size=xsmall&amp;avatarId=18803&amp;avatarType=issuetype" />GRANITE-20775</a> - Workflow Process step does not display scripts from /etc/workflow/scripts In Progress</li> 
    </ul> </td> 
   <td><p>Things will work as expected if the associated workflow process step isn't edited. However, full backwards compatibility, including when steps are edited, do require a manual action by the customer post-upgrade:</p> 
    <ul> 
     <li>The scripts must be moved from <strong>/etc/workflow/scripts</strong> to <strong>/apps/workflow/scripts</strong></li> 
     <li>Any<strong> </strong>references to /etc/workflow/scripts in WF Steps (Process, ORs, etc) must be updated to reference the new /apps/workflow/scripts location.</li> 
    </ul> </td> 
   <td><p>Customer considerations:</p> 
    <ul> 
     <li>Editing and saving a WF Step (Process, Splits, etc.) that references a script under /etc/workflow/scripts will remove the script reference entirely.</li> 
    </ul> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/cloudservices/translation</td> 
   <td><p>/libs/settings/cloudconfigs/translation/translationcfg</p> <p>/conf/&lt;tenant&gt;/settings/cloudconfigs/translation/translationcfg</p> <p> </p> </td> 
   <td>tenant-aware</td> 
   <td>Legacy cloudservices. Will be persisted on an inplace upgraded set up. Code to list them and read them still present in the product as a fallback.</td> 
   <td><p>When a user want to move cloud configurations to /conf, he can either</p> 
    <ul> 
     <li>create configurations using new Touch UI OR</li> 
     <li>copy older configs from /etc/cloudservices/translation to respective new location(s)</li> 
    </ul> <p>Once this is done, the configs need to be associated with Sites via Sites → Properties.</p> <p><strong>NOTE</strong>: Translation connectors should be compatible for AEM 6.4 for this to work.</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/cloudservices/msft-translation</td> 
   <td><p>/libs/settings/cloudconfigs/translation/msft-translation</p> <p>/conf/&lt;tenant&gt;/settings/cloudconfigs/translation/msft-translation</p> </td> 
   <td>tenant-aware</td> 
   <td>Legacy cloudservices. Will be persisted on an inplace upgraded set up. Code to list them and read them still present in the product as a fallback.</td> 
   <td><p>When a user want to move cloud configurations to /conf, he can either</p> 
    <ul> 
     <li>create configurations using new Touch UI OR</li> 
     <li>copy older configs from /etc/cloudservices/translation to respective new location(s)</li> 
    </ul> <p>Once this is done, the configs need to be associated with Sites via Sites → Properties.</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/cloudsettings</td> 
   <td><p>/libs/settings/cloudsettings</p> <p>/conf/&lt;tenant&gt;/settings/cloudsettings</p> </td> 
   <td>tenant-aware</td> 
   <td><p>Existing entries under /etc/ remain in place on upgrade</p> <p>Accessing the cloud settings UI post-upgrade will copy over the existing cloud settings to the new structure, while preserving the existing content for backwards compatibility.</p> </td> 
   <td><p>Content models are the same, only location changed to align with context aware configurations.</p> <p>(Automatic) lazy migration task will perform the following:</p> 
    <ul> 
     <li>copy existing cloud settings in /etc/cloudsettings to /conf/global/settings/cloudsettings</li> 
     <li>remove all children of /etc/cloudsettings</li> 
    </ul> <p>Steps required by the customers post-upgrade and before running the lazy migration tasks:</p> 
    <ul> 
     <li>Update all references pointing to /etc/loudsettings/* to point to /conf/global</li> 
    </ul> <p>Caveat:</p> 
    <ul> 
     <li>/etc/cloudsettings container needs to be preserved</li> 
    </ul> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/replication/treeactivation</td> 
   <td>/libs/replication/treeactivation</td> 
   <td>N/A</td> 
   <td>Legacy UI page remains in place on upgrade.</td> 
   <td>No action required, no models involved. Classic UI page that moved.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/cloudservices/dmscene7</td> 
   <td>/conf/global/settings/cloudservices/dmscene7</td> 
   <td>only global</td> 
   <td><p>Cloud config for dynamic media - Scene7 (dynamicmedia_scene7 runmode) setup will stay at the same location. The process is working as-is. If the client needs to adjust cloud config value, then they have 2 options.</p> 
    <ol> 
     <li>Update an existing config via old cloud config UI.</li> 
     <li>Create a new cloud config via new touch UI. This will have higher precedence than the old one.</li> 
    </ol> </td> 
   <td><p>The customer can run migration script.</p> <p><a href="http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json">http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json</a></p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/viewers</td> 
   <td>/libs/dam/viewers</td> 
   <td>N/A</td> 
   <td>The viewer is served via proxy pointing to /etc/dam/viewers location with content inside /libs/dam/viewers. Therefore, no change required for the customer.</td> 
   <td>The viewer is served via proxy pointing to /etc/dam/viewers location with content inside /libs/dam/viewers. Therefore, no change required for the customer.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/jobs</td> 
   <td>/var/dam/jobs</td> 
   <td>N/A</td> 
   <td>Temp location to hold zip file for client to download. There is no need to update since when the client requests to download the asset. It will generate file in the new location.</td> 
   <td>Temp location to hold zip file for client to download. There is no need to update since when the client requests to download the asset. It will generate file in the new location.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/presets/viewer</td> 
   <td><p>/libs/settings/dam/dm/presets/viewer</p> <p>/conf/global/settings/dam/dm/presets/viewer</p> </td> 
   <td>only global</td> 
   <td>For OOTB viewer preset, it will only available in the new location, while the custom viewer preset will still be in /etc until the client modified them. Then, it will be saved in the new location as lazy migration. Our embed image server will look into both legacy path (/etc) and new path (/conf) upon receiving a request. Therefore, the customer doesn't need to change their embed code or URL.</td> 
   <td><p>For OOTB viewer preset, it will only available in the new location. For custom viewer preset, the client will have to run migration script to move the node from /etc to /conf as <a href="http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json">http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json</a></p> <p>Similar to BC case, the client doesn't have to adjust their copyURL/embed code to point to /conf. The existing request to /etc will be re-route under the hood to the correct content from /conf.</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/imageserver/macros</td> 
   <td>/conf/global/settings/dam/dm/presets/macro</td> 
   <td>only global</td> 
   <td>The macro under /etc is still valid. If the customer makes a modification, the modified node will be moved to the new location under /conf as lazy migration.</td> 
   <td><p>The customer can run migration script.</p> <p><a href="http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json">http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json</a></p> <p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/video/dynamicmedia/Adaptive Video Encoding</td> 
   <td>/libs/settings/dam/dm/presets/video/jcr:content/Adaptive Video Encoding</td> 
   <td>N/A</td> 
   <td>OOTB video profile will be removed without updating asset folders' property to link to this profile. Encoding process has built-in translation between old and new location. It will convert the old path to look into the new profile path.</td> 
   <td>No need to do anything since this is OOTB profile. It will only exist in the new location.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/video/dynamicmedia</td> 
   <td>/conf/global/settings/dam/dm/presets/video/jcr:content</td> 
   <td>only global</td> 
   <td>Custom video profile will be kept as-is until the customer edits the profile. Then, it will be moved to the new location as lazy migration. This is similar to OOTB video preset on encoding look-up. The encoding process has built-in path translator to look into old location first and then the new location for video profile.</td> 
   <td><p>The customer can run migration script.</p> <p><a href="http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json">http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json</a></p> <p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/cloudservices/dynamicmediaservices</td> 
   <td>/conf/global/settings/dam/dm/cloudservices/dynamicmediaservices</td> 
   <td>only global</td> 
   <td><p>Cloud config for dynamic media hybrid setup (dynamicmedia runmode) will stay at the same location. The process is working as-is. If the client needs to adjust cloud config value, then they have 2 options.</p> 
    <ol> 
     <li>Update an existing config via old cloud config UI.</li> 
     <li>Create a new cloud config via new touch UI. This will have higher precedence than the old one.</li> 
    </ol> </td> 
   <td><p>The customer can run migration script.</p> <p><a href="http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.jso">http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.jso</a></p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/cloudservices/youtube</td> 
   <td>/libs/settings/dam/dm/youtube</td> 
   <td>only global</td> 
   <td><p>Cloud config for DM-Youtube setup will stay at the same location. The process is working as-is. If the client needs to adjust cloud config value, then they have 2 options.</p> 
    <ol> 
     <li>Update an existing config via old cloud config UI.</li> 
     <li>Create a new cloud config via new touch UI. This will have higher precedence than the old one.</li> 
    </ol> </td> 
   <td><p>The customer can run migration script.</p> <p><a href="http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json">http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json</a></p> <p> </p> <p> </p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dam/presets/analytics</td> 
   <td>/libs/settings/dam/dm/analytics</td> 
   <td>only global</td> 
   <td>This is generated automatically so there is nothing that the client can update.</td> 
   <td><p>The customer can run migration script.</p> <p><a href="http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json">http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json</a></p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>/etc/notification/email/default/com.day.cq.replication</p> <p>/etc/notification/email/default/com.day.cq.wcm.core.page</p> </td> 
   <td>/libs/settings/notification-templates</td> 
   <td>only global</td> 
   <td>The templates in /etc/notification/email/default/ are given preference over the /libs/settings/notification-templates.</td> 
   <td>If customers had modified those templates, they could now create new templates under /apps/settings/notification-templates and do their modifications there.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>/etc/msm/rolloutconfigs/launch</p> <p>/etc/msm/rolloutconfigs/pushonmodifyshallow</p> </td> 
   <td><p>/libs/msm/launches/rolloutconfigs/launch</p> <p>/libs/msm/launches/rolloutconfigs/pushonmodifyshallow</p> </td> 
   <td>N/A</td> 
   <td><p>Consuming Services are aware of old location.</p> <p>Configurations from legacy location / model are considered</p> </td> 
   <td><p>Service is able to map path of OOTB Configurations:</p> <p>Simply delete them.</p> <p>To meet 0dt requirement or on the long run:</p> <p>Script to move Configurations and references in Content.</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/commerce/products</td> 
   <td>/var/commerce/products</td> 
   <td>N/A</td> 
   <td><p>Old content remains in place and usable after upgrade.</p> <p>Provided lazy content migration task for migration to new location.</p> </td> 
   <td><p>The lazy migration task is implemented by <a href="https://jira.corp.adobe.com/browse/CQ-4217606">CQ-4217606</a> .</p> <p>It performs the following steps:</p> 
    <ul> 
     <li>adjusts references to old location to point to new location</li> 
     <li>moves content from old location to new location</li> 
     <li><p>removes old location to eventually activate the usage of new location in the whole system</p> </li> 
    </ul> <p>The locations covered by the task are:</p> 
    <ul> 
     <li>/etc/commerce/products</li> 
     <li>/etc/commerce/collections<br /> </li> 
     <li>/etc/commerce/orders<br /> </li> 
     <li>/etc/commerce/payment-methods<br /> </li> 
     <li>/etc/commerce/shipping-methods<br /> </li> 
    </ul> <p>For larger catalogs it's recommanded to run the commerce migration task individually by passing the following Java system property to AEM:</p> 
    <ul> 
     <li>proeprty name: com.adobe.upgrade.forcemigration</li> 
     <li>property value: com.day.cq.compat.codeupgrade.impl.cq64.CQ64CommerceMigrationTask</li> 
    </ul> <p>After migration AEM needs a restart.</p> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/commerce/orders</td> 
   <td>/var/commerce/orders</td> 
   <td>N/A</td> 
   <td><p>Old content remains in place and usable after upgrade.</p> <p>Provided lazy content migration task for migration to new location.</p> </td> 
   <td>See the description for /etc/commerce/products.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/commerce/collections</td> 
   <td>/var/commerce/collections</td> 
   <td>N/A</td> 
   <td><p>Old content remains in place and usable after upgrade.</p> <p>Provided lazy content migration task for migration to new location.</p> </td> 
   <td>See the description for /etc/commerce/products.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/commerce/classifications</td> 
   <td>/var/commerce/classifications</td> 
   <td>N/A</td> 
   <td>Currently this location is empty, migration task is not needed.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/commerce/shipping-methods</td> 
   <td>/var/commerce/shipping-methods</td> 
   <td>N/A</td> 
   <td><p>Old content remains in place and usable after upgrade.</p> <p>Provided lazy content migration task for migration to new location.</p> </td> 
   <td>See the description for /etc/commerce/products.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/commerce/payment-methods</td> 
   <td>/var/commerce/payment-methods</td> 
   <td>N/A</td> 
   <td><p>Old content remains in place and usable after upgrade.</p> <p>Provided lazy content migration task for migration to new location.</p> </td> 
   <td>See the description for /etc/commerce/products.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/designs/commerce/images/cancel.png</td> 
   <td>-</td> 
   <td>N/A</td> 
   <td>The removed content is part of the commerce backwards compatibility package.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/taskmanagement</td> 
   <td>/var/taskmanagement</td> 
   <td>N/A</td> 
   <td><p>New tasks created in /var/taskmanagement</p> <p>Existing tasks in legacy /etc/taskmanagement location still visible in inbox</p> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/clientlibs/foundation/sitecatalyst</td> 
   <td>/libs/cq/analytics/clientlibs/analytics</td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an inplace upgraded set up. New clientlibs have the same category names. Old clientlibs are removed by Vault filter.</td> 
   <td>Editing of these clientlibs was never supported and/or documented.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/clientlibs/foundation/personalization</td> 
   <td>/etc/clientlibs/foundation/personalization</td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an inplace upgraded set up. New clientlibs have the same category names. Old clientlibs are removed by Vault filter.</td> 
   <td>Editing of these clientlibs was never supported and/or documented.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/clientlibs/foundation/searchpromote</td> 
   <td>/libs/cq/searchpromote/clientlibs/searchpromote</td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an inplace upgraded set up. New clientlibs have the same category names. Old clientlibs are removed by Vault filter.</td> 
   <td>Editing of these clientlibs was never supported and/or documented.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/clientlibs/foundation/target</td> 
   <td>/libs/cq/target/clientlibs/target</td> 
   <td>N/A</td> 
   <td>Legacy clientlibs. Will be persisted on an inplace upgraded set up. New clientlibs have the same category names. Old clientlibs are removed by Vault filter.</td> 
   <td>Editing of these clientlibs was never supported and/or documented.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/packages</td> 
   <td>/var/workflow/packages</td> 
   <td>N/A</td> 
   <td><p>Packages created through the old miscadmin interface are still stored in /etc/workflow/packages</p> <p>Packages created outside of miscadmin (e.g. Sites workflows) continue to be stored in /var/workflow/packages</p> </td> 
   <td>Packages found in both /etc/workflow/packages and /var/workflow/packages can still be edited with the classic package editor (you can use it as the package editor URL). For better alignment with the new repository structure, /etc content can be copied to /var.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/<span class="ediffChangedA">etc</span>/workflow/instances</td> 
   <td>/var/workflow/instances</td> 
   <td>N/A</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/commerce/searchpromote</td> 
   <td>/var/cq/searchpromote</td> 
   <td>N/A</td> 
   <td>New physical location for Feed content, old URL continues to work and request is forwarded (by a ServletFilter) to new location.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/dtm-hook</td> 
   <td>/var/cq/dtm/web-hook</td> 
   <td>N/A</td> 
   <td>New physical location for DTM Web-Hooks, old URL continues to work and request is forwarded (by a ServletFilter) to new location.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/clientlibs/dtm</td> 
   <td>/var/cq/dtm/clientlibs</td> 
   <td>N/A</td> 
   <td>New physical location for DTM Client Libraries, old URL continues to work and request is forwarded (by a ServletFilter) to new location.</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/clientlibs/address</td> 
   <td>/libs/cq/address/clientlibs</td> 
   <td>N/A</td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/translation/supportedLanguages</td> 
   <td><p>/libs/settings/translation/supportedLanguages</p> <p>/apps/settings/translation/supportedLanguages</p> </td> 
   <td>absolute path</td> 
   <td>Caveats: one would need to add customized languages to the list.</td> 
   <td>Overlay and update the new list with additional languages (if any). Alternatively, copying the old list to /apps location would also work.</td> 
   <td>
    <div class="content-wrapper">
     <p>Added <span class="jira-issue" data-jira-key="CQ-4237887"><a class="jira-issue-key external-link" data-ext-link-init="true" target="_blank"><img class="icon" />CQ-4237887</a> - <span class="summary">[BC] read Translation supportedLanguages from /etc/translation/supportedLanguages on upgraded instance</span> <span class="aui-lozenge aui-lozenge-subtle aui-lozenge-complete jira-macro-single-issue-export-pdf">New</span></span> to fallback to older path in CFP/SP and <span><a class="external-link" data-ext-link-init="true" target="_blank">CQDOC-12213</a> to document the same.</span></p> 
    </div> <br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>/etc/workflow/models/translation/translation_rules.xml</td> 
   <td><p>/libs/settings/translation/rules/translation_rules.xml</p> <p>/apps/settings/translation/rules/translation_rules.xml</p> <p>/conf/global/settings/translation/rules/translation_rules.xml</p> </td> 
   <td>only global</td> 
   <td>Will be persisted on an inplace upgraded set up. Code to list them and read them still present in the product.</td> 
   <td>To persist user's changes, copy file from /etc to /libs or /conf. Alternatively,<strong> </strong>remove file from etc.</td> 
   <td> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

