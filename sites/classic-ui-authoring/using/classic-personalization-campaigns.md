---
title: Campaign Management
seo-title: Campaign Management
description: null
seo-description: Campaign management provides digital marketers the opportunity to deliver personalized content and so create dedicated experiences for visitors. It allows you to orchestrate your marketing campaigns across the web, email and mobile services and so engage your visitors.
uuid: dd3b833a-e866-4238-abdd-c4eb20915dff
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: 36a03f6a-2b8c-4534-8100-fe4b0981e9f0
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Campaign Management{#campaign-management}

Campaign management provides digital marketers the opportunity to deliver personalized content and so create dedicated experiences for visitors.

It allows you to orchestrate your marketing campaigns across the web, email and mobile services and so engage your visitors. You can create content, segment visitors, push and promote targeted content for specific user profiles and manage campaigns across multiple channels.

This document describes the various elements that make up campaigns. More detailed information is available in the following documents:

* [Teasers and Strategies](../../classic-ui-authoring/using/classic-personalization-campaigns-teasers-strategy.md)
* [E-mail Marketing](../../classic-ui-authoring/using/classic-personalization-campaigns-email.md)
* [Landing Pages](../../classic-ui-authoring/using/classic-personalization-campaigns-landingpage.md)
* [Target offers](../../classic-ui-authoring/using/classic-personalization-campaigns-target-offers.md)
* [Working with the Marketing Campaign Manager](../../classic-ui-authoring/using/classic-personalization-campaigns-mktg-manager.md)
* [Understanding Segmentation](../../classic-ui-authoring/using/classic-personalization-campaigns-segmentation.md)
* [Setting up your campaign](../../classic-ui-authoring/using/classic-personalization-campaigns-setting-up-your.md)

Campaign management is made up of various elements:

* **Brands** 
  In AEM, brands are the top level unit and form a collection of **Campaigns**.

* **Campaigns** 
  A campaign is a collection of individual **Experiences**.

* **Experiences** 
  The focused content forms the various experiences, presented to the visitor at **Touchpoints**. There are several types of experience available:

    * **Teasers** 
      [Teaser Pages / Paragraphs](#teasers) are used to steer specific visitor **Segments** to content that is focused on their interests.  
      Teaser pages can:

        * present a range of options for the visitor to choose from
        * show only one teaser paragraph that is based on the specific visitor segment; for example, the teaser paragraph shown may be dependent on the age of the visitor.

      Typically a teaser page is a temporary action that will last for a specific period of time, until it is replaced by the next teaser page.
    
    * **Newsletters** 
      [E-mail Communications](#emailmarketing) are used to engage users and encourage them to visit your web site. These usually take the form of a newsletter, sent to your **Leads** (which are usually grouped into **Lists**). **Note:** Adobe is not planning to further enhance this capability. Recommendation is to [leverage Adobe Campaign and the integration to AEM](../../administering/using/campaign.md).
    
    * **Adobe Target** 
      This allows integration with Adobe Target (formerly Test&Target) which gives marketers a conversion website optimization tool with the necessary capabilities to continually make their online content and offers more relevant to their customers—yielding greater conversion. Adobe Target provides an intuitive interface for designing and executing tests, creating audience segments and targeting content—all from a single application.

* **Touchpoints** 
  These are the points of contact between the visitor and your campaign. The touchpoints are connected to the experiences that you have created.  
  For example, for teasers it is the content page where the teaser paragraph is located, for a newsletter it is the mailing list.

* **Leads** 
  The information that you have collected about your visitors and how to contact them forms the basis for your leads. **Note:** Adobe is not planning to further enhance this capability.  
  Recommendation is to [leverage Adobe Campaign and the integration to AEM](../../administering/using/campaign.md).  

* **Lists** 
  Leads are usually grouped into lists so that you can take collective action on them. Note: **Note:** Adobe is not planning to further enhance this capability.  
  Recommendation is to [leverage Adobe Campaign and the integration to AEM.](../../administering/using/campaign.md)  

* **Segments** 
  Site visitors have different interests and objectives when they come to a site. Analyzing this according to factors such as activity on the website, profile information registered and activity on other websites, helps you to define segments. Content can then be specifically targeted to the visitor's needs and interests according to the segment(s) they match.

* **MCM** 
  The Marketing Campaign Manager (MCM) is a console that allows you to access all the functionality you need to create and control your campaigns, brands, experiences, touchpoints, leads, lists, segments and reports.  
  It can be accessed from various locations (labelled as **Campaigns**), or with, for example, the URL:  
  `http://localhost:4502/libs/mcm/content/admin.html`
