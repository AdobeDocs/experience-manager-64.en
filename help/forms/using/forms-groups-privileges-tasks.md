---
title: AEM Forms on OSGi Groups and Privileges
seo-title: AEM Forms on OSGi Groups and Privileges
description: Assign users to the groups to manage AEM Forms on OSGi
seo-description: Assign users to the groups to manage AEM Forms on OSGi
uuid: 7f063de5-0230-4577-b023-52d56fe925d0
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: Configuration
discoiquuid: 8226f46e-a7ca-43f7-8436-492e4f7403b0
index: y
internal: n
snippet: y
---

# AEM Forms on OSGi Groups and Privileges{#aem-forms-on-osgi-groups-and-privileges}

Assign users to the groups to manage AEM Forms on OSGi

You can [create groups](../../sites/administering/using/user-group-ac-admin.md#groupadministration) and assign policies and [users](../../sites/administering/using/user-group-ac-admin.md#useradministration) to the groups in AEM. These policies control privileges of the users that are part of the group.

Once you install [AEM Forms add-on package](../../forms/using/installing-configuring-aem-forms-osgi.md), the groups mentioned in this article, such as forms-user and forms-power-user, are automatically available for assignment. The following table lists the tasks a user can perform for AEM Forms on OSGi based on the group assignments:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Group</td> 
   <td>Tasks</td> 
  </tr>
  <tr>
   <td>forms-user <sup><a href="#main-pars-text">[1]</a></sup></td> 
   <td>
    <ul> 
     <li>Create, preview, publish, and submit adaptive forms</li> 
     <li>Create, preview, and publish interactive communications and document fragments</li> 
     <li>Upload assets to an AEM instance</li> 
     <li>Create themes</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>forms-power-user</td> 
   <td>
    <ul> 
     <li>Create, preview, publish, and submit adaptive forms</li> 
     <li>Create, preview, and publish interactive communications and document fragments</li> 
     <li>Create scripts for adaptive forms using code editor</li> 
     <li>Upload assets including scripts</li> 
     <li>Create themes</li> 
     <li>Import packages containing XDP</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>forms-submission-reviewers</td> 
   <td>
    <ul> 
     <li>Review submissions</li> 
     <li>Approve or reject submissions</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>template-authors <sup><a href="#main-pars-text">[2]</a></sup></td> 
   <td>
    <ul> 
     <li>Create and preview adaptive forms or interactive communications templates</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>template-power-user</td> 
   <td>
    <ul> 
     <li>Create and preview adaptive forms or interactive communications templates</li> 
     <li>Create scripts for adaptive forms or interactive communications templates using code editor</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><p>fdm-authors</p> </td> 
   <td>
    <ul> 
     <li>Create and modify a form data model</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>cm-user-agent</td> 
   <td>
    <ul> 
     <li>Access Correspondence Management letters or interactive communications using Agent UI</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><p>workflow-editors</p> </td> 
   <td>
    <ul> 
     <li>Create an inbox application</li> 
     <li>Create a workflow model</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>workflow-user</td> 
   <td>
    <ul> 
     <li>Use AEM inbox applications</li> 
     <li>Manage workflow instances</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td>fd-administrators</td> 
   <td>
    <ul> 
     <li>Configure PDF Generator</li> 
     <li>Configure Watched folder</li> 
     <li>Manage workflow applications</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

1. The user with forms-user group privileges cannot write scripts for adaptive forms.
1. The user with template-authors group privileges cannot write scripts for templates.

