---
title: Community Components Guide
seo-title: Community Components Guide
description: An interactive development tool to get started with the social component framework (SCF)
seo-description: An interactive development tool to get started with the social component framework (SCF)
uuid: 14a1a3e6-961d-4252-9e10-a3d833a0a78d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: f6055b41-25de-4fc1-a659-21673d3d4a81
index: y
internal: n
snippet: y
---

# Community Components Guide{#community-components-guide}

The Community Components guide is an interactive development tool for the [social component framework (SCF)](../../communities/using/scf.md). It provides a list of available AEM Communities components or the more complex features built of multiple components.

Along with basic information for each component, the guide allows for experimentation with how the SCF components/features work and how they can be configured or customized.

For information regarding development essentials related to each component, see [Feature and Component Essentials](../../communities/using/essentials.md).

## Getting Started {#getting-started}

The guide is intended for use on development installations of author (localhost:4502) and publish (localhost:4503) instances.

The Community Components site is accessed by browsing to

* [http://&lt;server&gt;:&lt;port&gt;/content/community-components/en.html](http://localhost:4502/content/community-components/en.html)

Interactions with the Communities components will vary depending on :

* the server (author or publish)
* whether or not the site visitor is signed in
* if signed in, the privileges assigned to the member
* whether or not the default SRP, [JSRP](../../communities/using/jsrp.md), is in use

On author, to enter edit mode, insert either * `editor.html`* or * `cf#`* as the first path segment after the server name :

* Standard UI :  
  [http://&lt;server&gt;:&lt;port&gt;/editor.html/content/community-components/en.html](http://localhost:4502/editor.html/content/community-components/en.html)

* Classic UI :  
  [http://&lt;server&gt;:&lt;port&gt;/cf#/content/community-components/en.html](http://localhost:4502/cf#/content/community-components/en.html)

>[!NOTE]
>
>On author in Edit mode, the links on a page are not active.
>
>To navigate to a component page, first select Preview mode to activate the links.
>
>With the component page displayed in the browser, return to Edit mode in order to open the component's edit dialog.
>
>For general authoring information, view the [quick guide to authoring pages](../../sites/authoring/using/qg-page-authoring.md).
>
>If not familiar with AEM, view the documentation on [basic handling](../../sites/authoring/using/basic-handling.md).

### Home Page {#home-page}

The guide provides a listing of SCF components available for preview and prototyping along the left side of the page.

Components Guide as viewed on an author instance in Edit mode :

![](assets/chlimage_1-404.png) 

## Component Pages {#component-pages}

Select a component from the list along the left side of the page. 

![](assets/chlimage_1-405.png)

The main body of the guide displays :

1. Title : the name of the component selected
1. [Client-Side Llibraries](#clientsidelibraries) : a list of one or more required categories
1. [Includable](../../communities/using/scf.md#addorincludeacommunitiescomponent) : if the component may be dynamically included, then the state can be toggled in author edit mode :

    * if added, text displayed is : "This component is included via its par node."
    * if included, text displayed is : "This component is included dynamically."
    * if not includable, then no text is displayed

1. Sample Component or Feature : an active instance of the component or feature. If a component, it may be altered with changes made to the templates, CSS and data provided in the tab section.

>[!NOTE]
>
>After making a selection from the left-hand side, the component will appear below, instead of beside, the listing of components when the browser window is too narrow.

### Author Interactions {#author-interactions}

When using the guide on an author instance, it is possible to experience configuring a component by opening its dialog. Information for developers is provided in the [Component and Feature Essentials](../../communities/using/essentials.md) section of the documentation, while the dialog settings are described in [Communities Components](../../communities/using/author-communities.md) section for authors.

For the Community Components guide, some component dialog settings are overlayed with the [Includable](../../communities/using/scf.md#addorincludeacommunitiescomponent) toggle state. To toggle between using the existing resource or a dynamically included resource, in edit mode select both the component and includable text and double-click to open the edit dialog :

![](assets/chlimage_1-406.png)

Under the **Templates **tab :

![](assets/chlimage_1-407.png)

* **Include the child component with sling:include** 
  
  If unchecked, the Component Guide will use the existing resource in the repository (a jcr node which is a child of a par node).

    * text displayed is : "This component is included via its par node."

  If checked, the Component Guide will use sling to dynamically include a component of the child node's resourceType (non-existing resource).

    * text displayed is : "This component is included dynamically."

  Default is unchecked.

### Publish Interactions {#publish-interactions}

When using the guide on a publish instance, it is possible to experience the components and features as a site visitor (not signed in) and as members with various privileges when signed in.

>[!NOTE]
>
>Be aware, if the SRP is left defaulted to [JSRP](../../communities/using/jsrp.md), then UGC entered on the publish instance will only be visible on publish, and will *not *be visible from the [moderation](../../communities/using/moderate-ugc.md) console on the author instance.

## Client-Side Libraries {#client-side-libraries}

The client-side libraries (clientlibs) listed for each component are those *required *to be referenced when the component is placed on a page. The clientlibs provide a means of managing and optimizing the download of the Javascript and CSS used to render the component in the browser.

For more information, visit [Clientlibs for Communities Components](../../communities/using/clientlibs.md).

## Impersonation {#impersonation}

On the author instance, where one is often signed in as an administrator or developer, in order to experience the component logged in as another user, use the text box to the left of the **Impersonate **button to either type in the username or select from the pull down list, and then click the button. Click Revert to signout and end the impersonation.

The publish instance does not need to impersonate. Simply use the Login/Logout link to impersonate various users, such as the [demo users](../../communities/using/tutorials.md#demousers).

## Customization {#customization}

When enabled, each SCF component is available for prototyping of possible customizations by temporarily modifying the component's template, CSS and data.

### Enabling Customization {#enabling-customization}

>[!NOTE]
>
>**This tool is read-only**. None of the edits made to templates, CSS or data are saved to the repository.

To quickly experiment with customizations, the `scg:showIde`property must be added to the component page's content JCR node and set to true.

Using the comments component as an example, on either the author or publish instance, signed in with administrator privileges :

1. browse to [CRXDE Lite](../../sites/developing/using/developing-with-crxde-lite.md)  
   for example, [http://localhost:4503/crx/de](http://localhost:4503/crx/de)

1. select the component's `jcr:content` node  
   for example, `/content/community-components/en/comments/jcr:content`

1. add a property

    * **Name **scg:showIde
    * **Type **String
    * **Value **true

1. select **Save All**
1. reload the Comments page in the guide  
   [http://localhost:4503/content/community-components/en/comments.html](http://localhost:4503/content/community-components/en/comments.html)

1. notice there are now 3 tabs for Templates, CSS, and Data.

![](assets/chlimage_1-408.png) ![](assets/chlimage_1-409.png) 

### Templates Tab {#templates-tab}

Select the templates tab to see the templates associated with the component.

The Template Editor allows local edits to be compiled and applied to the sample component instance at the top of the page without affecting the component in the repository.

Running compile on local edits will highlight any errors along by placing a dot in the gutter and marking the text red.

### CSS Tab {#css-tab}

Select the CSS tab to see the CSS associated with the component.

If a component is a composite of multiple components, some CSS may be listed under one of the other components.

The CSS Editor allows the CSS to be modified and applied to the sample component instance at the top of the page.

A rule may be selected to highlight the parts of the DOM using that rule by clicking next to the rule in the gutter.

### Data Tab {#data-tab}

Select the Data tab to show the .social.json endpoint data. This data is editable and is applied to the sample component instance.

Syntax errors may be marked in the gutter as well as highlighted in the editor.
