---
title: Using Sling Adapters
seo-title: Using Sling Adapters
description: Sling offers an Adapter pattern to conveniently translate objects that implement the Adaptable interface
seo-description: Sling offers an Adapter pattern to conveniently translate objects that implement the Adaptable interface
uuid: 274eb477-227c-413b-b5db-76f19ed2ce66
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 4e865081-39c9-43f1-b95f-aca5da8be758
index: y
internal: n
snippet: y
---

# Using Sling Adapters{#using-sling-adapters}

[Sling](http://sling.apache.org) offers an [Adapter pattern](http://sling.apache.org/site/adapters.html) to conveniently translate objects that implement the [Adaptable](http://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/Adaptable.html#adaptTo%28java.lang.Class%29) interface. This interface provides a generic [adaptTo()](http://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/Adaptable.html#adaptTo%28java.lang.Class%29) method that will translate the object to the class type being passed as the argument.

For example to translate a Resource object to the corresponding Node object, you can simply do:

```java
Node node = resource.adaptTo(Node.class);
```

### Use Cases {#use-cases}

There are the following use cases:

* Get implementation-specific objects.  
  For example, a JCR-based implementation of the generic [ `Resource`](http://sling.apache.org/apidocs/sling5/org/apache/sling/api/resource/Resource.html) interface provides access to the underlying JCR ` [Node](http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html).`

* Shortcut creation of objects that require internal context objects to be passed.  
  For example, the JCR-based [ `ResourceResolver`](http://sling.apache.org/apidocs/sling5/org/apache/sling/api/resource/ResourceResolver.html) holds a reference to the request's [ `JCR Session`](http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Session.html), which in turn is needed for many objects that will work based on that request session, such as the ` [PageManager](/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager.md)` or [ `UserManager`](/sites/developing/using/reference-materials/javadoc/com/day/cq/security/UserManager.md).

* Shortcut to services.  
  A rare case - `sling.getService()` is simple as well.

### Null Return Value {#null-return-value}

`adaptTo()` can return null.

There are various reasons for this, including:

* the implementation does not support the target type
* an adapter factory handling this case is not active (eg. due to missing service references)
* internal condition failed
* service is not available

It is important that you handle the null case gracefully. For jsp renderings it might be acceptable to have the jsp fail if that will result in an empty piece of content.

### Caching {#caching}

To improve performance, implementations are free to cache the object returned from a `obj.adaptTo()` call. If the `obj` is the same, the returned object is the same.

This caching is performed for all `AdapterFactory` based cases.

However, there is no general rule - the object could be either a new instance or an existing one. This means that you cannot rely on either behavior. Hence it is important, especially inside `AdapterFactory`, that objects are reusable in this scenario.

### How it works {#how-it-works}

There are various ways that `Adaptable.adaptTo()` can be implemented:

* By the object itself; implementing the method itself and mapping to certain objects.
* By an ` [AdapterFactory](http://sling.apache.org/apidocs/sling5/org/apache/sling/api/adapter/AdapterFactory.html)`, which can map arbitrary objects.  
  The objects must still implement the `Adaptable` interface and must extend ` [SlingAdaptable](/sites/developing/using/reference-materials/javadoc/org/apache/sling/adapter/SlingAdaptable.md)` (which passes the `adaptTo` call to a central adapter manager).  
  This allows hooks into the `adaptTo` mechanism for existing classes, such as `Resource`.

* A combination of both.

For the first case, the javadocs can state what `adaptTo-targets` are possible. However, for specific subclasses such as the JCR-based Resource, often this is not possible. In the latter case, implementations of `AdapterFactory` are typically part of the private classes of a bundle and thus not exposed in a client API, nor listed in javadocs. Theoretically, it would be possible to access all `AdapterFactory` implementations from the [OSGi](../../../sites/deploying/using/configuring-osgi.md) service runtime and look at their "adaptables" (sources and targets) configurations, but not to map them to each other. In the end, this depends on the internal logic, which must be documented. Hence this reference.

## Reference {#reference}

#### Sling {#sling}

[**Resource**](/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.md) adapts to:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td width="120"><a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Node</a></td> 
   <td>If this is a JCR-node-based resource or a JCR property referencing a node.</td> 
  </tr> 
  <tr> 
   <td><a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Property.html">Property</a></td> 
   <td>If this is a JCR-property-based resource.</td> 
  </tr> 
  <tr> 
   <td><a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Item.html">Item</a></td> 
   <td>If this is a JCR-based resource (node or property).</td> 
  </tr> 
  <tr> 
   <td><a href="http://java.sun.com/j2se/1.5.0/docs/api//java/util/Map.html">Map</a></td> 
   <td>Returns a map of the properties, if this is a JCR-node-based resource (or other resource supporting value maps).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ValueMap.md">ValueMap</a></td> 
   <td>Returns a convenient-to-use map of the properties, if this is a JCR-node-based resource (or other resource supporting value maps). Can also be achieved (more simply) by using<br /> <span class="code"><a href="/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ResourceUtil.md#getvaluemap%28org.apache.sling.api.resource.resource%29">ResourceUtil.getValueMap(Resource)</a></span> (handles null case, etc.).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/inherit/InheritanceValueMap.md">InheritanceValueMap</a></td> 
   <td>Extension of <a href="/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ValueMap.md" title="interface in org.apache.sling.api.resource">ValueMap</a> which allows the hierarchy of resources to be taken into account when looking for properties.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/PersistableValueMap.md">PersistableValueMap</a></td> 
   <td>If this is a JCR-node-based resource and the user has permissions to modify properties on that node.<br /> Note: multiple persistable maps do not share their values.</td> 
  </tr> 
  <tr> 
   <td><a href="http://java.sun.com/j2se/1.5.0/docs/api/java/io/InputStream.html">InputStream</a></td> 
   <td>Returns the binary content of a "file"<span class="code"></span> resource (if this is a JCR-node-based resource and the node type is <span class="code">nt:file</span> or <span class="code">nt:resource</span>; if this is a bundle resource; file content if this is a file system resource) or the data of a binary JCR property<br /> resource.</td> 
  </tr> 
  <tr> 
   <td><a href="http://java.sun.com/j2se/1.5.0/docs/api/java/net/URL.html">URL</a></td> 
   <td>Returns a URL to the resource (repository URL of this node if this is a JCR-node-based resource; jar bundle URL if this is a bundle resource; file URL if this is a file system resource).</td> 
  </tr> 
  <tr> 
   <td><a href="http://java.sun.com/j2se/1.5.0/docs/api/java/io/File.html">File</a></td> 
   <td>If this is a file system resource.</td> 
  </tr> 
  <tr> 
   <td><a href="http://sling.apache.org/apidocs/sling5/org/apache/sling/api/scripting/SlingScript.html">SlingScript</a></td> 
   <td>If this resource is a script (e.g. jsp file) for which a script engine is registered with sling.</td> 
  </tr> 
  <tr> 
   <td><a href="http://java.sun.com/products/servlet/2.2/javadoc/javax/servlet/Servlet.html">Servlet</a></td> 
   <td>If this resource is a script (e.g. jsp file) for which a script engine is registered with sling or if this is a servlet resource.</td> 
  </tr> 
  <tr> 
   <td><a href="http://jackrabbit.apache.org/api/2.8/org/apache/jackrabbit/api/security/user/Authorizable.html">Authorizable</a><br /> (Jackrabbit)<br /> </td> 
   <td>If this is a an authorizable resource (from the<br /> <span class="code">AuthorizableResourceProvider</span> in <span class="code">org.apache.sling.jackrabbit.usermanager</span>, under <span class="code">/system/userManager</span>).</td> 
  </tr> 
  <tr> 
   <td><a href="http://java.sun.com/j2se/1.5.0/docs/api/java/lang/String.html">String</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Boolean.html">Boolean</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Long.html">Long</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Double.html">Double</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/util/Calendar.html">Calendar</a><br /> <a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Value.html">Value</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/lang/String.html">String[]</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Boolean.html">Boolean[]</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/lang/Long.html">Long[]</a><br /> <a href="http://java.sun.com/j2se/1.5.0/docs/api/java/util/Calendar.html">Calendar[]</a><br /> <a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Value.html">Value[]</a></td> 
   <td>Returns the value(s) if this is a JCR-property-based resource (and the value fits).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.md">LabeledResource</a></td> 
   <td>If this is a JCR-node-based resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Page.md">Page</a></td> 
   <td>If this is a JCR-node-based resource and the node is a <span class="code">cq:Page</span> (or <span class="code">cq:PseudoPage</span>).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/components/Component.md">Component</a></td> 
   <td>If this is a <span class="code">cq:Component</span> node resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/designer/Design.md">Design</a></td> 
   <td>If this is a design node (<span class="code">cq:Page</span>, typically under<br /> /etc/designs).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Template.md">Template</a></td> 
   <td>If this is a <span class="code">cq:Template</span> node resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/msm/Blueprint.md">Blueprint</a></td> 
   <td>If this is a <span class="code">cq:Page</span> node resource (more specific checks possible in the future).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/Asset.md">Asset</a></td> 
   <td>If this is a dam:Asset node resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/Rendition.md">Rendition</a></td> 
   <td>If this is a dam:Asset rendition (nt:file under the rendition folder of a dam:Assert)</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/tagging/Tag.md">Tag</a></td> 
   <td>If this is a <span class="code">cq:Tag</span> node resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/preferences/Preferences.md">Preferences</a></td> 
   <td>If this is a <span class="code">cq:Preferences</span> node resource for a valid user/group.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/security/profile/Profile.md">Profile</a></td> 
   <td>If this is the profile below a user/group node (eg.<br /> cq/security/components/profile).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/security/UserManager.md">UserManager</a></td> 
   <td>Based on the JCR session if this is a JCR-based resource and the user has permissions to access the UserManager.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/security/Authorizable.md">Authorizable</a><br /> (cq-security)</td> 
   <td>This is a authorizable home node.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/security/User.md">User</a><br /> (cq-security)</td> 
   <td>If this is a user home node.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/security/privileges/PrivilegeManager.md">PrivilegeManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/search/SimpleSearch.md">SimpleSearch</a></td> 
   <td>Searches below the resource (or use setSearchIn()) if this is a JCR-based resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/workflow/status/WorkflowStatus.md">WorkflowStatus</a></td> 
   <td>Workflow status for the given page/workflow payload node.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/replication/ReplicationStatus.md">ReplicationStatus</a></td> 
   <td>Replication status for the given resource or its jcr:content subnode (checked first).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/connector/ConnectorResource.md">ConnectorResource</a></td> 
   <td>Returns an adapted connector resource for certain types, if this is a JCR-node-based resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/contentsync/config/package-summary.md">Config</a></td> 
   <td>If this is a <span class="code">cq:ContentSyncConfig</span> node resource.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/contentsync/config/package-summary.md">ConfigEntry</a></td> 
   <td>If this is below a <span class="code">cq:ContentSyncConfig</span> node resource.</td> 
  </tr> 
 </tbody> 
</table>

[**ResourceResolver**](/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/ResourceResolver.md) adapts to:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td width="120"><a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Session.html">Session</a></td> 
   <td>The request's JCR session, if this is a JCR-based resource resolver (default).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager.md">PageManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/components/ComponentManager.md">ComponentManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/designer/Designer.md">Designer</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/AssetManager.md">AssetManager</a></td> 
   <td>Based on the JCR session, if this is a JCR-based resource resolver.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/tagging/TagManager.md">TagManager</a></td> 
   <td>Based on the JCR session, if this is a JCR-based resource resolver.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/security/UserManager.md">UserManager</a></td> 
   <td>Based on the JCR session, if this is a JCR-based resource resolver, and if the user has permissions to access the UserManager.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/org/apache/jackrabbit/api/security/user/Authorizable.md">Authorizable</a> </td> 
   <td>The current user.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/org/apache/jackrabbit/api/security/user/User.md">User</a><br /> </td> 
   <td>The current user.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/security/privileges/PrivilegeManager.md">PrivilegeManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/preferences/Preferences.md">Preferences</a></td> 
   <td>Preferences of the current user (based on JCR session if this is a JCR-based resource resolver).</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/preferences/PreferencesService.md">PreferencesService</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/auth/pin/PinManager.md">PinManager</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/search/QueryBuilder.md">QueryBuilder</a></td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.md">Externalizer</a></td> 
   <td>For externalizing absolute URLs, even with out the request object.<br /> </td> 
  </tr> 
 </tbody> 
</table>

[**SlingHttpServletRequest**](/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/SlingHttpServletRequest.md) adapts to:

No targets yet, but implements Adaptable and could be used as source in a custom AdapterFactory.

[**SlingHttpServletResponse**](/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/SlingHttpServletResponse.md) adapts to:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td width="120"><a href="http://java.sun.com/j2se/1.5.0/docs/api/org/xml/sax/ContentHandler.html">ContentHandler</a><br /> (XML)</td> 
   <td>If this is a sling rewriter response.</td> 
  </tr> 
 </tbody> 
</table>

#### WCM {#wcm}

[**Page**](/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Page.md) adapts to:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td width="120"><a href="/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.md">Resource</a><br /> </td> 
   <td>Resource of the page.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.md">LabeledResource</a></td> 
   <td>Labeled resource (== this).</td> 
  </tr> 
  <tr> 
   <td><a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Node</a></td> 
   <td>Node of the page.</td> 
  </tr> 
  <tr> 
   <td>...</td> 
   <td>Everything that the page's resource can be adapted to.</td> 
  </tr> 
 </tbody> 
</table>

[**Component**](/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/components/Component.md) adapts to:

| [Resource](/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.md) |Resource of the component. |
|---|---|
| [LabeledResource](/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.md) |Labeled resource (== this). |
| [Node](http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) |Node of the component. |
| ... |Everything that the component's resource can be adapted to. |

[**Template**](/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/Template.md) adapts to:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td width="120"><a href="/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.md">Resource</a><a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html"><br /> </a></td> 
   <td>Resource of the template.</td> 
  </tr> 
  <tr> 
   <td><a href="/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/LabeledResource.md">LabeledResource</a></td> 
   <td>Labeled resource (== this).</td> 
  </tr> 
  <tr> 
   <td><a href="http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html">Node</a></td> 
   <td>Node of this template.</td> 
  </tr> 
  <tr> 
   <td>...</td> 
   <td>Everything that the template's resource can be adapted to.</td> 
  </tr> 
 </tbody> 
</table>

#### Security {#security}

[**Authorizable**](/sites/developing/using/reference-materials/javadoc/com/day/cq/security/Authorizable.md), [**User**](/sites/developing/using/reference-materials/javadoc/com/day/cq/security/User.md) and [**Group**](/sites/developing/using/reference-materials/javadoc/com/day/cq/security/Group.md) adapt to:

| [Node](http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) |Returns the user/group home node. |
|---|---|
| [ReplicationStatus](/sites/developing/using/reference-materials/javadoc/com/day/cq/replication/ReplicationStatus.md) |Returns the replication status for the user/group home node. |

#### DAM {#dam}

[**Asset**](/sites/developing/using/reference-materials/javadoc/com/day/cq/dam/api/Asset.md) adapts to:

| [Resource](/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.md) |Resource of the asset. |
|---|---|
| [Node](http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) |Node of the asset. |
| ... |Everything that the asset's resource can be adapted to. |

#### Tagging {#tagging}

[**Tag**](/sites/developing/using/reference-materials/javadoc/com/day/cq/tagging/Tag.md) adapts to:

| [Resource](/sites/developing/using/reference-materials/javadoc/org/apache/sling/api/resource/Resource.md) |Resource of the tag. |
|---|---|
| [Node](http://www.day.com/maven/jsr170/javadocs/jcr-2.0/javax/jcr/Node.html) |Node of the tag. |
| ... |Everything that the tag's resource can be adapted to. |

#### Other {#other}

Furthermore Sling / JCR / OCM also provides an ` [AdapterFactory](http://sling.apache.org/site/adapters.html#Adapters-AdapterFactory)` for custom OCM ([Object Content Mapping](http://jackrabbit.apache.org/object-content-mapping.html)) objects.
