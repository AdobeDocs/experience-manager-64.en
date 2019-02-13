---
title: Community Site Essentials
seo-title: Community Site Essentials
description: Exporting and deleting community sites and creating custom site templates
seo-description: Exporting and deleting community sites and creating custom site templates
uuid: 03bf9bfd-d6c1-4d9b-916a-a39cb565c69b
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 64a021ca-beed-448f-a280-da3ae1c18804
index: y
internal: n
snippet: y
---

# Community Site Essentials{#community-site-essentials}

## Custom Site Template {#custom-site-template}

A custom site template may be specified separately for each language copy of a community site.

To do so,

* create a custom template
* overlay the default site template path
* add the custom template to the overlay path
* specify the custom template by adding a `page-template` property to the `configuration` node

**Default template**:

/**libs**/social/console/components/hbs/sitepage/**sitepage**.hbs

**Custom template in overlay path** :

/**apps**/social/console/components/hbs/sitepage/**&lt;*template-name*&gt;**.hbs

** Property** : page-template  
** Type** : String  
** Value** : &lt;*template-name*&gt; (no extension)

**Configuration node** :

/content/&lt;*community site path*&gt;/&lt;*lang*&gt;/configuration

for example : /content/sites/engage/en/configuration

>[!NOTE]
>
>All nodes in the overlaid path need only be of type `Folder`.

>[!CAUTION]
>
>If the custom template is given the name *sitepage.hbs,* then all community sites will be customized.

### Custom Site Template Example {#custom-site-template-example}

As an example, `vertical-sitepage.hbs` is a site template that results in the placement of menu links vertically down the left side of the page, instead of horizontally below the banner.

[Get File](assets/vertical-sitepage.hbs)
Place the custom site template in the overlay folder :

/**apps**/social/console/components/hbs/sitepage/**vertical-sitepage**.hbs

Identify the custom template by adding a `page-template` property to the configuration node :

/content/sites/sample/en/configuration

![](assets/chlimage_1-87.png)

Be sure to** Save All** and replicate custom code to all AEM instances (custom code is not included when the community site content is published from the console).

The recommended practice for replicating custom code is to [create a package](../../sites/administering/using/package-manager.md#creatinganewpackage) and deploy it on all instances.

## Exporting a Community Site {#exporting-a-community-site}

Once a community site is created, it is possible to export the site as an AEM package stored in package manager and available for download and upload.

This is available from the [Communities Sites console](../../communities/using/sites-console.md#exportingthesite).

Note that UGC and custom code is not included in the community site package.

To export UGC, use the [AEM Communities UGC Migration Tool](https://github.com/Adobe-Marketing-Cloud/communities-ugc-migration), an open source migration tool available on GitHub.

## Deleting a Community Site {#deleting-a-community-site}

As of AEM Communities 6.3 Service Pack 1, Delete Site icon appears on hovering over the community site from Communities &gt; Sites console. During development, if it is desired to delete a community site and start fresh, you can use this functionality. Deleting a community site, removes the following items associated with that site:

* [UGC](#usergeneratedcontent)
* [user groups](#communityusergroups)
* [assets](#enablementassets)
* [database records](#databaserecords)

### Community Unique Site ID {#community-unique-site-id}

To identify the unique site ID associated with the community site, using CRXDE :

* navigate to the language root of the site, such as  
  `/content/sites/*<site name>*/en/rep:policy`

* find the `allow<#>` node with a `rep:principalName` in this format :

    * `rep:principalName = *community-enable-nrh9h-members*`

* the site ID is the 3rd component of `rep:principalName`  
  for example, if `rep:principalName = community-enable-nrh9h-members`

    * **site name** = *enable*
    
    * **site ID** = *nrh9h*
    
    * **unique site ID** = *enable-nrh9h*

### User Generated Content {#user-generated-content}

Obtain the communities-srp-tools project from Github :

* [https://github.com/Adobe-Marketing-Cloud/communities-srp-tools](https://github.com/Adobe-Marketing-Cloud/communities-srp-tools)

This contains a servlet to delete all UGC from any SRP.

All UGC may be removed or for a specific site, for example :

* path=/content/usergenerated/asi/mongo/content/sites/engage

This only removes user generated content (entered on publish) and not authored content (entered on author). Therefore, [shadow nodes](../../communities/using/srp.md#shadownodes) are not affected.

### Community User Groups {#community-user-groups}

On all author and publish instances, from the [security console](../../sites/administering/using/security.md), locate and remove the [user groups](../../communities/using/users.md) that are :

* prefixed with `community`
* followed by [unique site id](#communityuniquesiteid)

For example, `community-engage-x0e11-members`.

<!--
Comment Type: draft

<h3>Community Web Site</h3>
-->

<!--
Comment Type: draft

<p>From the main console :</p>
<ul>
<li>select <strong>Sites</strong></li>
<li>select <strong>Community Sites</strong> folder</li>
<li>enter <strong>Select </strong>mode</li>
<li>select Community Site to delete</li>
<li>select <strong>Delete</strong> (may need to select from <strong>More...</strong>)</li>
</ul>
-->

### Enablement Assets {#enablement-assets}

From the main console :

* select **Assets**
* enter **Select** mode
* select folder named with the [unique site Id](#communityuniquesiteid)
* select **Delete** (may need to select from **More...**)

### Database Records {#database-records}

There is no tool for selectively deleting database entries for one specific enablement community site.

When all community sites are being deleted, then drop the enablementdb and scormenginedb using MySQL Workbench.
