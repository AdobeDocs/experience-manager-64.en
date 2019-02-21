---
title: The CSRF Protection Framework
seo-title: The CSRF Protection Framework
description: The framework makes use of tokens to guarantee that the client request is legitimate
seo-description: The framework makes use of tokens to guarantee that the client request is legitimate
uuid: 5eb021de-71e1-40c4-8175-cf434cd7a33c
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 55ab2d15-1115-467a-8752-60f11ac279a7
index: y
internal: n
snippet: y
---

# The CSRF Protection Framework{#the-csrf-protection-framework}

In addition to the Apache Sling Referrer Filter, Adobe also provides a new CSRF Protection Framework to protect against this type of attack.

The framework makes use of tokens to guarantee that the client request is legitimate. The tokens are generated when the form is sent to the client and validated when the form is sent back to the server.

>[!NOTE]
>
>There are no tokens on the publish instances for anonymous users.

### Requirements {#requirements}

**Dependencies**

Any component that relies on the `granite.jquery` dependency will benefit from the CSRF Protection Framework automatically. If this is not the case for any of your components, you must declare a dependency to `granite.csrf.standalone` before you can use the framework.

**Replicating the Crypto Key**

In order to make use of the tokens, you need to replicate the `/etc/keys/hmac` binary to all of the instances in your deployment. A convenient way to copy the HMAC key to all the instances is to create a package containing the key and install it via the Package Manager on all the instances.

<!--
Comment Type: draft

<p>If <a href="../../../sites/administering/using/saml-2-0-authenticationhandler.md">SAML</a> is configured, be sure to exclude the <span class="code">saml </span>node from the package.</p>
<p>Specify the package filter as </p>
<ul>
<li><strong>Root path</strong> : <span class="code">/etc/key</span></li>
<li><strong>Rules</strong> : <span class="code">exclude | /etc/key/saml</span></li>
</ul>
-->

>[!NOTE]
>
>Make sure you also make the necessary [Dispatcher configuration changes](/content/help/en/experience-manager/dispatcher/user-guide) in order to use the CSRF Protection Framework.

<!--
Comment Type: draft

<h4>Whitelisting User Agents</h4>
-->

<!--
Comment Type: draft

<p>You also have the option to whitelist user agents for cases like automation where it might be impractical to embed the CSRF Filter.</p>
<p>All the whitelisted user agents will be considered safe by the CSRF Protection Framework. You can enable whitelisting by following the below procedure:</p>
<ol>
<li>Go to the Web Console at http://&lt;serveraddress:port&gt;/system/console/configMgr</li>
<li>Look for and click the <strong>Adobe Granite CSRF Filter</strong> service.</li>
<li>Add the user agent to the <strong>Safe User Agents</strong> list and click Save.</li>
</ol>
-->

>[!NOTE]
>
>If you use the manifest cache with your web application, make sure you add "**&#42;**" to the manifest in order to make sure the token does not take the CSRF token generation call offline. For more information, consult this [link](http://www.w3.org/TR/offline-webapps/).
>
>For more information on CSRF attacks and ways to mitigate them, see the [Cross-Site Request Forgery OWASP page](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_%28CSRF%29).

