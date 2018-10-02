---
uuid: e2f031ba-b921-4038-8229-20e01bf580d4
index: y
internal: n
snippet: y
translate: y
---

# IBM Websphere Commerce

Deploying the necessary eCommerce packages will provide the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with a IBM Websphere Commerce implementation (including a demonstration catalog).

This is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site.

>[!NOTE]
>
><p>To run the Geometrixx Outdoors store with WebSphere Commerce,&nbsp;<a href="/content/help/en/experience-manager/6-4/sites/deploying/using/setup.html">the Geometrixx Outdoors products and catalog data must be loaded into WebSphere Commerce</a>.</p>

### Technical Requirements

The IBM Websphere extension of the eCommerce Integration Framework has been made to support Websphere Commerce version 7 Feature Pack 8.

>[!NOTE]
>
><p>You will need Java 7.</p>

### Packages Needed for eCommerce with Websphere Commerce

To install eCommerce functionality you need:

* Your Websphere Commerce server.
* AEM eCommerce framework:

    * this is part of a standard AEM installation    
    * CQ Geometrixx Outdoors demo store (needs seperate package, as Geometrixx demos are not part of AEM 6.3 any more)

* AEM Websphere Commerce content packages, available through your [Daycare](http://daycare.day.com/home.html) account: ``

    * `cq-geometrixx-all-pkg-5.10.68`    
    * `cq-6.3.0-featurepack-6709`    
    * a reference implementation to illustrate use of Websphere Commerce ( `geometrixx-outdoors/en_US`)

### Installation of eCommerce with Websphere Commerce

To install AEM with a Websphere Commerce integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](deploy.md).

1. Install the demonstration content packages using the [package manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager):

    1. `cq-geometrixx-all-pkg`    
    1. `cq-6.3.0-featurepack-6709`

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

>[!NOTE]
>
><p>To download the packages, navigate to&nbsp;<a href="/content/help/en/experience-manager/6-4/sites/administering/using/package-manager.html#main-pars_title_3">Package Share</a>.</p>

AEM needs to be configured to connect to the WebSphere Commerce server instance, which is our demo WebSphere Commerce Server running the Geometrixx Outdoors eSite.

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Click **Adobe CQ Commerce - IBM WebSphere Commerce REST API client**.

1. Enter the **Websphere Commerce server host / ip **as required.

1. Click **Save**.

>[!CAUTION]
>
><p>Use of the Websphere Commerce server requires a separate license.</p> 
