---
title: Extending Assets Search
description: Extend the search capabilities of [!DNL Experience Manager] Assets beyond out-of-the-box searches for assets by strings.
contentOwner: AG
feature: Search
role: Developer
exl-id: d68c735f-2699-4923-a7e7-4d1356eae335
---
# Extending Assets Search {#extending-assets-search}

You can extend Adobe Experience Manager Assets search capabilities. Out of the box, [!DNL Experience Manager] Assets searches for assets by strings.

Searching is done via the QueryBuilder interface so the search can be customized with several predicates. You can overlay the default set of predicates in the following directory: `/apps/dam/content/search/searchpanel/facets`.

You can also add additional tabs to the [!DNL Experience Manager] Assets admin panel.

>[!CAUTION]
>
>As of [!DNL Experience Manager] 6.4, Classic UI is deprecated. For announcement, see [Deprecated and Removed Features](../release-notes/deprecated-removed-features.md). You are encouraged to use Touch-enabled UI. For customizations, see [Search Facets](search-facets.md).

## Overlaying {#overlaying}

To overlay the preconfigured predicates, copy the `facets` node from `/libs/dam/content/search/searchpanel` to `/apps/dam/content/search/searchpanel/` or specify another `facetURL` property in the searchpanel configuration (the default is to `/libs/dam/content/search/searchpanel/facets.overlay.infinity.json`). 

![screen_shot_2012-06-05at113619am](assets/screen_shot_2012-06-05at113619am.png)

>[!NOTE]
>
>By default, the directory structure under / `apps` does not exist and needs to be created. Ensure that the node types match those under / `libs`.
>

## Adding tabs {#adding-tabs}

You can add additional Search tabs by configuring them in the [!DNL Experience Manager] Assets Admin. To create additional tabs:

1. Create the folder structure `/apps/wcm/core/content/damadmin/tabs,`if it does not already exist, and copy the `tabs` node from `/libs/wcm/core/content/damadmin` and paste it.
1. Create and configure the second tab, as desired.

   >[!NOTE]
   >
   >When you create a second siteadminsearchpanel, be sure to set an `id` property in order to prevent form conflicts.

## Creating Custom Predicates {#creating-custom-predicates}

[!DNL Experience Manager] Assets comes with a set of predefined predicates that can be used to customize an Asset Share page. Customizing an Asset Share in this way is covered in [Creating and Configuring an Asset Share Page](assets-finder-editor.md#creating-and-configuring-an-asset-share-page).

In addition to using pre-existing predicates, [!DNL Experience Manager] developers can also create their own predicates using the [Query Builder API](/help/sites-developing/querybuilder-api.md).

Creating custom predicates requires basic knowledge about the [Widgets framework](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html).

The best practice is to copy an existing predicate and adjust it. Sample predicates are located in `/libs/cq/search/components/predicates`.

### Example: Build a simple property predicate {#example-build-a-simple-property-predicate}

To build a property predicate:

1. Create a component folder in your projects directory, for example `/apps/geometrixx/components/titlepredicate`.
1. Add `content.xml`:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
    xmlns:cq="https://www.day.com/jcr/cq/1.0"
    xmlns:jcr="https://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Title Predicate"
       sling:resourceSuperType="foundation/components/parbase"
       allowedParents="[*/parsys]"
       componentGroup="Search"/>
   ```

1. Add `titlepredicate.jsp`.

   ```xml
   <%--
     Sample title predicate component

   --%><%@ page import="java.util.Calendar" %><%
   %><%@include file="/libs/foundation/global.jsp"%><%

       // A unique id is necessary in case this predicate is inserted multiple times on the same page
       String elemId = "cq-predicate-" +  Long.toString(Calendar.getInstance().getTimeInMillis());

   %><div class="predicatebox">

       <div class="title">Title</div>

       <%-- The wrapper for the form elements. All items will be append to this wrapper. --%>
       <div id="<%= elemId %>" class="content"></div>

   </div><script type="text/javascript">

       CQ.Ext.onLoad(function() {

           var predicateName = "property";
           var propertyName = "jcr:content/metadata/dc:title";
           var elemId = "<%= elemId %>";

           // Get the page wide available QueryBuilder.
           var qb = CQ.search.Util.getQueryBuilder();

           // createId adds a counter to the predicate name - useful in case this predicate
           // is inserted multiple times on the same page.
           var id = qb.createId(predicateName);

           // Hidden field that defines the property to search for; in our case this
           // is the "dc:title" metadata. The name "property" (or "1_property", "2_property" etc.)
           // indicates the server to use the property predicate
           // (com.day.cq.search.eval.JcrPropertyPredicateEvaluator).
           qb.addField({
               "xtype": "hidden",
               "renderTo": elemId,
               "name": id,
               "value": propertyName
           });

           // The visible text field. The name has to be like the one of the hidden field above
           // plus the ".value" suffix.
           qb.addField({
               "xtype": "textfield",
               "renderTo": elemId,
               "name": id + ".value"
           });

           // Depending on the predicate additional parameters allow to configure the
           // predicate. Here we add an operation parameter to create a "like" query.
           // Again note the name set to the id and a suffix.
           qb.addField({
               "xtype": "hidden",
               "renderTo": elemId,
               "name": id + ".operation",
               "value": "like"
           });

       });

   </script>
   ```

1. To make the component available, you need to be able to edit it. To make a component editable, in CRXDE, add a node `cq:editConfig` of primary type `cq:EditConfig`. So that you can remove paragraphs, add a multi-value property `cq:actions` with a single value of **DELETE**.
1. Navigate to your browser, and on your sample page (for example, `press.html`) switch to design mode and enable your new component for the predicate paragraph system (for example, **left**).  

1. In **Edit** mode, the new component is now available in the sidekick (found in the **Search** group). Insert the component in the **Predicates** column and type a search word, for example, **Diamond** and click the magnifying glass to start the search.

   >[!NOTE]
   >
   >When searching, be sure to type in the term exactly, including the correct case.

### Example: Build a simple group predicate {#example-build-a-simple-group-predicate}

To build a group predicate:

1. Create a component folder in your projects directory, for example `/apps/geometrixx/components/picspredicate`.
1. Add `content.xml`:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
    xmlns:cq="https://www.day.com/jcr/cq/1.0"
    xmlns:jcr="https://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Image Formats"
       sling:resourceSuperType="foundation/components/parbase"
       allowedParents="[*/parsys]"
       componentGroup="Search"/>
   ```

1. Add `titlepredicate.jsp`:

   ```java
   <%--

     Sample group predicate component

   --%><%@ page import="java.util.Calendar" %><%
   %><%@include file="/libs/foundation/global.jsp"%><%

       // A unique id is necessary in case this predicate is inserted multiple times on the same page.
       String elemId = "cq-predicate-" +  Long.toString(Calendar.getInstance().getTimeInMillis());

   %><div class="predicatebox">

       <div class="title">Image Formats</div>

       <%-- The wrapper for the form elements. All items will be append to this wrapper. --%>
       <div id="<%= elemId %>" class="content"></div>

   </div><script type="text/javascript">

       CQ.Ext.onLoad(function() {

           var predicateName = "property";
           var propertyName = "jcr:content/metadata/dc:format";
           var elemId = "<%= elemId %>";

           // Get the page wide available QueryBuilder.
           var qb = CQ.search.Util.getQueryBuilder();

           // Create a unique group ID; will return e.g. "1_group".
           var groupId = qb.createGroupId();

           // Hidden field that defines the property to search for  - in our case "dc:format" -
           // and declares the group of predicates. "property" in the name ("1_group.property")
           // indicates to the server to use the "property predicate"
           // (com.day.cq.search.eval.JcrPropertyPredicateEvaluator).
           qb.addField({
               "xtype": "hidden",
               "renderTo": "<%= elemId %>",
               "name": groupId + "." + predicateName, // 1_group.property
               "value": propertyName
           });

           // Declare to combine the multiple values using OR.
           qb.add(new CQ.Ext.form.Hidden({
               "name": groupId + ".p.or",  // 1_group.p.or
               "value": "true"
           }));

           // The options
           var options = [
               { "label":"JPEG", "value":"image/jpeg"},
               { "label":"PNG",  "value":"image/png" },
               { "label":"GIF",  "value":"image/gif" }
           ];

           // Build a checkbox for each option.
           for (var i = 0; i < options.length; i++) {
               qb.addField({
                   "xtype": "checkbox",
                   "renderTo": "<%= elemId %>",
                   // 1_group.property.0_value, 1_group.property.1_value etc.
                   "name": groupId + "." +  predicateName + "." + i + "_value",
                   "inputValue": options[i].value,
                   "boxLabel": options[i].label,
                   "listeners": {
                       "check": function() {
                           // Submit the search form when checking/unchecking a checkbox.
                           qb.submit();
                       }
                   }
               });
           }

       });
   ```

1. To make the component available, you need to be able to edit it. To make a component editable, in CRXDE, add a node `cq:editConfig` of primary type `cq:EditConfig`. So that you can remove paragraphs, add a multi-value property `cq:actions` with a single value of `DELETE`.
1. Navigate to your browser, and on your sample page (for example, `press.html`) switch to design mode and enable your new component for the predicate paragraph system (for example, **left**).
1. In **Edit** mode, the new component is now available in the sidekick (found in the **Search** group). Insert the component in the **Predicates** column.

### Installed Predicate Widgets {#installed-predicate-widgets}

The following predicates are available as preconfigured ExtJS widgets.

### FulltextPredicate {#fulltextpredicate}

| Property | Type | Description |
|---|---|---|
| predicateName | String | Name of the predicate. Defaults to `fulltext` |
| searchCallback | Function | Callback for triggering search on event `keyup`. Defaults to `CQ.wcm.SiteAdmin.doSearch` |

### PropertyPredicate {#propertypredicate}

| Property | Type | Description |
|---|---|---|
| predicateName | String | Name of the predicate. Defaults to `property` |
| propertyName | String | Name of the JCR property. Defaults to `jcr:title` |
| defaultValue | String | Prefilled default value. |

### PathPredicate {#pathpredicate}

| Property | Type | Description |
|---|---|---|
| predicateName | String | Name of the predicate. Defaults to `path` |
| rootPath | String | Root path of the predicate. Defaults to `/content/dam` |
| pathFieldPredicateName | String | Defaults to `folder` |
| showFlatOption | Boolean | Flag to show Checkbox `search in subfolders`. Defaults to true. |

### DatePredicate {#datepredicate}

| Property | Type | Description |
|---|---|---|
| predicateName | String | Name of the predicate. Defaults to `daterange` |
| propertyname | String | Name of the JCR property. Defaults to `jcr:content/jcr:lastModified` |
| defaultValue | String | Prefilled default value |

### OptionsPredicate {#optionspredicate}

| Property | Type | Description |
|---|---|---|
| title | String | Adds an additional top title |
| predicateName | String | Name of the predicate. Defaults to `daterange` |
| propertyname | String | Name of the JCR property. Defaults to `jcr:content/metadata/cq:tags` |
| collapse | String | Collapse level. Defaults to `level1` |
| triggerSearch | Boolean | Flag for triggering search on check. Defaults to false |
| searchCallback | Function | Callback for triggering search. Defaults to `CQ.wcm.SiteAdmin.doSearch` |
| searchTimeoutTime | Number | Timeout before searchCallback is fired. Defaults to 800ms |

## Customizing Search Results {#customizing-search-results}

The presentation of search results on an Asset Share page is governed by the selected lens. [!DNL Experience Manager] Assets comes with a set of predefined lenses that can be used to customize an Asset Share page. Customizing an Asset Share in this way is covered in [Creating and Configuring an Asset Share Page](assets-finder-editor.md#creating-and-configuring-an-asset-share-page).

In addition to using pre-existing lenses, [!DNL Experience Manager] developers can also create their own lenses.
