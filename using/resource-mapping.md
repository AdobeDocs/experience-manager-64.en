---
uuid: 9aa9ff60-0579-4e39-b609-15fa5a21aada
index: y
internal: n
snippet: y
translate: y
---

# Resource Mapping

Resource mapping is used to define redirects, vanity URLs and virtual hosts for AEM.

For example, you can use these mappings to:

* Prefix all requests with `/content` so that the internal structure is hidden from the visitors to your website.
* Define a redirect so that all requests to the `/content/en/gateway` page of your website are redirected to `http://gbiv.com/`.

One possible HTTP mapping [prefixes all requests to `localhost:4503` with `/content`](#Configuringaninternalredirecttocontent). A mapping like this could be used to hide the internal structure from the visitors to the website as it allows:

`localhost:4503/content/geometrixx/en/products.html`

to be accessed using:

`localhost:4503/geometrixx/en/products.html`

as the mapping will automatically add the prefix `/content` to `/geometrixx/en/products.html`.

>[!CAUTION]
>
><p>Vanity URLs do not support regex patterns.</p> 

>[!NOTE]
>
><p>See the Sling documentation, and <a href="http://sling.apache.org/site/resources.html">Mappings for Resource Resolution</a> and <a href="http://sling.apache.org/site/mappings-for-resource-resolution.html">Resources</a> for further information.<br> </p>

### Viewing Mapping Definitions

The mappings form two lists that the JCR Resource Resolver evaluates (top-down) to find a match.

These lists can be viewed (together with configuration information) under the **JCR ResourceResolver** option of the Felix console; for example, `http://<*host*>:<*port*>/system/console/jcrresolver`:

* Configuration Shows the current configuration (as defined for the [Apache Sling Resource Resolver](osgi-configuration-settings.md#ApacheSlingResourceResolver)).
* Configuration Test This allows you to enter a URL or resource path. Click **Resolve** or **Map** to confirm how the system will transform the entry.
* **Resolver Map Entries** The list of entries used by the ResourceResolver.resolve methods to map URLs to Resources.
* **Mapping Map Entries** The list of entries used by the ResourceResolver.map methods to map Resource Paths to URLs.

The two lists show various entries, including those defined as defaults by the application(s). These often aim to simplify URLs for the user.

The lists pair a **Pattern**, a regular expression matched to the request, with a **Replacement** that defines the redirection to impose.

For example, the:

**Pattern ** `^[^/]+/[^/]+/welcome$`

will trigger the:

**Replacement** `/libs/cq/core/content/welcome.html`.

to redirect a request:

`http://localhost:4503/welcome` ``

to:

`http://localhost:4503/libs/cq/core/content/welcome.html`

New mapping definitions are created within the repository. 

>[!NOTE]
>
><p>There are many resources available that help explain how to define regular expressions; for example <a href="http://www.regular-expressions.info/">http://www.regular-expressions.info/</a>.<br> </p>

### Creating Mapping Definitions in AEM

In a standard installation of AEM you can find the folder:

`/etc/map/http`

This is the structure used when defining mappings for the HTTP protocol. Other folders ( `sling:Folder`) can be created under `/etc/map` for any other protocols that you want to map.

#### Configuring an Internal Redirect to /content

To create the mapping that prefixes any request to http://localhost:4503/ with `/content`:

1. Using CRXDE navigate to `/etc/map/http`.
1. Create a new node:

    * **Type** `sling:Mapping` This node type is intended for such mappings, though its use is not mandatory.    
    * **Name** `localhost_any`

1. Click **Save All**.
1. **Add** the following properties to this node:

    * **Name** `sling:match`

        * **Type** `String`        
        * **Value** `localhost.4503/`

    * **Name** `sling:internalRedirect`

        * **Type** `String`        
        * **Value** `/content/`

1. Click **Save All**.

This will handle a request such as: `localhost:4503/geometrixx/en/products.html` as if: `localhost:4503/content/geometrixx/en/products.html` had been requested.

>[!NOTE]
>
><p>See <a href="http://sling.apache.org/site/mappings-for-resource-resolution.html">Resources</a> in the Sling Documentation for further information about the sling properties available and how they can be configured.<br> </p> 

>[!NOTE]
>
><p>You can use <span class="code">/etc/map.publish</span> to hold the configurations for the publish environment. These must then be replicated, and the new location (<span class="code">/etc/map.publish</span>) configured for the <b>Mapping Location</b> of the <a href="/content/help/en/experience-manager/6-4/sites/deploying/using/osgi-configuration-settings.html#ApacheSlingResourceResolver">Apache Sling Resource Resolver</a> of the publish environment.</p> 
