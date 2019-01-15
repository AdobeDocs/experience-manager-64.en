---
title: Trying out Core Components in We.Retail
seo-title: Trying out Core Components in We.Retail
description: null
seo-description: null
uuid: 786510b5-2949-4d60-86ee-0199d53bc74d
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 28cb99ed-a4b6-4603-ac31-439c26613a53
disttype: dist5
gnavtheme: light
groupsectionnavitems: no
hidemerchandisingbar: inherit
hidepromocomponent: inherit
isreadyforlocalization: false
modalsize: 426x240
index: y
internal: n
snippet: y
---

# Trying out Core Components in We.Retail{#trying-out-core-components-in-we-retail}

The core components are modern, flexible components featuring easy extensibility and allowing for simple integration into your projects. The core components have been built around several major design principles such as HTL, usability out-of-the-box, configurability, versioning, and extensibility. We.Retail has been built on core components.

## Trying it out {#trying-it-out}

1. Start AEM with the We.Retail sample content and open the [Components Console](../../authoring/using/default-components-console.md).

   **Global Navigation -&gt; Tools -&gt; Components**

1. Opening the rail in the Components Console, you can filter for a particular component group. The core components can be found in

    * `.core-wcm`: The standard core components
    * `.core-wcm-form`: The form submission core components

   Choose `.core-wcm`.

   ![](assets/chlimage_1-240.png)

1. Note that all core components are named **v1**, reflecting that this is the first version of this core component. Regular versions will be released going forward, which will be version-compatible with AEM and allowing easy upgrading so you can take advantage of the latest features.
1. Click **Text (v1)**.

   See that the **Resource Type** of the component is `/apps/core/wcm/components/text/v1/text`. Core components are found under `/apps/core/wcm/components` and are versioned per component.

   ![](assets/chlimage_1-241.png)

1. Click on the **Documentation** tab to see the developer documentation for the component.

   ![](assets/chlimage_1-242.png)

1. Return to the Component Console. Filter for the group **We.Retail** and select the **Text** component.
1. See that the **Resource Type** points to a component as expected under `/apps/weretail` but the **Resource Super Type** points back to the core component `/apps/core/wcm/components/text/v1/text`.

   ![](assets/chlimage_1-243.png)

1. Click the **Live Usage** tab to see on which pages this component is currently being used. Click the first **Thank You** page to edit the page.

   ![](assets/chlimage_1-244.png)

1. On the Thank You page, select the text component and in the edit menu of the component click the Cancel Inheritance icon.

   [We.Retail has a globalized site structure](../../developing/using/we-retail-globalized-site-structure.md) where content is pushed from language masters to [live copies through a mechanism called inheritance](../../administering/using/msm.md). For this reason, inheritance must be cancelled in order to allow a user to manually edit text.

   ![](assets/chlimage_1-245.png)

1. Confirm the cancellation by clicking **Yes**.

   ![](assets/chlimage_1-246.png)

1. Once the inheritance is cancelled and you select the text components, many more options are available. Click on** Edit**.

   ![](assets/chlimage_1-247.png)

1. You can now see what edit options are available to the text component.

   ![](assets/chlimage_1-248.png)

1. From the **Page Information** menu select **Edit Template**.
1. In the Template Editor of the page, click on the **Policy** icon of the Text component in the **Layout Container** of the page.

   ![](assets/chlimage_1-249.png)

1. The core components allow a template author to configure which Properties are available to the page authors. These include features such as allowed paste sources, formatting options, available paragraph styles, etc.

   Such design dialogs are available for many core components and work hand-in-hand with the template editor. Once enabled, they are available to the author through the component editors.

   ![](assets/chlimage_1-250.png)

## Further Information {#further-information}

For further information on the core components, see the authoring document [Core Components](/content/help/en/experience-manager/core-components/user-guide) for an overview of the capabilities of the core components and the developer document [Developing Core Components](/content/help/en/experience-manager/core-components/using/developing) for a technical overview.

Also you may wish to further investigate [editable templates](../../developing/using/we-retail-editable-templates.md). Refer to the authoring document [Creating Page Templates](../../authoring/using/templates.md) or the developer document Page [Templates - Editable](../../developing/using/page-templates-editable.md) for complete details on editable templates.
