---
title: Customizing Asset Share
seo-title: Customizing Asset Share
description: null
seo-description: null
uuid: 588a9dde-f5d7-4a33-8d1b-e67b03f870a3
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: extending-assets
content-type: reference
discoiquuid: 61bdb731-4f39-4a05-96e3-0ceb97f42084
index: y
internal: n
snippet: y
---

# Customizing Asset Share{#customizing-asset-share}

The Asset Share page is used to search for assets based on their metadata. You can customize the search, search results, and what actions users can take.

## Creating an Asset Share Template {#creating-an-asset-share-template}

* Geometrixx Sample Page: **/content/geometrixx/en/press.html**
* Sample Template:** /apps/geometrixx/templates/assetshare**
* Sample Page Component:** /apps/geometrixx/components/assetshare **

#### Configuring Clientlib {#configuring-clientlib}

Adobe Experience Manager (AEM) Assets components use an extension of the WCM edit clientlib. The clientlibs are usually loaded in **init.jsp**.

Compared to the default clientlib loading (in core's **init.jsp**), an AEM Assets template must have the following:

* The template must include the **cq.dam.edit** clientlib (instead of **cq.wcm.edit**).

* The clientlib must also be included in disabled WCM mode (for example, loaded on **publish**) to be able to render the predicates, actions, and lenses.

In most cases, copying the existing sample **init.jsp** (**/apps/geometrixx/components/assetshare/init.jsp**) should meet these needs.

#### Additional Style Sheets {#additional-style-sheets}

Some of the AEM Assets components use the AEM widgets library. To be rendered properly in the content context, an additional style sheet has to be loaded. The tag action component requires one more.

```xml
<link href="/etc/designs/geometrixx/ui.widgets.css" rel="stylesheet" type="text/css">
```

#### Geometrixx Style Sheet {#geometrixx-style-sheet}

The sample page components require all selectors to start with .**assetshare** of **static.css** (**/etc/designs/geometrixx/static.css**). Best practice: Copy all** .assetshare **selectors to your style sheet and adjust the rules as desired.

#### Query Builder {#query-builder}

The Geometrixx sample page includes the default AEM Assets query builder component (**/libs/dam/components/assetshare/querybuilder**) with two columns (in **/apps/geometrixx/components/assetshare/body.jsp**):

* left column for predicates and actions
* right column for the lens deck that displays the current lens
* top bar with search field, paging, and lens switcher

To achieve one of the following, you have to create (and include) your own component:

* different layout
* different default values for the Query Builder, for example, **limit** (It is possible to set the values available in the Query Builder Properties dialog box. The default values are only applied as long as no values have been set.)

The best practice is to copy the existing component to your project folder in** /apps** and adjust it.

## Customizing Actions {#customizing-actions}

AEM Assets comes with a set of predefined actions that can be used to customize an Asset Share page. Customizing an Asset Share in this way is covered in [Creating and Configuring an Asset Share Page](../../assets/using/assets-finder-editor.md#main-pars-title).

In addition to using pre-existing actions, AEM developers can also create their own actions.

### Adding a custom action {#adding-a-custom-action}

Creating custom actions requires basic knowledge about the [Widgets framework](/sites/developing/using/reference-materials/widgets-api/index).

The best practice is to copy an existing action and adjust it. Sample actions are located in **/libs/cq/dam/assetshare/components/actions**. See also [Developing components](../../sites/developing/using/developing-components-samples.md).

#### Example: Create a simple action {#example-create-a-simple-action}

To create a custom action:

1. Create a component folder in your projects directory, for example, **/apps/geometrixx/components/sampleaction.**
1. Add **content.xml**:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0" xmlns:cq="http://www.day.com/jcr/cq/1.0" xmlns:jcr="http://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Image Formats"
       sling:resourceSuperType="foundation/components/parbase"
       allowedParents="[*/parsys]"
       componentGroup="Asset Share"/>
   
   ```

1. Add **sampleaction.jsp**:

   ```xml
   <%--
   
     Sample action component
   
   --%><%@include file="/libs/foundation/global.jsp"%>
   <script type="text/javascript">
       // Note: Functions should be defined in a global script block. The script inside
       // the component will be loaded in every paragraph that uses this component.
   
       // alert the title and path of the selected assets.
       function alertSelectedAssets() {
           var selection = CQ.search.Util.getSelection();
   
           if (selection.length == 0) {
               CQ.dam.Util.alertNoSelection();
               return;
           }
   
           var msg = "";
           for (var i = 0; i < selection.length; i++) {
               msg += "Title: " + selection[i]["jcr:content"]["metadata"]["dc:title"] + "\n";
               msg += "Path: " + selection[i]["jcr:path"] + "\n\n";
           }
           alert(msg);
       }
   
   </script>
   <a href="javascript:alertSelectedAssets();">Sample Action</a>
   
   ```

1. To make the component available, you need to be able to edit it. To make a component editable, in CRXDE, add a node **cq:editConfig** of primary type **cq:EditConfig**. So that you can remove paragraphs, add a multi-value property **cq:actions** with a single value of **DELETE**.
1. Navigate to your browser, and on your sample page (for example, **press.html**) switch to design mode and enable your new component for the predicate paragraph system (for example, **actions**).
1. In **Edit** mode, the new component is now available in the sidekick (found in the **Asset Share **group). Insert the component in actions area.

