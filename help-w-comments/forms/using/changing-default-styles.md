---
title: Changing default styles of HTML5 forms
seo-title: Changing default styles of HTML5 forms
description: HTML5 forms styling is based on CSS. You can change the default styles of the form.
seo-description: HTML5 forms styling is based on CSS. You can change the default styles of the form.
uuid: 52098467-c70d-463b-bbd5-32e6e2e95c48
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 2756cc11-4cb9-4178-b31b-4e3e4804eea6
index: y
internal: n
snippet: y
---

# Changing default styles of HTML5 forms{#changing-default-styles-of-html-forms}

HTML5 forms are rendered using HTML5 capabilities and the styling of the rendered form is done using CSS. Default appearance of a HTML5 forms is similar to its PDF rendition. Developers can use custom CSS to change default appearance of HTML5 forms.

This article provides step-by-step information to change style of an HTML5 form and [Introduction to Styles](../../forms/using/css-styles.md) article contains detailed information about various styling aspects of HTML5 forms. Ensure that you read Introduction to styles article before performing steps mentioned in this article.

The following two images show the difference between the default and customized styles.

![](assets/pictures-002-small.png) 

## Style your forms {#style-your-forms}

1. Access the CRX DE interface at the URL: **http://&lt;server&gt;:&lt;port&gt;/crx/de** and create a profile or choose an existing profile. To know how to create a profile, see [Creating a new Profile](../../forms/using/custom-profile.md)
1. Navigate to the folder in which you have created the profile renderer and create a CSS style sheet file. The steps to follow are

    1. Right click the folder and select **create **-&gt; **create File** from the menu
    
    1. In the create file dialog, enter the name of the style sheet. Make sure that you use the extension .css (for example stylesheet.css)
    1. From the navigation pane, open the CSS file that you have created.
    1. Define the CSS classes of the components that you want to style and add styles in those classes.

   To know which CSS classes to create for a particular component in your HTML5 forms, see [Introduction to Styles](../../forms/using/css-styles.md).  

1. Open the Profile Renderer page (jsp file) in CRX DE, and include the CSS file in the page just below the XFA client library. Perform these steps to include the CSS file in profile.

    1. Search in the renderer page for the following line:  
    
       &lt;cq:includeClientLib categories="xfaforms.profile" /&gt;  
    
    1. Insert the following below the line above to include the style sheet:  
    
       &lt;link href="/path/to/stylesheet" rel="stylesheet" type="text/css"/&gt;  
    
    1. Save the file.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)

<!--
<related-links>
<a href="../../forms/using/introduction-widgets.md">Appearance framework for adaptive and HTML5 forms</a>
<a href="../../forms/using/custom-profile.md">Creating custom profiles for HTML5 forms</a>
<a href="../../forms/using/custom-widgets.md">Custom Widgets for HTML5 forms</a>
<a href="../../forms/using/form-bridge-apis.md">Form Bridge for HTML5 forms</a>
<a href="../../forms/using/integrate-form-bridge-forms-portal.md">Integrating form bridge with forms portal</a>
<a href="../../forms/using/css-styles.md">Changing default styles of HTML5 forms</a>
</related-links>
-->
