---
uuid: b17e1a8a-3b9c-43b0-8113-6d1f9924465c
index: y
internal: n
snippet: y
translate: y
---

# OSGi Configuration Settings

[OSGi](http://www.osgi.org/) is a fundamental element in the technology stack of AEM. It is used to control the composite bundles of AEM and their configuration.

OSGi "*provides the standardized primitives that allow applications to be constructed from small, reusable and collaborative components. These components can be composed into an application and deployed*".

This allows easy management of bundles as they can be stopped, installed, started individually. The interdependencies are handled automatically. Each OSGi Component (see the [OSGi Specification](http://www.osgi.org/Specifications/HomePage)) is contained in one of the various bundles. When working with AEM there are several methods of managing the configuration settings for such bundles; see [Configuring OSGi](configuring-osgi.md) for more details and the recommended practices.

The following OSGi configuration settings (listed according to bundle) are relevant to project implementation. Not all the listed settings need adjusting, some are mentioned to help you understand how AEM operates. 

>[!CAUTION]
>
><p>The list is intended to act as a guideline and is not exhaustive. Not all bundles are listed, nor all parameters for some of the bundles that are.</p> <p>The configuration necessary will vary from project to project.</p> <p>Please see the Web console for values used and detailed information about parameters.</p> 

>[!NOTE]
>
><p>The <a href="http://www.aemstuff.com/osgi.html">AEM OSGi Config Details</a> tool can be used to list the default OSGi configurations.<br> </p> 

>[!NOTE]
>
><p>Further bundles may be required for specific areas of functionality within AEM. In these cases, configuration details can be found on the page related to the appropriate functionality. &nbsp;</p> 

>[!NOTE]
>
><p>This configuration should be made using the Felix Console as it is needed at startup - before the repository is available.<br> </p> 

>[!CAUTION]
>
><p>Be sure to configure the following:</p> <p><b>User Name</b> and <b>Password</b>, the credentials for accessing the Apache Felix Web Management Console itself.<br> The password must be changed after the initial installation to ensure the <a href="/content/docs/en/aem/6-3/deploy/security_checklist.html">security</a> of your instance.</p> 

>[!NOTE]
>
><p>This configuration should be made using the Felix Console as it is needed at startup - before the repository is available.<br> </p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html">Production Ready Mode</a>.</p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html" >Production Ready Mode</a>.<br> </p> 

>[!NOTE]
>
><p>The Apache Sling Referrer Filter is dependent on the installation of a quick fix package.<br> </p> 

>[!CAUTION]
>
><p>In particular these options must be configured in the repository.</p> <p>Otherwise changes made to <b>URL Mappings</b> using the Felix console might be overwritten by AEM upon the next startup.</p> 

>[!NOTE]
>
><p>In AEM 6.0 and earlier releases proxy was configured in Day Commons HTTP Client. As of AEM 6.1 and later releases the proxy configuration has moved to the &quot;Apache HTTP Components Proxy Configuration&quot; instead of the 'Day Commons HTTP Client' config.</p> 

>[!CAUTION]
>
><p>When changing the setting for either <b>Minify</b> or <b>Gzip</b> you will also need to delete the contents of <span class="code">/var/clientlibs</span>. This is a cached version of the clientlibs and will be rebuilt when next requested.</p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html">Production Ready Mode</a>.</p> 

>[!NOTE]
>
><p>Upon a standard installation the touch-optimized UI is the default UI.</p> 

>[!NOTE]
>
><p>This setting is automatically configured for production instances if you run AEM in <a href="/content/help/en/experience-manager/6-4/sites/administering/using/production-ready.html">Production Ready Mode</a>.</p> 

>[!CAUTION]
>
><p>This configuration will allow anonymous requests to the tracking service.</p> 

>[!NOTE]
>
><p>See <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/configuring.html#EnablingPageImpressions">Page Impressions</a> for more information.</p> 

>[!NOTE]
>
><p>See <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/configuring.html#EnablingPageImpressions">Page Impressions</a> for more information.</p>

**CQ Rewriter HTML Parser Factory**

Controls the HTML Parser for the CQ rewriter.

* **Additional Tags to Process** - You can add or remove HTML tags to be processed by the parser. By default, the following tags are processed: A,IMG,AREA,FORM,BASE,LINK,SCRIPT,BODY,HEAD.
* **Preserve Camel Case** - By default, the HTML parser converts attributes in camel case (e.g. eBay) to lower case (e.g. ebay). You can turn this off to preserve the camel case attributes. This is useful when using frontend frameworks such as Angular 2.

![](assets/chlimage_1.png) 
>[!NOTE]
>
><p>This feature is currently only enabled for AEM author instances.</p> 
