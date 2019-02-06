---
title: Embed adaptive form in external web page
seo-title: Embed adaptive form in external web page
description: Learn how to embed an adaptive form in an external web page
seo-description: Learn how to embed an adaptive form in an external HTML web page
uuid: 06e03da5-0a16-4f8f-8abd-02dcab09e8f6
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: author
discoiquuid: 838577ff-6f15-4b39-8470-7dde47364da4
index: y
internal: n
snippet: y
---

# Embed adaptive form in external web page{#embed-adaptive-form-in-external-web-page}

Learn how to embed an adaptive form in an external web page

AEM Forms allows form developers to seamlessly embed adaptive forms in an AEM Sites page or a web page hosted outside AEM. The embedded adaptive form is fully functional and users can fill and submit the form without leaving the page. It helps user remain in context of other elements on the web page and simultaneously interact with the form.

For information about embedding an adaptive form in an AEM Sites page, see [Embed adaptive form in AEM Sites](../../forms/using/embed-adaptive-form-aem-sites.md).

Read on for how to embed an adaptive form in an external web page.

## Prerequisites {#prerequisites}

Do the following before embedding an adaptive form in an external web page:

* Publish the adaptive form on AEM Publish instance.
* If AEM server and the web page are on different domains, do the following to configure the Apache Sling Referrer Filter bundle:

    1. On AEM author instance, go to AEM Web Console Configuration Manager at `http://[server]:[port]/system/console/configMgr`.  
    
    1. Find and click **[!UICONTROL Apache Sling Referrer Filter]** to edit the configuration.
    1. In the **[!UICONTROL Allowed Hosts]** field, specify the domain where the web page resides. It enables the host to make POST requests to the AEM server. You can also use regular expression to specify a series of external application domains.

## Embed adaptive form {#embed-adaptive-form}

You can embed an adaptive form by inserting a few lines of JavaScript in the web page. The API in the code sends an HTTP request to the AEM server for adaptive form resources and injects the adaptive form in the specified form container.

To embed the adaptive form:

1. Insert the following code in the web page in which you want to embed the adaptive form.

   ```
   var loadAdaptiveForm = function(options){
       if(options.path) {
           // options.path refers to the publish URL of the adaptive form
           // For Example: http:myserver:4503/content/forms/af/ABC, where ABC is the adaptive form
           // Note: If AEM server is running on a context path, the adaptive form URL must contain the context path 
           var path = options.path;
           path += "/jcr:content/guideContainer.html";
           $.ajax({
               url  : path ,
               type : "GET",
               data : {
                   // Set the wcmmode to be disabled
                   wcmmode : "disabled",
                   // Set the data reference, if any
                   "dataRef": options.dataRef
                   // Specify a different theme for the form object
                   "themeOverride" : options.themepath
               },
               async: false,
               success: function (data) {
                   // If jquery is loaded, set the inner html of the container
                   // If jquery is not loaded, use APIs provided by document to set the inner HTML but these APIs would not evaluate the script tag in HTML as per the HTML5 spec
                   // For example: document.getElementById().innerHTML
                   if(window.$ && options.CSS_Selector){
                       // HTML API of jquery extracts the tags, updates the DOM, and evaluates the code embedded in the script tag.
                       $(options.CSS_Selector).html(data);
                   }
               },
               error: function (data) {
                   // any error handler
               }
           });
       } else {
           if (typeof(console) !== "undefined") {
               console.log("Path of Adaptive Form not specified to loadAdaptiveForm");
           }
       }
   ```

1. In the embedded code:

    * Replace `options.path` with the publish URL of the adaptive form. If the AEM server is running on a context path, ensure that the URL includes the context path.
    * Replace `options.dataRef` with attributes to pass with the URL.
    * Replace `options.themePath` with the path to a theme other than the theme configured in the adaptive form. Alternatively, you can specify the theme path using the request attribute.
    * `CSS_Selector` is the CSS selector of the form container in which the adaptive form is embedded.

The adaptive form is embedded in the web page. Observe the following in the embedded adaptive form:

* Header and footer in the original adaptive form are not included in the embedded form.
* Drafts and submitted forms are available in the Drafts and Submissions tab in the Forms Portal. 
* Submit action configured on the original adaptive form is retained in the embedded form.
* Adaptive form rules are retained and fully functional in the embedded form.
* Experience targeting and A/B tests configured in the original adaptive form do not work in the embedded form. 
* If Adobe Analytics is configured on the original form, the analytics data is captured in Adobe Analytics server. However, it is not available in the Forms analytics report.

## Sample topology {#sample-topology}

The external web page that embeds the adaptive form sends requests to the AEM server, which typically sits behind the firewall in a private network. To ensure that the requests are securely directed to the AEM server, it is recommended to set up a reverse proxy server.

Let's look at an example how you can set up an Apache 2.4 reverse proxy server without dispatcher. In this example, you will host the AEM server with `/forms` context path and map `/forms` for the reverse proxy. It ensures that any request for `/forms` on Apache server are directed to the AEM instance. This topology helps reduces the number of rules at the dispatcher layer as all request prefixed with `/forms` route to the AEM server.

1. Open the `httpd.conf` configuration file and uncomment the following lines of code. Alternatively, you can add these lines of code in the file.

   ```
   LoadModule proxy_html_module modules/mod_proxy_html.so
    LoadModule proxy_http_module modules/mod_proxy_http.so
   ```

1. Set up proxy rules by adding the following lines of code in the `httpd-proxy.conf` configuration file.

   ```
   ProxyPass /forms http://[AEM_Instance]/forms
    ProxyPassReverse /forms http://[AEM_Instance]/forms
   ```

   Replace `[AEM_Instance`] with the AEM server publish URL in the rules.

If you do not mount the AEM server on a context path, the proxy rules at Apache layer will be as follows:

```java
ProxyPass /content http://<AEM_Instance>/content
ProxyPass /etc http://<AEM_Instance>/etc
ProxyPass /etc.clientlibs http://<AEM_Instance>/etc.clientlibs
# CSRF Filter
ProxyPass /libs/granite/csrf/token.json http://<AEM_Instance>/libs/granite/csrf/token.json
  
ProxyPassReverse /etc http://<AEM_Instance>/etc
ProxyPassReverse /etc.clientlibs http://<AEM_Instance>/etc.clientlibs
# written for thank you page and other URL present in AF during redirect
ProxyPassReverse /content http://<AEM_Instance>/content
```

>[!NOTE]
>
>If you set up any other topology, ensure that you whitelist the submit, prefill, and other URLs at the dispatcher layer.

## Best practices {#best-practices}

When embedding an adaptive form in a web page, consider the following best practices:

* Ensure that the styling rules defined in the web page CSS do not conflict with the form object CSS. To avoid the conflicts, you can reuse the web page CSS in the adaptive form theme using AEM client library. For information about using client library in adaptive form themes, see [Themes in AEM Forms](../../forms/using/themes.md).
* Make the form container in the web page use the entire window width. It ensures that the CSS rules configured for mobile devices work without any changes. If the form container does not take the entire window width, you need to write custom CSS to make the form adapt to different mobile devices. 
* Use ` [getData](https://helpx.adobe.com/experience-manager/6-3/forms/javascript-api/GuideBridge.html)` API to get the XML or JSON representation of form data in client. 
* Use ` [unloadAdaptiveForm](https://helpx.adobe.com/experience-manager/6-3/forms/javascript-api/GuideBridge.html)` API to unload the adaptive form from HTML DOM.
* Set up the access-control-origin header when sending response from AEM server.

