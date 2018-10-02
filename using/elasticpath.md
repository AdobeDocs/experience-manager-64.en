---
uuid: 92e347dd-5a38-440d-8551-1993acda07df
index: y
internal: n
snippet: y
translate: y
---

# Elastic Path

Deploying the necessary eCommerce packages provides the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with Elastic Path implementation (including a demonstration catalog).

This catalog is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site.

>[!NOTE]
>
><p>This page contains links to the&nbsp;<a href="http://www.elasticpath.com/">Elastic Path website</a>. Certain areas need an account for full access.</p>

### Installation of eCommerce with Elastic Path

To install AEM with an Elastic Path integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](deploy.md) and any other pre-requisite packages (see [https://docs.elasticpath.com/display/EP611DEV/System+Requirements](https://docs.elasticpath.com/display/EP611DEV/System+Requirements) for details).

1. Install the latest demonstration content packages using the [Package Manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager#PackageManager) in the following order:

    1. `ep-cortex-java-bindings`    
    1. `ep-aem-integration`    
    1. `cq-geometrixx-ep-content`

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

>[!NOTE]
>
><p>To be able to find and download those packages and the matching Elastic Path Commerce demo server, please&nbsp;<a href="http://www.elasticpath.com/company/contact-us">contact Elastic Path</a>.</p> <p>For additional details on Elastic Path for Adobe Marketing Cloud, please see&nbsp;<a href="http://cms-developers.elasticpath.com">http://cms-developers.elasticpath.com</a>.</p>

If Elastic Path is running on any other machine or server (as recommended for Production):

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Open `com.elasticpath.web.config.EPConfigurationHandler`.

1. Update the `cortex.url` to point to that machine in which Elastic Path is running.
   ![](assets/chlimage_1.png)

>[!CAUTION]
>
><p>Use of the Elastic Path server requires a separate Elastic Path license.</p> 
