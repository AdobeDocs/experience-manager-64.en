---
title: E-Commerce Repository Restructuring in AEM 6.4
seo-title: E-Commerce Repository Restructuring in AEM 6.4
description: Learn how to make the necessary changes in order to migrate to the new repository structure in AEM 6.4 for E-Commerce.
seo-description: Learn how to make the necessary changes in order to migrate to the new repository structure in AEM 6.4 for E-Commerce.
uuid: 0e2abaa9-b96d-4184-98bf-958daa344d72
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: 7d5555ca-15a6-4160-9f4e-52fdadff0f38
index: y
internal: n
snippet: y
---

# E-Commerce Repository Restructuring in AEM 6.4{#e-commerce-repository-restructuring-in-aem}

As described on the parent [Repository Restructuring in AEM 6.4](../../../sites/deploying/using/repository-restructuring.md) page, customers upgrading to AEM 6.4 should use this page to assess the work effort associated with repository changes impacting the AEM E-Commerce Solution. Some changes require work effort during the AEM 6.4 upgrade process, while others can be deferred until a 6.5 upgrade.

## With 6.4 Upgrade {#with-upgrade}

### Product, Order, Collections, Classifications, Shipping Methods and Payment Methods Data {#product-order-collections-classifications-shipping-methods-and-payment-methods-data}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Previous location</strong></td> 
   <td><p><span class="code">/etc/commerce/products</span></p> <p><span class="code">/etc/commerce/orders</span></p> <p><span class="code">/etc/commerce/collections</span></p> <p><span class="code">/etc/commerce/classifications</span></p> <p><span class="code">/etc/commerce/shipping-methods</span></p> <p><span class="code">/etc/commerce/payment-methods</span></p> </td> 
  </tr>
  <tr>
   <td><strong>New location(s)</strong></td> 
   <td><p><span class="code">/var/commerce/products</span></p> <p><span class="code">/var/commerce/orders</span></p> <p><span class="code">/var/commerce/collections</span></p> <p><span class="code">/var/commerce/classifications</span></p> <p><span class="code">/var/commerce/shipping-methods</span></p> <p><span class="code">/var/commerce/payment-methods</span></p> </td> 
  </tr>
  <tr>
   <td><strong>Restructuring guidance</strong></td> 
   <td><p>You can use a <a href="../../../sites/deploying/using/lazy-content-migration.md" target="_blank">Lazy Migration</a> task to migrate E-Commerce data.</p> <p>It performs the following steps:</p> 
    <ul> 
     <li>adjusts references to old location to point to new location</li> 
     <li>moves content from old location to new location</li> 
     <li>removes old location to eventually activate the usage of new location in the whole system</li> 
    </ul> <p>The locations covered by the task are:</p> 
    <ul> 
     <li>/etc/commerce/products</li> 
     <li>/etc/commerce/collections<br /> </li> 
     <li>/etc/commerce/orders<br /> </li> 
     <li>/etc/commerce/payment-methods<br /> </li> 
     <li>/etc/commerce/shipping-methods<br /> </li> 
    </ul> <p>For larger catalogs it is recommanded to run the commerce migration task individually by passing the following Java system property to AEM:</p> <p><span class="code">propertyname: com.adobe.upgrade.forcemigration</span></p> <p><span class="code">property value: com.day.cq.compat.codeupgrade.impl.cq64.CQ64CommerceMigrationTask</span></p> <p>After migration AEM needs a restart.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr>
 </tbody>
</table>

