---
uuid: 96f6ec8c-30dc-49fd-9e88-59a4ca2cb961
index: y
internal: n
snippet: y
translate: y
---

# Upgrading Custom Search Forms

In AEM 6.2, the location where Customized Search Forms are stored in the repository has changed. Upon upgrading, they are moved from their location in 6.1 at:

* /apps/cq/gui/content/facets

to a new location under:

* /conf/global/settings/cq/search/facets

Because of this, manual adjustments are required after an upgrade in order for the forms to continue to function.

This applies to new Search Forms as well as default Forms that have been customized.

For more information, see the documentation on [Search Facets](/content/help/en/experience-manager/6-4/assets/using/custom-search-facets).

---

## Changing the resourceType property
Unless stated otherwise, most of the adjustments that need to be done after the upgrade require changing the `sling:resourceType` property for the configured custom Search Forms. This is needed so that the property points to the correct location of the rendering script.

You can change the property by doing the following:

1. Open CRXDE Lite by going to `http://server:port/crx/de/index.jsp`

1. Browse to the location of the node that needs to be adjusted, as specified in the List of [Custom Search Forms](upgrading-custom-search-forms.md#ListofCustomSearchForms) below.

1. Click the node. In the right properties pane, click and modify the **sling:resourceType** property.

1. Finally, save the changes by pressing the **Save All** button.

---

## List of Custom Search Forms
Below you will find a list of all cusom Search Forms and the modifications they require after the upgrade. They refer to the names in `/conf/global/settings/cq/search/facets/sites/items`.

### Fulltext Predicate with node name "fulltext"

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1</td> 
   <td>fulltext</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/common/admin/customsearch/searchpredicates/fulltextpredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td>n/a</td> 
  </tr>
 </tbody>
</table>

In AEM 6.1, the standard fulltext predicate was part of the search form. In 6.2, the fulltext field has been replaced by the OmniSearch. This predicate is skipped programmatically and can be removed.

**Action:** Remove the node entirely.

### Other Fulltext Predicates

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search From in 6.1</td> 
   <td>n/a</td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/common/admin/customsearch/searchpredicates/fulltextpredicate</p> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>common/admin/customsearch/searchpredicates/fulltextpredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Path Browser Predicates

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>path</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/common/admin/customsearch/searchpredicates/pathpredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>common/admin/customsearch/searchpredicates/pathpredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Tags Predicates

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>tags</td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/common/admin/customsearch/searchpredicates/tagspredicate</p> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>common/admin/customsearch/searchpredicates/tagspredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the **resourceType** property (add "**/coral**" like in the 6.2 location indicated above).

### Page Status Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>pagestatuspredicate</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/pagestatuspredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td>n/a</td> 
  </tr>
 </tbody>
</table>

The Page Status has been replaced by two Options Property Predicates, one for publish and one for LiveCopy status.

**Actions: **

* Remove the `pagestatuspredicate` node
* Copy node

    * `/libs/settings/cq/search/facets/sites/jcr:content/items/publishstatuspredicate`    
    * to `/conf/global/settings/cq/search/facets/sites/jcr:content/items`

* Copy node

    * `/libs/settings/cq/search/facets/sites/jcr:content/items/livecopystatuspredicate`    
    * to `/conf/global/settings/cq/search/facets/sites/jcr:content/items`

* Make sure you set `listOrder` property for the `analyticspredicate` node to "**8**". This is needed in order to avoid conflicts.

### Date Range Predicates

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>daterangepredicate</td> 
  </tr>
  <tr>
   <td>Resource type in 6.1</td> 
   <td>cq/gui/components/common/admin/customsearch/searchpredicates/daterangepredicate</td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>common/admin/customsearch/searchpredicates/daterangepredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Hidden Filter

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>type</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>granite/ui/components/foundation/form/hidden</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>granite/ui/components/foundation/form/hidden</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Nothing to adjust.

### Analytics Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>analyticspredicate</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/analyticspredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>siteadmin/admin/searchpanel/searchpredicates/analyticspredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Range Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>n/a</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/rangepredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>siteadmin/admin/searchpanel/searchpredicates/rangepredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

>[!NOTE]
>
><p>Note: In opposition to 6.1, the Range Predicate does no longer render a tag in the search bar.</p>

### Options Property Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>n/a</td> 
   <td> </td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/optionspredicate</p> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>siteadmin/admin/searchpanel/searchpredicates/optionspredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Slider Range Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>n/a</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/sliderrangepredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>siteadmin/admin/searchpanel/searchpredicates/sliderrangepredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Components Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>n/a</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/componentspredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>siteadmin/admin/searchpanel/searchpredicates/componentspredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Author Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>n/a</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/userpredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>siteadmin/admin/searchpanel/searchpredicates/userpredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Templates Predicate

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Node/s in default Search Form in 6.1<br /> <br /> </td> 
   <td>n/a</td> 
  </tr>
  <tr>
   <td><p>Resource type in 6.1</p> </td> 
   <td><p>cq/gui/components/siteadmin/admin/searchpanel/searchpredicates/templatespredicate</p> </td> 
  </tr>
  <tr>
   <td>Resource type in 6.2</td> 
   <td><p>cq/gui/components<strong>/coral/</strong>siteadmin/admin/searchpanel/searchpredicates/templatespredicate</p> </td> 
  </tr>
 </tbody>
</table>

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

---

## Assets Admin Search Rail
The nodes below refer to the names in `/conf/global/settings/dam/search/facets/assets/items`

### Fulltext Predicate with node name "fulltext"

| Node/s in default Search Form in 6.1 |fulltext |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/fulltextpredicate |
| Resource type in 6.2 |n/a |

In 6.1 the standard fulltext predicate was part of the search form. In 6.2 the fulltext field has been replaced by OmniSearch. This predicate is skipped programmatically and can be removed.

**Action:** Remove the above mentioned node.

### Path Browser Predicates

| Node/s in default Search Form in 6.1 |pathbrowser |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/pathbrowserpredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/pathbrowserpredicate |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### Mime Type Predicates

| Node/s in default Search Form in 6.1 |mimetype |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/optionspredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/optionspredicate |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above).

### File Size Predicates

| Node/s in default Search Form in 6.1 |filesize |  |
|---|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/filesizepredicate |  |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/sliderangepredicate |  |

**Action:** Adjust `resourceType` as shown in the 6.2 location above.

### Asset Last Modified Predicates

| Node/s in default Search Form in 6.1 |assetlastmodifiedpredicate |  |
|---|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/assetlastmodifiedpredicate |  |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/assetlastmodifiedpredicate |  |

### Publish Predicate

| Node/s in default Search Form in 6.1 |publish |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/publishpredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/publishpredicate |

**Actions: **

* Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)
* Add an `optionPaths` (of type String) property with the value: `/libs/dam/options/predicates/publish`
* Add `singleSelect` property with boolean value `true`.

### Status Predicates

| Node/s in default Search Form in 6.1 |status |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/optionspredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/optionspredicate |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)

### Expiry Status Predicates

| Node/s in default Search Form in 6.1 |expirystatus |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/expiredassetpredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/expiredassetpredicate |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)

### Metadata Validity Predicates

| Node/s in default Search Form in 6.1 |metadatavalidity |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/optionspredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/optionspredicate |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)

### Rating Predicates

| Node/s in default Search Form in 6.1 |rating |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/ratingpredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/sliderangepredicate |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)

### Orientation Predicate

| Node/s in default Search Form in 6.1 |orientation |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/tagsfilterpredicate |
| Resource type in 6.2 |cq/gui/components/coral/common/admin/customsearch/searchpredicates/tagspredicate |

**Actions: **

* Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)
* Add a `fieldLabel` property with the same value as the `text` property on the same node.
* Add an `emptyText` property with the value same as the `text` property on the same node.
* Add a `rootPath` property with the same value same as the `optionPaths` property on the same node.

### Style Predicate

| Node/s in default Search Form in 6.1 |style |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/tagsfilterpredicate |
| Resource type in 6.2 |cq/gui/components/coral/common/admin/customsearch/searchpredicates/tagspredicate |

**Actions: **

* Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)
* Add a `fieldLabel` property with the same value as the `text` property on the same node.
* Add an `emptyText` property with the value same as the `text` property on the same node.
* Add a `rootPath` property with the same value same as the `optionPaths` property on the same node.

### Video Format Predicates

| Node/s in default Search Form in 6.1 |videoFormat |
|---|---|
| Resource type in 6.1 |dam/gui/components/admin/customsearch/searchpredicates/optionspredicate |
| Resource type in 6.2 |dam/gui/coral/components/admin/customsearch/searchpredicates/optionspredicate |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)

### Mainasset Predicate

| Node/s in default Search Form in 6.1 |mainasset |
|---|---|
| Resource type in 6.1 |granite/ui/components/foundation/form/hidden |
| Resource type in 6.2 |granite/ui/components/coral/foundation/form/hidden |

**Action:** Adjust the `resourceType` property (add "**/coral**" like in the 6.2 location indicated above)
