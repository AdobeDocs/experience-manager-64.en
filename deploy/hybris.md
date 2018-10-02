---
uuid: df91d55a-7f34-479b-930d-1ef267431c26
index: y
internal: n
snippet: y
translate: y
---

# hybris

>[!NOTE]
>
><p>This page contains links to the hybris website. For certain pages you will need an account to login.</p>

---

## Deploying eCommerce with hybris

>[!NOTE]
>
><p>The following procedures use the following demonstration catalog to illustrate the deployment:</p> <p><span class="code">&nbsp;&nbsp;&nbsp;&nbsp;Geometrixx Outdoors Site English (US)</span> &nbsp;</p>

Deploying the [necessary eCommerce packages](#PackagesNeededforeCommercewithhybris) will provide the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with a hybris implementation (including a demonstration catalog)

This is available under the English (US) branch ( `/content/geometrixx-outdoors/en_US`) of the Geometrixx Outdoors site:

* [Product Information](#ProductInformationwithColorVariants) (with color variants when appropriate)
* [Shopping Cart content overviews](#ShoppingCartContentOverview)
* [Customer Sign-Up](#CustomerSignUp) and [Customer Sign-In](#CustomerSignIn)
* [Access to the hybris management console](#Accesstothehybrismanagementconsole)

### Technical Requirements - hybris Server

The hybris extension of the eCommerce Integration Framework has been updated to support Hybris 5 (as default), while maintaining backward compatibility with [Hybris 4](/content/help/en/experience-manager/6-4/sites/developing/using/hybris#Developingforhybris4).

>[!NOTE]
>
><ul> <li>Supports up to hybris 6.4 with OCC version 2.</li> <li>You will need Java 7 to run the <a href="http://www.hybris.com/en/architecture-technology">hybris 5 server.</a></li> <li>The hybris add-on, the <a href="http://www.hybris.com/en/products/telecommunication">Telco Accelerator</a>, is not supported by the AEM extension.</li> </ul>

### Packages Needed for eCommerce with hybris

To install eCommerce functionality you need:

* Your hybris server, available from [hybris](#ConfigureandBuildthehybrisServer).
* AEM eCommerce framework:

    * this is part of a standard AEM installation

* AEM Geometrixx-all package:

    * `cq-geometrixx-all-pkg`

* AEM hybris content packages: ``

    * `cq-hybris-content-6.3.2`    
    * hybris-specific API implementation    
    * `cq-geometrixx-hybris-content-6.3.2`    
    * a reference implementation to illustrate use of hybris ( `geometrixx-outdoors/en_US`)

### Installation of eCommerce with hybris

To install a fully-fledged configuration (using the demonstration catalog, Geometrixx Outdoors) the basic steps are:

1. [Install AEM](deploy.md).
1. Install the Geometrixx-all package

    1. ` [cq-geometrixx-all-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq60/product/cq-geometrixx-all-pkg)`

1. Install the demonstration content packages using the [package manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager):

    1. ` [cq-hybris-content-6.3.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/cq-hybris-content)`    
    1. ` [cq-geometrixx-hybris-content-6.3.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/cq-geometrixx-hybris-content)`

1. [Download and build your hybris Server](#DownloadandBuildyourhybrisServer).
1. Construct your catalog in your eCommerce engine:

    1. [Setup the Geometrixx Outdoor Store](#SetuptheGeometrixxOutdoorsStore).

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

>[!CAUTION]
>
><p>Use of the hybris server requires a separate hybris license.</p> 

>[!NOTE]
>
><p>For developers <a href="/content/help/en/experience-manager/6-4/sites/developing/using/ecommerce.html#APIDocumentation">API documentation</a> is also available for download.<br /> </p>

### Download and Build your hybris Server

The steps in this procedure will download and build the hybris server. It will also make the initial configurations required for the connections between hybris and cq. The extension will then be usable with the default settings.

>[!CAUTION]
>
><p>Hybris versions earlier than 5.5.1 are not supported.</p> 

>[!NOTE]
>
><p>To complete this, you will need <a href="http://groovy-lang.org/">Groovy</a> installed on your system.</p>

1. Download the **hybris Commerce Suite **distribution from the hybris download site.

   >[!CAUTION]
   >
   ><p>You will need an account (from hybris) to access this.</p> 

1. Unzip the distribution file to the required location (referred as &lt;hybris-root-directory&gt;).

1. From the command line, execute the following:

   ```shell
   cd <hybris-root-directory>/bin/platform
   . ./setantenv.sh
   ant clean all 
   cd ../..
   ```

   >[!NOTE]
   >
   ><p>When executing:</p> <p><span class="code">&nbsp;&nbsp;&nbsp; ant clean all</span></p> <p>Press <span class="code">Return</span> when required.</p> 

1. Download the following files to the root folder of your extracted hybris distribution, ` <*hybris-root-directory*>`:

   >[!NOTE]
   >
   ><p>For hybris 5.6.0 and later, please use the following setup.groovy.</p> 

1. From the command line, execute the following to:

    * update the configuration of the hybris server (as required by the extension)    
    * rebuild the hybris server with the modified configuration    
    * start the server

   ```shell
   groovy setup.groovy
   cd bin/platform
   ant clean all
   sh hybrisserver.sh
   ```

   >[!NOTE]
   >
   ><p>Dependent on your system, several of these steps might take several minutes to complete.</p> 

1. In your browser, navigate to the **hybris administration console** at:

   [http://localhost:9002](http://localhost:9002) 

1. Click **Initialize** and then confirm the initialization action (as it will delete existing data).

   The progress will be shown on the console, with `FINISHED` indicating completion.

   >[!NOTE]
   >
   ><p>Dependent on your system, this might take several minutes to complete.</p>

### Setup the Geometrixx Outdoors Store

This procedure will upload and configure the demonstration store - Geometrixx Online.

1. Start your hybris instance. From the command line, execute the following:

   ```shell
   cd <hybris-root-directory>/bin/platform
   sh hybrisserver.sh
   ```

1. In your browser, navigate to the **hybris management console** at:

   [http://localhost:9002/hmc/hybris](http://localhost:9002/hmc/hybris)

1. From the sidebar navigation, expland **System** and **Tools**. Then select **Import** to open the **Wizard: CSV Import** window.

1. In the **Configuration** tab, **Upload** the following **Import file**:

1. Set the **Locale Setting** to:

   `en_US - English (United States)`

1. Open the **Resources** tab.

1. **Upload** the following **Media-Zip**:

1. Click **Start** to import the specified files. The **Result** tab will show any log entries. 

1. Click **Done** to close the import window. 

1. From the sidebar, select **System**, then **Tools**, then **Import**. 

1. **Upload** the following **Import file**:

   For hybris 5.7, please use the following:

1. Set the **Locale Setting** to:

   `en_US - English (United States)`

1. Click **Start** to import the specified files. The **Result** tab will show any log entries. 

1. Click **Done** to close the import window. 

1. You can now use the product cockpit to view the imported catalogs and products:

   [http://localhost:9002/productcockpit](http://localhost:9002/productcockpit)

