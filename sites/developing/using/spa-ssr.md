---
title: SPA and Server-Side Rendering
seo-title: SPA and Server-Side Rendering
description: null
seo-description: null
uuid: 75bf3274-5d59-46a1-9d78-a9e79d4392a6
contentOwner: bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: spa
content-type: reference
discoiquuid: e8fb1977-bbf0-4437-93b1-e24f67b30de9
index: y
internal: n
snippet: y
---

# SPA and Server-Side Rendering{#spa-and-server-side-rendering}

>[!CAUTION]
>
>Although the Single-Page Application (SPA) Editor is available as part of the [We.Retail Journal](https://github.com/adobe/aem-sample-we-retail-journal) sample content (requires [AEM 6.4 service pack 2](/content/help/en/experience-manager/6-4/release-notes/sp-release-notes)), its server side rendering features as described in this document are still considered a technical preview, available for testing and feedback but not intended for production roll out.

## Overview {#overview}

Single page applications (SPAs) can offer the user a rich, dynamic experience that reacts and behaves in familiar ways, often just like a native application. [This is achieved by relying on the client to load the content up front and then do the heavy lifting of handling user interaction](../../developing/using/spa-walkthrough.md#main-pars-header-29566281) and thus minimizing the amount of communication needed between the client and the server, making the app more reactive.

However this can lead to longer initial load times, especially if the SPA is large and rich in its content. In order to optimize load times, some of the content can be rendered server-side. Using server side rendering (SSR) can accelerate the initial load of the page and then pass further rendering on to the client.

<!--
Comment Type: annotation
Last Modified By: fauchere
Last Modified Date: 2018-12-06T11:23:40.461-0500
In Gabriel's slides, there is a section about the importance of this initial load time over SEO
-->

## AEM-Driven Communication Flow {#aem-driven-communication-flow}

When using SSR, the [component interaction workflow](../../developing/using/spa-overview.md#main-pars-header-1731324886) of SPAs in AEM includes a phase in which the initial content of the app is generated on a Node.js server.

1. The browser requests the SSR content from AEM  

1. AEM posts the model to the Node.js server

1. The Node.js server returns the generated content  

1. AEM serves the HTML returned by the Node.js server via the HTL template of the backend page component.

![](assets/server-side-rendering-cms-drivenaemnode.png)

### Node.js-Driven Communication Flow {#node-js-driven-communication-flow}

The previous section describes the standard and recommended implementation of server side rendering with regards to SPAs in AEM, where AEM performs the bootstrapping and serving of content.

Alternatively, SSR can be implemented so that the Node.js server is responsible for the bootstrapping, effectively reversing the communication flow.

Both models are valid and supported by AEM. However, one should consider the advantages and disadvantages of each before implementing a particular model.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <th><strong>Bootstrapping</strong></th> 
   <th><strong>Advantages</strong></th> 
   <th><strong>Disadvantages</strong></th> 
  </tr>
  <tr>
   <th><strong>via AEM</strong><br /> </th> 
   <td>
    <ul> 
     <li>AEM manages injecting libraries where needed</li> 
     <li>Resources only need to be maintained on AEM<br /> </li> 
    </ul> </td> 
   <td>
    <ul> 
     <li>Possibly unfamiliar to SPA developer<br /> </li> 
    </ul> </td> 
  </tr>
  <tr>
   <th><strong>via Node.js</strong></th> 
   <td>
    <ul> 
     <li>More familiar to SPA developers<br /> </li> 
    </ul> </td> 
   <td>
    <ul> 
     <li>Clientlib resources required by the application such as CSS and JavaScript will need to be made available by the AEM developer via the <span class="code"><a href="../../developing/using/clientlibs.md#main-pars-title-8ced">allowProxy</a></span> property<br /> </li> 
     <li>Resources must be synched between AEM and the Node.js server</li> 
     <li>To enable authoring of the SPA, a proxy server for the Node.js instance may be necessary</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

## Planning for SSR {#planning-for-ssr}

Generally only part of an application needs to be rendered server side. The common example is the content that will be displayed above the fold on the initial load of the page is rendered server side. This saves time by delivering to the client, already rendered content. As the user interacts with the SPA, the additional content is rendered by the client.

As you consider implementing server side rendering for your SPA, you need to review for what parts of the app it will be necessary.

## Developing an SPA using SSR {#developing-an-spa-using-ssr}

SPA components could be rendered by the client (in the browser) or server side. When rendered server side, browser properties such as window size and location are not present. Therefore SPA components should be isomorphic, making no assumption about where they will be rendered.

To leverage SSR, you will need to deploy your code in AEM as well as on a Node.js server. Node.js is responsible for the server side rendering. Most of the code will be the same, however server-specific tasks will differ.

## SSR for SPAs in AEM {#ssr-for-spas-in-aem}

SSR for SPAs in AEM require a Node.js server, which is called for the rendering of the app content server side. Within the HTL of the app, a resource on the Node.js server is called to render the content.

Just as AEM supports the Angular and React SPA frameworks out-of-the box, server side rendering is also supported for Angular and React apps. See the NPM documentation for both frameworks for further details.

* React: [https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component](https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component)
* Angular: [https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component](https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component)

For a simplistic example, please refer to the [We.Retail Journal app](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail-journal). It renders the entire application server side. Although this is not a real-world example, it does illustrate what is needed to implement SSR.

>[!NOTE]
>
>Adobe recommends a separate Node.js instance for every AEM environment (author, publish, stage, etc.).

