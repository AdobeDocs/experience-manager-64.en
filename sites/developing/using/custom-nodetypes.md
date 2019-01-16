---
title: Custom Node Types
seo-title: Custom Node Types
description: null
seo-description: AEM is based on Sling and uses a JCR repository with node types offered by both, but AEM also provides a range of custom node types
uuid: ac6a1d54-9ceb-41af-a642-51e2e8019a27
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 7bbebdbb-1d0a-4a2e-9169-34844c4e2646
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Custom Node Types{#custom-node-types}

As CQ is based on Sling and uses a JCR repository, node types offered by both of these are available for use:

* [JCR Node Types](http://www.day.com/specs/jcr/2.0/3_Repository_Model.html#NodeTypes)
* [Sling Node Types](https://cwiki.apache.org/confluence/display/SLING/Sling+Node+Types)

In addition to these. CQ provides a range of custom node types.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:20.869-0500

<p>Taken from the CQ 5.3.0 branch (and compared with current versions):</p> 
<ul> 
 <li>http://svn.day.com/view/svn/cq5/trunk/content/jcr_root/libs/.../*.cnd</li> 
</ul> 
<p>A tool to generate the docu automatically (isn't standard javadocs) would be good - but not all comments use the same formatting (and proof-reading is good too). Currently using awk and sed to extract relevant information.<br /> </p> 
<p>Updates encountered for 5.4 are currently set as draft.<br /> </p> 
<p>Need confirmation of status on some node types flagged as ToDo.<br /> </p>

 -->

## Audit {#audit}

### cq:AuditEvent {#cq-auditevent}

**Description** Defines the node type of an audit event node.

* @prop cq:time
* @prop cq:userid
* @prop cq:path
* @prop cq:type
* @prop cq:category
* @prop cq:properties

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:20.963-0500

<p>Description needs more detail from RnD.<br /> </p>

 -->

**Definition** [cq:AuditEvent] - &#42; (undefined) - &#42; (undefined) multiple + &#42; (nt:base) = nt:base multiple version - cq:time (date) - cq:userid (string) - cq:path (string) - cq:type (string) - cq:category (string) - cq:properties (binary)

<!-- 

Comment Type: draft

<h2>Calendar</h2>

 -->

<!-- 

Comment Type: remark
Last Modified By: (ims-author-D9FB647253FD17BE0A4C98A6@AdobeID)
Last Modified Date: 2018-01-18T11:19:21.036-0500

<p>Calendar mixin as a marker for calendar subtrees.</p> 
<p>Removed for <a href="https://jira.corp.adobe.com/browse/DOC-6415">DOC-6415</a></p> 
<p>5.6.1 (1.3.12) and 6.0 (1.5.124) have<br /> /libs/social/calendar/nodestypes/calendar.cnd<br /> cq:Calendar<br /> cq:CalendarComponent<br /> cq:CalendarEvent<br /> cq:CalendarRecurrence<br /> cq:CalendarRecurrenceRule<br /> cq:CalendarTodo<br /> cq:Alarm<br /> cq:CalendarAttendee</p> 
<p>6.1 GA (1.7.197) does not have calendar.cnd</p>

 -->

## Comment {#comment}

<!-- 

Comment Type: remark
Last Modified By: (ims-author-D9FB647253FD17BE0A4C98A6@AdobeID)
Last Modified Date: 2018-01-18T11:19:21.082-0500

<p>UNSURE WHETHER THESE SHOULD BE UNDER<br /> develop/platform<br /> or<br /> develop/communities</p> 
<p>Updating per AEM 6.1 FP2 (1.8.269) /libs/social/commons/nodetypes/</p> 
<ul> 
 <li>comments.cnd 
  <ul> 
   <li>removed cq:Rating per <a href="https://jira.corp.adobe.com/browse/CQ-39458">CQ-39458</a></li> 
  </ul> </li> 
 <li>commentscontent.cnd</li> 
 <li>commentattachment.cnd</li> 
 <li>location.cnd</li> 
</ul> 
<p> </p>

 -->

### cq:Comment {#cq-comment}

**Description** Defines the nodetype of a comment node.

* @prop userIdentifier  
  The user identifier.

**Definition** [cq:Comment] > mix:title, mix:created, mix:language, nt:unstructured, cq:Taggable - email (string) - ip (string) - referer (string) - url (string) - userAgent (string) - userIdentifier (string) - authorizableId (string)

### cq:CommentAttachment {#cq-commentattachment}

**Description** Defines the nodetype of a commentattachment node

**Definition** [cq:CommentAttachment] > nt:file - &#42; (undefined) - &#42; (undefined) multiple

### cq:CommentContent {#cq-commentcontent}

**Description** Defines the nodetype of a comment content node

**Definition** [cq:Comment] > mix:title, mix:created, mix:language, nt:unstructured, cq:Taggable - email (string) - ip (string) - referer (string) - url (string) - userAgent (string) - userIdentifier (string) - authorizableId (string)

### cq:GeoLocation {#cq-geolocation}

**Description** A mixin that defines a geographic location in decimal degrees (DD)

* @prop latitude  
  latitude encoded as double using decimal degrees
* @prop longitude  
  longitude encoded as double using decimal degrees

**Definition** [cq:GeoLocation] mixin - latitude (double) - longitude (double)

### cq:Trackback {#cq-trackback}

**Description** Defines the node type of a trackback node.

**Definition** [cq:Trackback] > mix:title, mix:created, mix:language, nt:unstructured

<!-- 

Comment Type: draft

<h2>Content Sync</h2>

 -->

<!-- 

Comment Type: draft

<h3>cq:ContentSyncConfig</h3>

 -->

<!-- 

Comment Type: draft

<p><strong>FOR CQ5.4</strong></p> 
<p><strong>Description</strong></p> 
<p></p> 
<p>Defines a CQ Content Sync Configuration.</p> 
<p></p> 
<p><strong>Definition</strong></p> 
<p></p> 
<p>[cq:ContentSyncConfig] &gt; sling:Folder</p> 
<p></p>

 -->

<!-- 

Comment Type: draft

<h3>cq:ContentSyncHash</h3>

 -->

<!-- 

Comment Type: draft

<p><strong>FOR CQ 5.4</strong></p> 
<p><strong>Description</strong></p> 
<p></p> 
<p>Defines a mixin that adds a md5 hash.<br /> </p> 
<ul> 
 <li>@prop md5<br /> MD5 hash as hex string.<br /> </li> 
</ul> 
<p></p> 
<p><strong>Definition</strong></p> 
<p></p> 
<p>[cq:ContentSyncHash] mixin<br /> - md5 (string) copy</p> 
<p></p>

 -->

## Core {#core}

### cq:Page {#cq-page}

**Description** Defines the default CQ page.

* @node jcr:content  
  Primary content of the page.

**Definition** [cq:Page] > nt:hierarchyNode orderable + jcr:content (nt:base) = nt:unstructured copy primary + &#42; (nt:base) = nt:base version

### cq:PseudoPage {#cq-pseudopage}

**Description** Defines a mixin type that marks nodes as pseudo pages. This means they can be adapted for Page and WCM editing support.

**Definition** [cq:PseudoPage] mixin

### cq:PageContent {#cq-pagecontent}

**Description** Defines the default node for page content, with the minimum properties as used by WCM.

* @prop jcr:title  
  Title for the page.
* @prop jcr:description  
  Description of this page.
* @prop cq:template  
  Path to the template used to create the page.
* @prop cq:allowedTemplates  
  List of regular expressions used to determine the path(s) to allowed template.
* @prop pageTitle  
  Title usually displayed in the <title> tag.
* @prop navTitle  
  Title usually used in navigation.
* @prop hideInNav  
  Specifies whether the page should be hidden in the navigation.
* @prop onTime  
  Time when this page becomes valid.
* @prop offTime  
  Time when this page becomes invalid.
* @prop cq:lastModified  
  Date the page (or its paragraphs) was last modified.
* @prop cq:lastModifiedBy  
  Last user to change the page (or its paragraphs).
* @prop jcr:language  
  The language of page content.

>[!NOTE]
>
>It is not compulsory for page content to use this type.

**Definition** [cq:PageContent] > nt:unstructured, mix:title, mix:created, cq:OwnerTaggable, sling:VanityPath, cq:ReplicationStatus, sling:Resource orderable - cq:template (string) - cq:allowedTemplates (string) multiple - pageTitle (string) - navTitle (string) - hideInNav (boolean) - onTime (date) - offTime (date) - cq:lastModified (date) - cq:lastModifiedBy (string) - cq:designPath (string) - jcr:language (string)

### cq:Template {#cq-template}

**Description** Defines a CQ template.

* @node jcr:content  
  Default content for new pages.
* @node icon.png  
  A file that holds a characteristic icon.
* @node thumbnail.png  
  A file that holds a characteristic thumbnail image.
* @node workflows  
  Auto assign workflow configuration. The configuration will follow the structure below:  
  + workflows  
  + name1  
  - cq:path  
  - cq:workflowName

* @prop allowedParents  
  Regular expression patterns to determine the path(s) to templates allowed as parent templates.
* @prop allowedChildren  
  Regular expression patterns to determine the path(s) to templates allowed as child templates.
* @prop ranking  
  Position within the list of templates in the create page dialog.

**Definition** [cq:Template] > nt:hierarchyNode, mix:title - &#42; (undefined) - &#42; (undefined) multiple + &#42; (nt:base) = nt:base multiple version + jcr:content (nt:base) copy + icon.png (nt:file) copy + thumbnail.png (nt:file) copy + workflows (nt:base) copy - allowedParents (string) multiple - allowedChildren (string) multiple - ranking (long)

### cq:Component {#cq-component}

**Description** Defines a CQ component.

* @prop jcr:title   
  Title for the component.
* @prop jcr:description   
  Description of the component.
* @node dialog   
  Primary dialog.
* @prop dialogPath  
  Primary dialog path (alternative to dialog).
* @node design_dialog   
  Design dialog.
* @prop cq:cellName   
  Name of the design cell.
* @prop cq:isContainer   
  Indicates whether this is a container component. This forces the cell names of child components to be used instead of path names. For example, the `parsys` is a container component. If this value is not defined, the check is made based on the existence of a `cq:childEditConfig`.

* @prop cq:noDecoration   
  If true, no decoration `div` tags are drawn when including this component.

* @node cq:editConfig   
  The configuration that defines the parameters for the edit bar.
* @node cq:childEditConfig  
  The edit configuration that is inherited by child components.
* @node cq:htmlTag   
  Defines additional tag attributes that are added to the "surrounding" `div` tag when the component is included.

* @node icon.png   
  A file that holds a characteristic icon.
* @node thumbnail.png   
  A file that holds a characteristic thumbnail image.
* @prop allowedParents   
  Regular expression patterns to determine the path(s) of components that are allowed as parent components.
* @prop allowedChildren  
  Regular expression patterns to determine the path(s) of components that are allowed as child components.
* @node virtual   
  Contains subnodes that reflect virtual components used for the component drag and drop.
* @prop componentGroup  
  Name of the component group, used for the component drag and drop.
* @node cq:infoProviders   
  Contains subnodes, each of which has a property `className` that refers to a `PageInfoProvider`.

**Definition** [cq:Component] > nt:folder, mix:title, sling:ResourceSuperType - &#42; (undefined) - &#42; (undefined) multiple + &#42; (nt:base) = nt:base multiple version + dialog (nt:base) = nt:unstructured copy - dialogPath (string) + design_dialog (nt:base) = nt:unstructured copy - cq:cellName (string) - cq:isContainer (boolean) - cq:noDecoration (boolean) + cq:editConfig (cq:EditConfig) = cq:EditConfig copy + cq:childEditConfig (cq:EditConfig) = cq:EditConfig copy + cq:htmlTag (nt:base) = nt:unstructured copy + icon.png (nt:file) copy + thumbnail.png (nt:file) copy - allowedParents (string) multiple - allowedChildren (string) multiple + virtual (nt:base) = sling:Folder copy - componentGroup (string) + cq:infoProviders (nt:base) = nt:unstructured copy

### cq:ComponentMixin {#cq-componentmixin}

**Description** Defines a CQ Component as mixin type.

**Definition** [cq:ComponentMixin] > cq:Component mixin

### cq:EditConfig {#cq-editconfig}

**Description** Defines the configuration for the "editbar".

* @prop cq:dialogMode  
  Mode of the dialog:

    * `floating` - for a normal, floating dialog
    * `inline` - inline editing
    * `auto` - automatic detection (depending on available space)

* @node cq:inplaceEditing   
  Inplace editing configuration for this component.
* @prop cq:layout   
  Layout of the edit bar:

    * `editbar` - edit bar
    * `rollover` - roll over frame
    * `auto` - automatic detection

* @node cq:formParameters   
  Additional parameters to add to the dialog form.
* @prop cq:actions   
  List of actions (edit bar buttons, or menu items).
* @node cq:actionConfigs   
  Widget configurations for edit bar or menu items.
* @prop cq:emptyText   
  Text to be displayed if no visual content is present.
* @node cq:dropTargets   
  Collection of `{@link cq:DropTargetConfig}` nodes.

**Definition** [cq:EditConfig] > nt:unstructured, nt:hierarchyNode orderable - cq:dialogMode (string) < 'auto', 'floating', 'inline' - cq:layout (string) < 'editbar', 'rollover', 'auto' + cq:formParameters (nt:base) = nt:unstructured - cq:actions (string) multiple + cq:actionConfigs (nt:base) = nt:unstructured - cq:emptyText (string) + cq:dropTargets (nt:base) = nt:unstructured + cq:listeners (nt:base) = cq:EditListenersConfig

<!-- 

Comment Type: draft

<p><strong>For CQ5.4</strong></p> 
<p> after dialogMode:</p> 
<p> + cq:inplaceEditing (cq:InplaceEditingConfig) = cq:InplaceEditingConfig<br /> </p>

 -->

### cq:DropTargetConfig {#cq-droptargetconfig}

**Description** Configures one drop target of a component. The name of the this node will be used as an ID for drag and drop.

* @prop accept   
  List of mime types accepted by this drop target; e.g. `["image/*"]`

* @prop groups   
  List of drag and drop groups that accept a source.
* @prop propertyName   
  Name of the property used to store the reference.

**Definition** [cq:DropTargetConfig] > nt:unstructured orderable - accept (string) multiple - groups (string) multiple - propertyName (string) + parameters (nt:base) = nt:unstructured

<!-- 

Comment Type: draft

<h3>cq:InplaceEditingConfig</h3>

 -->

<!-- 

Comment Type: draft

<p><strong>For CQ 5.4</strong></p> 
<p><strong>Description</strong></p> 
<p></p> 
<p>Configures inplace editing of a component.</p> 
<ul> 
 <li>@prop active<br /> True to activate inplace editing for the component.</li> 
 <li>@prop editorType<br /> ID of the inplace editor to be used.</li> 
 <li>@prop configPath<br /> Path to the configuration of the editor (optional).</li> 
 <li>@node config<br /> Configuration of the editor (used if no configPath is specified; optional).<br /> </li> 
</ul> 
<p></p> 
<p><strong>Definition</strong></p> 
<p><span class="code">[cq:InplaceEditingConfig] &gt; nt:unstructured<br /> - active (boolean)<br /> - editorType (string)<br /> - configPath (string)<br /> + config (nt:unstructured) = nt:unstructured</span></p>

 -->

### cq:VirtualComponent {#cq-virtualcomponent}

**Description** Defines a virtual CQ component. These are currently used only for the new component drag and drop wizard.

* @prop jcr:title   
  Title of this component.
* @prop jcr:description   
  Description of this component.
* @node cq:editConfig   
  Edit configuration that defines the parameters for the edit bar.
* @node cq:childEditConfig   
  Edit configuration that is inherited by child components.
* @node icon.png  
  A file that holds a characteristic icon.
* @node thumbnail.png   
  A file that holds a characteristic thumbnail image.
* @prop allowedParents   
  Regular expression patterns to determine path(s) of components that are allowed as parent components.
* @prop allowedChildren  
  Regular expression patterns to determine path(s) of components that are allowed as child components.
* @prop componentGroup   
  Name of the component group for the component drag and drop.

**Definition** [cq:VirtualComponent] > nt:folder, mix:title - &#42; (undefined) - &#42; (undefined) multiple + &#42; (nt:base) = nt:base multiple version + cq:editConfig (cq:EditConfig) = cq:EditConfig copy + icon.png (nt:file) copy + thumbnail.png (nt:file) copy - allowedParents (string) multiple - allowedChildren (string) multiple - componentGroup (string)

### cq:EditListenersConfig {#cq-editlistenersconfig}

**Description** Defines the (client side) listeners to be executed on an edit event. The values must either reference a valid client side listener function or contain a predefined shortcut:

* REFRESH_PAGE
* REFRESH_SELF
* REFRESH_PARENT

* @prop aftercreate   
  Fires after a component has been created.
* @prop afteredit   
  Fires after a component has been edited (modified).
* @prop afterdelete   
  Fires after a component has been deleted.
* @prop afterinsert   
  Fires after a component has been added to this container.
* @prop afterremove   
  Fires after a component has been removed from this container.
* @prop aftermove   
  Fires after components have been moved in this container.

**Definition** [cq:EditListenersConfig] - &#42; (undefined) - &#42; (undefined) multiple + &#42; (nt:base) = nt:base multiple version - aftercreate (string) - afteredit (string) - afterdelete (string) - afterinsert (string) - afterremove (string) - aftermove (string)

## DAM {#dam}

### dam:AssetContent {#dam-assetcontent}

**Description** Content of a DAM asset.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:22.647-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [dam:AssetContent] > nt:unstructured + metadata (nt:unstructured) + renditions (nt:folder)

### dam:Asset {#dam-asset}

**Description** DAM asset.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:22.743-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [dam:Asset] > nt:hierarchyNode + jcr:content (dam:AssetContent) = dam:AssetContent copy primary + &#42; (nt:base) = nt:base version

### dam:Thumbnail {#dam-thumbnail}

**Description** Thumbnail to represent a DAM asset.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:22.835-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [dam:Thumbnails] mixin + dam:thumbnails (nt:folder)

## Delivery Container List {#delivery-container-list}

### cq:containerList {#cq-containerlist}

**Description** Container List.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:22.958-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:containerList] mixin

## Delivery Page {#delivery-page}

### cq:Cq4PageAttributes {#cq-cq-pageattributes}

**Description** cq:attributes is the node type for the ContentBus version tags. This node only has a series of properties; of which three are predefined "created", "csd", and "timestampe".

* @prop created (long) mandatory copy  
  Timestamp of creation of the version information, generally the time of checkin of the previous version or time of page creation.
* @prop csd (string) mandatory copy  
  csd standard attribute, copy of the cq:csd property of the page node
* @prop timestampe (long) mandatory copy  
  Timestamp of last version modification, generally checkin time.
* @prop &#42; (string) copy  
  Additional attributes, versioned with the parent node.

**Definition** [cq:Cq4PageAttributes] > nt:base - created (long) mandatory copy - csd (string) mandatory copy - timestampe (long) mandatory copy - &#42; (string) copy

### cq:Cq4ContentPage {#cq-cq-contentpage}

**Description** The node type cq:contentPage contains the property and child node definitions for ContentBus content pages. Only when this mixin type is added to a node of type "cq:page", a node becomes a ContentBus content page.

The items in a "cq:Cq4ContentPage" are:

* @prop cq:csd  
  The ContentBus CSD of the page.
* @node cq:content  
  The content of the page. This child node does not exist if the page node is in state "Existing without content" or "Deleted".
* @node cq:attributes  
  The list of page attributes, which were formerly known as version tags. This node is mandatory for the cq:contentPage type. The attrbutes node is versioned, when the page is node is versioned.

**Definition** [cq:Cq4ContentPage] - cq:csd (string) mandatory copy + cq:attributes (cq:Cq4PageAttributes)

## Importer {#importer}

### cq:PollConfig {#cq-pollconfig}

**Description** Poll configuration.

* @prop source (String) mandatory  
  Data source URI, this is required and must not be empty
* @prop target (String)  
  The target location where data retrieved from the data source is stored. This is optional and defaults to the cq:PollConfig node.
* @prop interval (Long)  
  The interval in seconds at which to poll for new or updated data from the data source. This is optional and defaults to 30 Minutes (1800 seconds).  

* [Creating Custom Data Importer Services for Adobe Experience Manager](/content/help/en/experience-manager/using/polling)

**Definition** [cq:PollConfig] mixin - source (String) mandatory - target (String) - interval (Long)

### cq:PollConfigFolder {#cq-pollconfigfolder}

**Description** Convenience primary node type to easily create poll configuration nodes.

**Definition** [cq:PollConfigFolder] > sling:Folder, cq:PollConfig

## Location {#location}

### cq:GeoLocation {#cq-geolocation-1}

**Description** A mixin that defines a geographic location in decimal degrees (DD).

* @prop latitude   
  Latitude encoded as double using decimal degrees.
* @prop longitude   
  Longitude encoded as double using decimal degrees.

**Definition** [cq:GeoLocation] mixin - latitude (double) - longitude (double)

## Mailer {#mailer}

### cq:mailerMessage {#cq-mailermessage}

**Description** MailerService nodetypes. The mailer uses nodes having this mixin as root nodes of message definitions.

**Definition** [cq:mailerMessage] mixin - messageStatus (string) = 'new' mandatory autocreated

## MSM {#msm}

### cq:LiveRelationship {#cq-liverelationship}

**Description** Defines a LiveRelationship mixin. A master node and a slave node can be virtually linked through a LiveRelationship.

**Definition** [cq:LiveRelationship] mixin - cq:lastRolledout (date) - cq:lastRolledoutBy (string) - cq:sourceUUID (string)

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:23.597-0500

<p>remove sourceUUID for CQ 5.4<br /> </p>

 -->

### cq:LiveSync {#cq-livesync}

**Description** Defines a LiveSync mixin. If a node is involved in a LiveRelationship with a master node as a slave, it is marked a LiveSync.

* @prop cq:master   
  Path of the master node of the LiveRelationship.
* @prop cq:isDeep   
  Defines if the relationship is available for children.
* @prop cq:syncTrigger   
  Defines when is triggered the sync.
* @node &#42; LiveSyncAction   
  Actions to perform on sync

**Definition** [cq:LiveSync] > cq:LiveRelationship mixin orderable + &#42; (cq:LiveSyncAction) = cq:LiveSyncAction + cq:LiveSyncConfig (nt:base) = cq:LiveSyncConfig

### cq:LiveSyncCancelled {#cq-livesynccancelled}

**Description** Defines a LiveSyncCancelled mixin. Cancel the LiveSync behavior of a slave node which may be involded in a LiveRelationship owing to one of its parents.

* @prop cq:isCancelledForChildren   
  Defines whether a LiveSync is cancelled; also for children.

**Definition** [cq:LiveSyncCancelled] > cq:LiveRelationship mixin - cq:isCancelledForChildren (boolean)

### cq:LiveSyncAction {#cq-livesyncaction}

**Description** Defines a LiveSyncAction attached to a LiveSync.

* @prop name   
  Action name.
* @prop value   
  Action value.

**Definition** [cq:LiveSyncAction] > nt:unstructured

### cq:LiveSyncConfig {#cq-livesyncconfig}

**Description** Live Sync configuration.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:24.024-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:LiveSyncConfig] - cq:master (string) mandatory - cq:isDeep (boolean) - cq:trigger (string) /&#42;&#42; deprecated &#42;&#42;/

For CQ 5.4 add to the end of list:

`- cq:rolloutConfigs (string) multiple deprecated **/`

### cq:BlueprintAction {#cq-blueprintaction}

**Description** Blueprint action.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:24.135-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:BlueprintAction] > nt:unstructured

<!-- 

Comment Type: draft

<h3>cq:BlueprintSyncConfig</h3>

 -->

<!-- 

Comment Type: draft

<p><strong>FOR CQ 5.4</strong></p> 
<p><strong>Description</strong></p> 
<p></p> 
<p>Blueprint Sync configuration.<br /> </p> 
<p></p> 
<p></p> 
<p><strong>Remark</strong> by Alison Heimoz (aheimoz) on Fri, 8 Oct 2010, 00:29:38 EDT<br /> </p> 
<p>Need definition from RnD.<br /> </p> 
<p></p> 
<p></p> 
<p><strong>Definition</strong></p> 
<p></p> 
<p>[cq:BlueprintSyncConfig] &gt; nt:unstructured<br /> - cq:rolloutConfigs (string) multiple</p> 
<p></p>

 -->

## Platform {#platform}

### cq:Console {#cq-console}

**Description** Defines the nodetype of a console node.

**Definition** [cq:Console] > sling:VanityPath, mix:title mixin

## Replication {#replication}

### cq:ReplicationStatus {#cq-replicationstatus}

**Description** Defines replication status information mixin.

* @prop cq:lastPublished   
  The date the page was last published (not used anymore).
* @prop cq:lastPublishedBy   
  The user who published the page last (not used anymore).
* @prop cq:lastReplicated   
  The date the page was last replicated.
* @prop cq:lastReplicatedBy   
  The user that replicated the page last.
* @prop cq:lastReplicationAction   
  The replication action: activate or deactivate.
* @prop cq:lastReplicationStatus   
  The replication status (not used anymore).

**Definition** [cq:ReplicationStatus] mixin - cq:lastPublished (date) ignore - cq:lastPublishedBy (string) ignore - cq:lastReplicated (date) ignore - cq:lastReplicatedBy (string) ignore - cq:lastReplicationAction (string) ignore - cq:lastReplicationStatus (string) ignore

## Security {#security}

### cq:ApplicationPrivilege {#cq-applicationprivilege}

**Description** Defines an application privilege.

**Definition** [cq:ApplicationPrivilege] mixin

### cq:PrivilegeAcl {#cq-privilegeacl}

**Description** Defines an application privilege ACL.

* @prop cq:isPathDependent
* @node &#42; ACEs

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:24.599-0500

<p>Need more detailed definition from RnD.<br /> </p>

 -->

**Definition** [cq:PrivilegeAcl] > cq:ApplicationPrivilege mixin orderable - cq:isPathDependent (boolean) + &#42; (cq:PrivilegeAce) = cq:PrivilegeAce

### cq:PrivilegeAce {#cq-privilegeace}

**Description** Defines an application privilege ACE.

* @prop path
* @prop deny

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:24.689-0500

<p>Need more detailed definition from RnD.<br /> </p>

 -->

**Definition** [cq:PrivilegeAce] - path mandatory - deny (boolean)

### cq:ApplicationPrivilege {#cq-applicationprivilege-1}

**Description** Defines an application privilege.

**Definition** [cq:ApplicationPrivilege] mixin

### cq:PrivilegeAcl {#cq-privilegeacl-1}

**Description** Defines an application privilege ACL.

* @prop cq:isPathDependent
* @node &#42; ACEs

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:24.862-0500

<p>Need more detailed definition from RnD.<br /> </p>

 -->

**Definition** [cq:PrivilegeAcl] > cq:ApplicationPrivilege mixin orderable - cq:isPathDependent (boolean) + &#42; (cq:PrivilegeAce) = cq:PrivilegeAce

### cq:PrivilegeAce {#cq-privilegeace-1}

**Description** Defines an application privilege ACE.

* @prop path
* @prop deny

**Definition** [cq:PrivilegeAce] - path mandatory - deny (boolean)

## Site Importer {#site-importer}

### cq:ComponentExtractorSource {#cq-componentextractorsource}

**Description** Defines a mixin type that marks files that can be opened with component extractor.

**Definition** [cq:ComponentExtractorSource] mixin

## Tagging {#tagging}

### cq:Tag {#cq-tag}

**Description** Defines a single tag, but can also contain tags, thus creating a taxonomy

**Definition** [cq:Tag] > nt:base, mix:title - sling:resourceType (String) - &#42; (undefined) multiple - &#42; (undefined) + &#42; (nt:base) = cq:Tag version

### cq:Taggable {#cq-taggable}

**Description** Abstract base mixin for taggable content.

* @node cq:tags

**Definition** [cq:Taggable] - cq:tags (string) multiple

### cq:OwnerTaggable {#cq-ownertaggable}

**Description** Only authors/owners are allowed to tag the content (moderated/administered tagging).

**Definition** [cq:OwnerTaggable] > cq:Taggable

### cq:UserTaggable (ToDo) {#cq-usertaggable-todo}

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:25.480-0500

<p>is this active or todo for 5.3?<br /> </p>

 -->

**Description** Any user/public website can tag the content (Web2.0 style), used inside cq:userContent.

**Definition** [cq:UserTaggable] > cq:Taggable mixin

### cq:AllowsUserContent {#cq-allowsusercontent}

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:25.586-0500

<p>is this active or todo for 5.3?<br /> </p>

 -->

**Description** Adds a cq:userContent subnode that can be modified by users; each user will have their own cq:userContent/<userid> subnode, that typically has the mixin cq:UserTaggable.

**Definition** [cq:AllowsUserContent] mixin + cq:userContent (nt:unstructured)

`TODO: extended variant, more explicitly defining the cq:userContent tree`

`[cq:AllowsUserContent]  
mixin  
+ cq:userContent (cq:UserContent)`

`` ``

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:25.655-0500

<p>ToDo by when? Leave in or remove from here.<br /> </p>

 -->

### cq:UserContent {#cq-usercontent}

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:25.700-0500

<p>is this active or todo for 5.3?<br /> </p>

 -->

**Description** Can be modified by users.

**Definition** [cq:UserContent] > nt:unstructured // userids + &#42; (cq:UserData) // other content + &#42; (nt:base)

### cq:UserData {#cq-userdata}

**Description** User data.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:25.818-0500

<p>is this active or todo for 5.3?<br /> </p>

 -->

**Definition** [cq:UserData] > nt:unstructured, cq:UserTaggable

## Widgets {#widgets}

### cq:ClientLibraryFolder {#cq-clientlibraryfolder}

**Description** Client library folder.

**Definition** [cq:ClientLibraryFolder] > sling:Folder - categories (string) multiple - dependencies (string) multiple

### cq:Widget {#cq-widget}

**Description** Widget.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.003-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:Widget] > nt:unstructured orderable - xtype (string) - name (string) - title (string) + items (nt:base) = cq:WidgetCollection copy

### cq:WidgetCollection {#cq-widgetcollection}

**Description** Widget collection.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.095-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:WidgetCollection] > nt:unstructured orderable + &#42; (cq:Widget) = cq:Widget copy

### cq:Dialog {#cq-dialog}

**Description** Dialog.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.187-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:Dialog] > cq:Widget orderable

### cq:Panel {#cq-panel}

**Description** Panel.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.297-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:Panel] > cq:Widget orderable

### cq:TabPanel {#cq-tabpanel}

**Description** Tab panel.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.407-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:TabPanel] > cq:Panel orderable - activeTab (long)

### cq:Field {#cq-field}

**Description** Field.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.554-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:Field] > cq:Widget orderable - fieldLabel (string) - value (string) - ignoreData (boolean)

## Wiki {#wiki}

### wiki:Topic {#wiki-topic}

**Description** Wiki topic.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.694-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [wiki:Topic] > nt:unstructured, nt:hierarchyNode, mix:versionable, mix:lockable + &#42; (wiki:Topic) version + wiki:attachments (nt:folder) = nt:folder version + wiki:properties (wiki:Properties) = wiki:Properties copy - wiki:text (string) mandatory primary - wiki:lastModified (date) mandatory - wiki:lastModifiedBy (string) mandatory - wiki:topicName - wiki:topicTitle - wiki:lockedBy - wiki:logMessage (string) - wiki:quietSave (boolean)

### wiki:User {#wiki-user}

**Description** Wiki user.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.799-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [wiki:User] mixin - wiki:subscriptions (string) multiple

### wiki:Properties {#wiki-properties}

**Description** Wiki properties.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:26.910-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [wiki:Properties] - wiki:isGlobal (boolean) - &#42; (undefined)

## Workflow {#workflow}

### cq:Workflow {#cq-workflow}

**Description** Represents a workflow instance.

**Definition** [cq:Workflow] > nt:base, mix:referenceable - modelId (String) - modelVersion (String) - startTime (Date) - endTime (Date) - initiator (String) - &#42; (undefined) - &#42; (undefined) multiple - sling:resourceType (String) = "cq/workflow/components/instance" mandatory autocreated + workflowStack (nt:unstructured) + wait (nt:unstructured) + orTab (nt:unstructured) + data (cq:WorkflowData) + history (nt:unstructured) + metaData (nt:unstructured) + workItems (nt:unstructured)

### cq:WorkItem {#cq-workitem}

**Description** Work item.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.174-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:WorkItem] - assignee (String) - workflowId (String) - nodeId (String) - startTime (Date) - endTime (Date) - dueTime (Date) - sling:resourceType (String) = "cq/workflow/components/workitem" mandatory autocreated + metaData (nt:unstructured)

### cq:Payload {#cq-payload}

**Description** Payload.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.278-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:Payload] - path (Path) - uuid (String) - jcr:url (String) - binary (Binary) - javaObject (String) - &#42; (undefined) - &#42; (undefined) multiple

### cq:WorkflowData {#cq-workflowdata}

**Description** Workflow data.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.377-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:WorkflowData] - &#42; (undefined) - &#42; (undefined) multiple + payload (cq:Payload) + metaData (nt:unstructured) copy

### cq:WorkflowModel {#cq-workflowmodel}

**Description** Auto assign workflow configuration. The configuration will follow this structure below: workflows + name1 - cq:path - cq:workflowName + workflows (nt:base)

**Definition** [cq:WorkflowModel] > nt:base, mix:versionable orderable - title (String) - description (String) - sling:resourceType (String) = "cq/workflow/components/model" mandatory autocreated + nodes (nt:unstructured) copy + transitions (nt:unstructured) copy + metaData (nt:unstructured) copy

### cq:WorkflowNode {#cq-workflownode}

**Description** Workflow node.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.564-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:WorkflowNode] orderable - title (String) - description (String) - maxIdleTime (long) - type (String) - &#42; (undefined) - &#42; (undefined) multiple + metaData (nt:unstructured) copy + timeoutConfiguration (nt:unstructured) copy

### cq:WorkflowTransition {#cq-workflowtransition}

**Description** Workflow transition.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.654-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:WorkflowTransition] orderable - from (String) - to (String) - rule (String) + metaData (nt:unstructured) copy

### cq:OrTab {#cq-ortab}

**Description** Or tab.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.745-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:OrTab] - workflowId (String) // not compulsory as this node will already be attached to the workflow node - nodeId (String)

### cq:Wait {#cq-wait}

**Description** Wait.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.835-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:Wait] - workflowId (String) // not compulsory as this node will be already attached to the workflow node - destNodeId (String) - fromNodeId (String)

### cq:WorkflowStack {#cq-workflowstack}

**Description** Workflow stack.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:27.926-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:WorkflowStack] - containeeInstanceId (String) - parentInstanceId (String) - nodeId (String)

### cq:ProcessStack {#cq-processstack}

**Description** Process stack.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:28.015-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:ProcessStack] - workflowId (String) // not compulsory as this node will be already attached to the workflow node - containerWorkflowModelId (String) - containerWorkflowNodeId - containerWorkflowEndNodeId // still needed (if name already defines that id)

### cq:WorkflowLauncher {#cq-workflowlauncher}

**Description** Workflow launcher.

<!-- 

Comment Type: remark
Last Modified By: (aheimoz)
Last Modified Date: 2018-01-18T11:19:28.107-0500

<p>Need definition from RnD.<br /> </p>

 -->

**Definition** [cq:WorkflowLauncher] - nodetype (String) - glob (String) - eventType (Long) - description (String) - condition (String) - workflow (String) - &#42; (undefined) - &#42; (undefined) multiple
