---
title: Security Changes in CQ 5.3 and CRX 2.0
seo-title: Security Changes in CQ 5.3 and CRX 2.0
description: Changes have been made to the security model between CRX 1.4.x and CRX 2.0 - and therefore between AEM 5.2 and AEM 5.3
seo-description: Changes have been made to the security model between CRX 1.4.x and CRX 2.0 - and therefore between AEM 5.2 and AEM 5.3
page-status-flag: de-activated
uuid: 375ac01a-ed2c-4eae-a737-8c6d93e04f0b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 247e24d1-3ad5-467d-bbaf-06a93082ec63
---

# Security Changes in CQ 5.3 and CRX 2.0{#security-changes-in-cq-and-crx}

Changes have been made to the security model between CRX 1.4.x and CRX 2.0 - and therefore between CQ 5.2 and CQ 5.3. The upgrade procedure compensates for most of these changes and so for most installations, no further action is necessary.

However, some changes could not be covered by the upgrade procedure but may affect  
some existing installations. This list is provided to cover such changes:

>[!NOTE]
>
>This page describes security concepts in a very detailed manner and requires a good understanding of the security model of CQ5 versions prior to 5.3 and CRX versions prior to 2.0, knowledge of the new JCR 2.0 standard in the area of Access Control Management, knowledge about the new security/ACL/user management APIs in Jackrabbit 2.0 and last but not least some general developer knowledge.
>
>It is intended as a supporting resource in the case of questions related to an upgrade to CQ 5.3 / CRX 2.0 in the area of Security.

## Access Control Evaluation {#access-control-evaluation}

The Access Control Evaluation (ACE) changed from CRX 1.4.x to CRX 2.0. The major changes are as follows:

CRX 1.4.x

* ACEs are strictly evaluated based on their order in the Access Control List (ACL).
* Local ACEs take precedence over hierarchically distant ACEs.
* When editing in the GUI, ACEs for users are inserted in the ACL so that they take precedence over ACEs for group principals. This can be changed be reordering ACEs.
* Redundant ACEs can be created and are not cleared from the Access Control implementation. The evaluation order decides on the final result. The clean up is executed by the UI helper classes.

CRX 2.0

* ACEs for user principals always take precedence over group principal ACEs, irrespective of:

    * their order in the ACL   
    * their position in the node hierarchy

* For a given principal there exists at most 1 deny and 1 allow entry at a given node. The implementation always clears redundant entries and makes sure that the same privilege is not listed in the allow and in the deny.

For example:

User `aUser` who is member of the group `aGroup`:

```xml
   + parentNode
     + acl
       + ace: aUser - deny - write
     + childNode
       + acl
         + ace: aGroup - allow - write
       + grandChildNode

```

In the previous case:

* CRX 1.4:

    * `aUser` is granted write permission on `grandChildNode.`

* CRX 2.0:

    * `aUser` is not granted write permission on `grandChildNode`.

```xml
   + parentNode
     + acl
       + ace: aUser - deny - write
     + childNode
       + acl
         + ace: aGroup - allow - write
         + ace: aUser - deny -write
       + grandChildNode
```

In this case:

* CRX 1.4:

    * write permission for `aUser` on `grandChildNode` depends on the order of ACEs on `childNode`.

* CRX 2.0:

    * `aUser` is not granted write permission on `grandChildNode`.  
    
    * The second ACE for `aUser` is redundant.

### Mapping of Former CRX ActionSet to New JCR Privileges {#mapping-of-former-crx-actionset-to-new-jcr-privileges}

The current mappings are defined in `CqActions` code module and were selected as the closest match to the previous mappings:

<table border="1" cellpadding="1" cellspacing="0" width="400"> 
 <tbody> 
  <tr> 
   <td><strong>ActionSet</strong></td> 
   <td><strong>JCR Privilege(s)</strong></td> 
   <td><strong>Match</strong></td> 
   <td><strong>Comment</strong></td> 
  </tr> 
  <tr> 
   <td>read</td> 
   <td>JCR_READ</td> 
   <td>+</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>set_property</td> 
   <td>JCR_MODIFY_PROPERTIES<br /> JCR_LOCK_MANAGEMENT<br /> JCR_VERSION_MANAGEMENT</td> 
   <td>+-</td> 
   <td><a href="#1">[1]</a></td> 
  </tr> 
  <tr> 
   <td>add_node</td> 
   <td>JCR_ADD_CHILD_NODES<br /> JCR_NODE_TYPE_MANAGEMENT</td> 
   <td>+</td> 
   <td><a href="#2">[2]</a></td> 
  </tr> 
  <tr> 
   <td>remove</td> 
   <td>JCR_REMOVE_CHILD_NODES<br /> JCR_REMOVE_NODE</td> 
   <td>+-</td> 
   <td><a href="#3">[3]</a></td> 
  </tr> 
  <tr> 
   <td>acl_read</td> 
   <td>JCR_READ_ACCESS_CONTROL</td> 
   <td>+</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>acl_edit</td> 
   <td>JCR_MODIFY_ACCESS_CONTROL</td> 
   <td>+</td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>-<br /> -</td> 
   <td>JCR_LIFECYCLE_MANAGEMENT<br /> JCR_RETENTION_MANAGEMENT</td> 
   <td>-<br /> -</td> 
   <td><a href="#4">[4]<br /> [4]</a></td> 
  </tr> 
  <tr> 
   <td>sudo</td> 
   <td>-</td> 
   <td>-</td> 
   <td><a href="#5">[5]</a></td> 
  </tr> 
  <tr> 
   <td>workspaceAccess</td> 
   <td>-</td> 
   <td>-</td> 
   <td><a href="#6">[6]</a></td> 
  </tr> 
 </tbody> 
</table>

The following table shows the mapping of CQActions versus CRX 1.4 ActionSet. The mapping between CQActions and the CRX 1.4 ActionSet was 1:1 and formerly defined in `AclRecord.js`.

| **CQAction** |**CRX ActionSet** |
|---|---|
| read |read |
| modify |set_property |
| create |add_node |
| delete |remove |
| acl_read |acl_read |
| acl_edit |acl_edit |

**[1]** The set_property ActionSet matches to JCR_MODIFY_PROPERTIES.

With CRX 2.0, protected items are no longer checked with the regular permission-check but need to be covered with special privileges that determine whether a given operation that modifies protected items can be executed.

To produce the same effect before, JCR_LOCK_MANAGEMENT and JCR_VERSION_MANAGEMENT (both writing protected properties) are automatically granted in CQ if a user is granted modify properties.

The JCR_MODIFY_PROPERTIES not only covers the creation of new properties and modification of existing ones but also of property removal. see [[3]](#3).

**Note:** If a user is granted JCR_MODIFY_PROPERTIES, but not the other two privileges, the "Modify" action in the CQ page permission flag displays **false** even if the user is allowed to add/set/remove regular JCR properties.

**[2]** The add_node ActionSet matches to JCR_ADD_CHILD_NODES.

Because JCR_NODE_TYPE_MANAGEMENT is necessary to be able to write the protected properties jcr:primaryType and jcr:mixinTypes, the latter is included in the mapping to grant both permissions to call Node.addNode(String) and Node.addNode(String, String).

In CRX 1.4, **create** not only included the right to add child nodes, but also entitled the user to write properties as long as the new node was not persisted. In CRX 2.0, this is no longer the case. The privilege to write non-protected properties is covered by JCR_MODIFY_PROPERTIES only.

**[3]** The CRX 1.4 remove ActionSet removed the node in the ACE where the ActionSet was located and all child nodes and their properties. To remove a node in CRX 2.0, the editing session must have JCR_REMOVE_CHILD_NODES on the parent node and on the node that is being removed JCR_REMOVE_NODE. Removing properties is governed by the JCR_MODIFY_PROPERTIES privilege.

The **remove** ActionSet defined by CRX and its corresponding ActionSet in CQ is mapped to both JCR privileges JCR_REMOVE_CHILD_NODES and JCR_REMOVE_NODE.

This slightly changes the result:

* The target node where the two privileges are granted cannot be removed anymore.
* Child nodes of the target can be removed (same as before).
* Properties present with the target and its child nodes cannot be removed unless JCR_MODIFY_PROPERTIES is granted.

**Example:**

A user `aUser` is granted the CQ delete page permission at `/foo`.

CRX 1.4: ``

**delete** is translated to **remove** ActionSet in CRX 1.4.

```
 aUser
```

is allowed to remove `/foo` and `/foo/*` and all properties.

CRX 2.0:

`aUser` is allowed to remove all nodes that match `/foo/*` but not `/foo` nor any properties such as `/foo/prop` nor `/foo/*/prop`.

**[4]** The JCR privileges JCR_LIFECYCLE_MANAGEMENT and JCR_RETENTION_MANAGEMENT have no correspondents in CRX 1.4.

They have intentionally been omitted from the mapping. The JCR_LIFECYCLE_MANAGEMENT is not used within the scope of CQ, and the JCR_RETENTION_MANAGEMENT privilege is expected to be present and used with defined retention management tools only and not within a regular CQ instance that does not offer retention management functionality.

**[5]** The sudo ActionSet available in CRX 1.4 has been eliminated in CRX 2.0.

With CRX 2.0, a user **A** can impersonate a user **B** if the principal name of **A** is listed in the **rep:impersonators** property of user **B**.

**[6]** The workspaceAccess ActionSet available in CRX 1.4 has been eliminated in CRX 2.0. With CRX 2.0, access to a given workspace is granted if the configured WorkspaceAccessManager implementation grants access.

The default implementation of CRX and CQ grants workspace access only if the user is known to the UserManager defined for that workspace.

Alternative implementations are as follows:

* SimpleWorkspaceAccessManager: Always granting access.
* DefaultSecurityManager#WorkspaceAccessManagerImpl: Granting  
  access if the root node is visible to a given user.

### CRX Access Control API {#crx-access-control-api}

The access control API available in CRX 1.x has been replaced by interfaces defined by JSR 283 and some extensions defined by the Jackrabbit API.

### AclSetupService {#aclsetupservice}

As of CQ 5.3, run-mode dependent default permissions can be defined with the AclSetupService that always runs during startup.

The AclSetupService allows you to specify access control entries to be created at a given path for a given principal name. In addition, it allows you to clear existing entries at a given path for a given principal name.

Because of the nature of the service, this may potentially cause issues with existing access control content.
