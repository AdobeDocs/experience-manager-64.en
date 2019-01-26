---
title: Customizing the Welcome Console (Classic UI)
seo-title: Customizing the Welcome Console (Classic UI)
description: null
seo-description: The Welcome console provides a list of links to the various consoles and functionality within AEM
uuid: 82706d0d-aeb8-4dd4-838c-9406ad8671ea
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 45f35885-3086-4582-95a4-774eaabdb523
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Customizing the Welcome Console (Classic UI){#customizing-the-welcome-console-classic-ui}

>[!CAUTION]
>
>This page deals with the classic UI.
>
>See [Customizing the Consoles](../../developing/using/customizing-consoles-touch.md) for details on the standard, touch-enabled UI.

The Welcome console provides a list of links to the various consoles and functionality within AEM.

![](assets/cq_welcomescreen.png)

It is possible to configure the links that are visible. This can be defined for specific users and/or groups. The actions to be taken are dependent on the target type (which correlates to the section of the console they are in):

* [Main Consoles](#linksinmainconsoleleftpane) - Links in the main console (left pane)
* [Resources, Documentation and Reference, Features](#linksinsidebarrightpane) - Links in the sidebar (right pane)

<!--
Comment Type: remark
Last Modified By: Alison Heimoz (aheimoz)
Last Modified Date: 2018-01-18T11:19:19.766-0500
<p>please check: </p>
<p>have removed the following for the moment. </p>
<p style="margin-left: 40px;">"With this configuration it is not only the links that are impacted, access to the functionality being linked to is also restricted for those users. For example, if you disable the link to the Tools console for a specific group, then access to the Tools icon available at the top of the other consoles (Websites, Users, etc ) will also be impacted. Direct access to the console via the URL will also be restricted, again for that group."</p>
<p>It only seems to apply to the consoles. Have just tested it with Packages and the functionality is still available via the Tools console.</p>
<p>Surely we need to document how to disable the underlying functionality? Or at least make them aware of the issues? </p>
<p>Need to check how to completely disable the various items in the sidebar.</p>
-->

### Links in Main Console (Left Pane) {#links-in-main-console-left-pane}

This lists the main consoles of AEM.

![](assets/cq_welcomescreenmainconsole.png) 

#### Configuring whether Main Console Links are Visible {#configuring-whether-main-console-links-are-visible}

Node level permissions determine whether the link can be seen or not. The nodes in question are:

* **Websites** 
  `/libs/wcm/core/content/siteadmin`

* **Digital Assets** 
  `/libs/wcm/core/content/damadmin`

* **Community** 
  `/libs/collab/core/content/admin`

* **Campaigns** 
  `/libs/mcm/content/admin`

* **Inbox** 
  `/libs/cq/workflow/content/inbox`

* **Users** 
  `/libs/cq/security/content/admin`

* **Tools** 
  `/libs/wcm/core/content/misc`

* **Tagging** 
  `/libs/cq/tagging/content/tagadmin`

For example:

* To restrict access to **Tools**, remove read access from  
  `` `/libs/wcm/core/content/misc`

See the [Security section](../../administering/using/security.md) for more information on how to set the desired permissions.

### Links in Sidebar (Right Pane) {#links-in-sidebar-right-pane}

![](assets/cq_welcomescreensidebar.png)

These links are based on the existence of *and* read access to nodes under the following path:

`/libs/cq/core/content/welcome`

There are three sections (spaced slightly apart) provided by default:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td width="150"><strong>Resources</strong></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td width="150"> Cloud Services</td> 
   <td><span class="code">/libs/cq/core/content/welcome/resources/cloudservices</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Workflows</td> 
   <td><span class="code">/libs/cq/core/content/welcome/resources/workflows</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Task Management</td> 
   <td><span class="code">/libs/cq/core/content/welcome/resources/taskmanager</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Replication</td> 
   <td><span class="code">/libs/cq/core/content/welcome/resources/replication</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Reports</td> 
   <td><span class="code">/libs/cq/core/content/welcome/resources/reports</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Publications</td> 
   <td><span class="code">/libs/cq/core/content/welcome/resources/publishingadmin</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Manuscripts</td> 
   <td><span class="code">/libs/cq/core/content/welcome/resources/manuscriptsadmin</span></td> 
  </tr> 
  <tr> 
   <td width="150"><strong>Documentation and Reference</strong></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td width="150"> Documentation</td> 
   <td><span class="code">/libs/cq/core/content/welcome/docs/docs</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Developer Resources</td> 
   <td><span class="code">/libs/cq/core/content/welcome/docs/dev</span></td> 
  </tr> 
  <tr> 
   <td width="150"><strong>Features</strong></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td width="150"> CRXDE Lite</td> 
   <td><span class="code">/libs/cq/core/content/welcome/features/crxde</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Packages</td> 
   <td><span class="code">/libs/cq/core/content/welcome/features/packages</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Package Share</td> 
   <td><span class="code">/libs/cq/core/content/welcome/features/share</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Clustering</td> 
   <td><span class="code">/libs/cq/core/content/welcome/features/cluster</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Backup</td> 
   <td><span class="code">/libs/cq/core/content/welcome/features/backup</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Web Console<br /> </td> 
   <td><span class="code">/libs/cq/core/content/welcome/features/config</span></td> 
  </tr> 
  <tr> 
   <td width="150"> Web Console Status Dump<br /> </td> 
   <td><span class="code">/libs/cq/core/content/welcome/features/statusdump</span></td> 
  </tr> 
 </tbody> 
</table>

#### Configuring whether Sidebar Links are Visible {#configuring-whether-sidebar-links-are-visible}

It is possible to hide a link from specific users or groups by removing read access to the nodes that represent the link.

* Resources - remove access to:  
  `/libs/cq/core/content/welcome/resources/<*link-target*>`

* Docs - remove access to:  
  `/libs/cq/core/content/welcome/docs/<*link-target*>`

* Features - remove access to:  
  `/libs/cq/core/content/welcome/features/<*link-target*>`

For example:

* To remove the link to **Reports**, remove read access from  
  `/libs/cq/core/content/welcome/resources/reports`  

* To remove the link to **Packages**, remove read access from  
  `/libs/cq/core/content/welcome/features/packages`

See the [Security section](../../administering/using/security.md) for more information on how to set the desired permissions.

### Link Selection Mechanism {#link-selection-mechanism}

In `/libs/cq/core/components/welcome/welcome.jsp` use is made of [ConsoleUtil](/developing/using/reference-materials/javadoc/com/day/cq/commons/ConsoleUtil), which executes a query on nodes that have the property:

* `jcr:mixinTypes` with the value: `cq:Console`

>[!NOTE]
>
>Execute the following query to see the existing list:
>
>* `select * from cq:Console`
>

When a user or group does not have read permission on a node with the mixin `cq:Console`, that node is not retrieved by the `ConsoleUtil` search, hence it is not listed on the console.

### Adding a Custom Item {#adding-a-custom-item}

The [link selection mechanism](#linkselectionmechanism) can be used to add your own custom item to the list of links.

Add your custom item to the list by adding the `cq:Console` mixin to your widget or resource. This is done by defining the property:

* `jcr:mixinTypes` with the value: `cq:Console`

