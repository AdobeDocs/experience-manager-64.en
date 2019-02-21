---
title: Using Dynamic Embedded Sequence
seo-title: Using Dynamic Embedded Sequence
description: null
seo-description: null
page-status-flag: never-activated
uuid: f90e8950-bc54-4c98-8c44-440338ab717a
contentOwner: jsyal
discoiquuid: 2ab82dee-bc1e-499b-8939-d8261d3cfa73
index: y
internal: n
snippet: y
---

# Using Dynamic Embedded Sequence{#using-dynamic-embedded-sequence}

Dynamic embedded sequences are created for larger projects that follow parent child hierarchy. It allows the user to embed a sequence inside a channel by Channel Role.

You can assign content to a channel by channel role. Channel role defines the context of the display. The role is targeted by various actions and is independent of the actual channel that fulfils the role. This section describes a use case that defines channels by role and how you can leverage that content to a global channel.

## Overview {#overview}

While assigning a channel to a display, you have the option of either specifying the path of the display or the name of the channel that will resolve to an actual channel by context.

Defining Channel By Role, allows you to create local version of a channel, in order to dynamically resolve location-specific content and also allows you to create a global channel that leverages the content for the localised channels..

>[!NOTE]
>
>To learn more about channel assignment, see Channel Assignment under authoring section in Screens documentation.

## Use Case Description {#use-case-description}

This use case allows you to create channels by roles and then use dynamic embedded sequence to leverage the content of the two localised channels, thus allowing the the main channel to use the content by their locations.

### Steps for Creating a Project {#steps-for-creating-a-project}

The project allows you to create two channels in different cities that displays localised content and then a global channel that shows the content of the localized channel.

Follow the steps below to create a sample project using dynamic embedded sequences:

1. Create a new project named **ClothingStore** in AEM Screens.

   **Screens** --&gt; **Create** --&gt; **Create Project** --&gt; **Screens** and enter name of the project as **ClothingStore**.

   ![](assets/screen_shot_2018-01-09at12242pm.png)

1. Create a location folder as (**UnitedStates**) to the **ClothingStore**.

   Select **ClothingStore** --&gt; **Locations** and click **+Create** from action bar.

   Select **Locations Folder** --&gt; **Next** and enter name and title as **UnitedStates** and click **Create**.

   ![](assets/screen_shot_2018-01-09at25329pm.png)

1. Create two different locations as **SanFrancisco** and **SanJose** in **UnitedStates** location folder.

   Select **ClothingStore** --&gt; **Locations** --&gt; **UnitesStates** and click **+ Create**.

   Select **Location** --&gt; **Next** and enter name and title of the locations as **SanFrancisco**.

   Similarly, create another location for **SanJose**.

1. Select **ClothingStore** --&gt; **Locations** --&gt; **UnitesStates** and click **+ Create**.

   Select **Sequence Channel** --&gt; **Next** and enter name and title of the channel as **DealsSF**.

   Similarly, create another channel for your location (**SanJose**), titles and named as **DealsSJ**.

1. 
1. Select **ClothingStore** --&gt; **Locations** --&gt; **UnitesStates** and click **+ Create**.

   Select **Display** --&gt; **Next** and enter name and title of the channel as **DealsCoats**.

   Similarly, create another display for your location (**SanJose**), titles and named as **DealsShoes**.

1. Select **ClothingStore** --&gt; **Channels** and click **+ Create**.

   Select **Sequence Channel** --&gt; **Next** and enter name and title of the channel as **SharedContent**.

