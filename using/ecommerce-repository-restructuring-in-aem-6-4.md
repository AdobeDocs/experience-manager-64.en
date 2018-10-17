---
title: E-Commerce Repository Restructuring in AEM 6.4
seo-title: E-Commerce Repository Restructuring in AEM 6.4
description: null
seo-description: Learn how to make the necessary changes in order to migrate to the new repository structure in AEM 6.4 for E-Commerce.
uuid: b94212fc-f9ab-4a93-9833-b2c1a4ad9bae
content-encoding: ISO-8859-1
acrolinxstatus: not_checked
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/ecommerce-repository-restructuring-in-aem-6-4
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-07-27T04 43 28.438-0400
cq-lastmodifiedby: reference-adjustment-service
cq-lastreplicated: 2018-07-27T04 43 28.746-0400
cq-lastreplicatedby: sarchiz
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
cq-template: /apps/help/templates/article-3
discoiquuid: 9c32bcf0-b106-4130-a399-0b113e2e0dd7
donotlocalize: false
firstPublishExternalDate: 2018-07-27T04:43:28.415-0400
herogradient: light
jcr-created: 2018-07-12T07 29 36.518-0400
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-07-27T04:43:28.415-0400
lr-lastreplicatedby: sarchiz@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/repo_restructuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/repo_restructuring
pagecreatedat: en
pagelayout: video
publishexternaldate: 2018-07-27T04 43 28.415-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/ecommerce-repository-restructuring-in-aem-6-4.html
sha1: c14002d3d82cbbaf0882a3c7ee59e47b22cd01e2
sidecolumn: left
topicBrowsingSortDate: 2018-07-27T04:43:28.415-0400
index: y
internal: n
snippet: y
---

# E-Commerce Repository Restructuring in AEM 6.4

As described on the parent [Repository Restructuring in AEM 6.4](repository-restructuring.md) page, customers upgrading to AEM 6.4 should use this page to assess the work effort associated with repository changes impacting the AEM E-Commerce Solution. Some changes require work effort during the AEM 6.4 upgrade process, while others can be deferred until a 6.5 upgrade.

## With 6.4 Upgrade

### Product, Order, Collections, Classifications, Shipping Methods and Payment Methods Data

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
   <td><p>You can use a <a href="lazy-content-migration.md" target="_blank">Lazy Migration</a> task to migrate E-Commerce data.</p> <p>It performs the following steps:</p> 
    <ul> 
     <li>adjusts references to old location topointtonewlocation</li> 
     <li>moves content from old location to new location</li> 
     <li>removes old location to eventually activate theusageofnewlocationinthe whole system</li> 
    </ul> <p>The locations covered by the task are:</p> 
    <ul> 
     <li>/etc/commerce/products</li> 
     <li>/etc/commerce/collections<br /> </li> 
     <li>/etc/commerce/orders<br /> </li> 
     <li>/etc/commerce/payment-methods<br /> </li> 
     <li>/etc/commerce/shipping-methods<br /> </li> 
    </ul> <p>For larger catalogs it is recommanded to run the commerce migration task individually by passing the following Java system property to AEM:</p> <p><span class="code">proeprtyname: com.adobe.upgrade.forcemigration</span></p> <p><span class="code">property value: com.day.cq.compat.codeupgrade.impl.cq64.CQ64CommerceMigrationTask</span></p> <p>After migration AEM needs a restart.</p> </td> 
  </tr>
  <tr>
   <td><strong>Notes</strong></td> 
   <td>N/A<br /> </td> 
  </tr>
 </tbody>
</table>

