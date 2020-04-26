---
title: Multi Zone to Single Zone Takeover Loop
seo-title: Multi Zone to Single Zone Takeover Loop
description: Follow  this page to learn about Multi Zone to Single Zone Takeover Loop in an AEM Screens project.  
seo-description: Multi Zone to Single Zone Takeover Loop in an AEM Screens project.  
---

# Multi Zone to Single Zone Takeover Loop{#single-zoneto-multizone}

## Use Case Description {#use-case-description}

This section describes a use case example that emphasizes on how to set up a multi zone layout channel that alternates with a single zone layout channel. Each channel has sequencing image/video assets.

### Preconditions {#preconditions}

Before you start this use case, make sure you understand how to:

* **[Create and Manage Channels](/help/screens/managing-channels.md)**
* **[Create and Manage Locations](/help/screens/managing-locations.md)**
* **[Create and Manage Schedules](/help/screens/managing-schedules.md)**
* **[Device Registration](/help/screens/device-registration.md)**

### Primary Actors {#primary-actors}

Content Authors

## Setting up the Project {#setting-up-the-project}

Follow the steps below to set up a project:

1. Create an AEM Screens Project named as **TakeoverLoop**, as shown below.

   >[!NOTE]
   >
   >To learn more about creating and managing projects in AEM Screens, refer to [Creating a Project](/help/screens/creating-a-screens-project.md).

   ![](assets/takeover-loop1.png)

1. **Creating a Split Screen Channel**

    1. Select the **Channels** folder and click **Create** from the action bar to open the wizard to create a channel.
    1. Select **Left-L Bar Split Screen Channel** from the wizard and create the channel titled as **MultiZoneLayout**.

       ![](assets/takeover-loop2.png)

    1. Select the **MultiZoneLayout** channel and click **Edit** from the action bar to open the editor. Drag and drop the assets to each of the zones. The following example shows a video, image and a text banner in the channel, as shown below.
        ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ3.png)

1. **Creating a 2X2 Channel with four images**

    1. Select the **Channels** folder and click **Create** from the action bar to open the wizard to create a channel.

    1. Select **2X2 Split Screen Channel** template from the wizard and create the channel titled as **TwobyTwoChannel**.

       ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ4.png)
    1. Select the channel and click **Edit** from the action bar to open the editor and drag and drop four images (four different zones) to that channel, as shown below.
        ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ5.png)

1. **Creating a 1X2 Split Screen Channel with two images**

    1. Select the **Channels** folder and click **Create** from the action bar to open the wizard to create a channel.

    1. Select **1X2 Split Screen Channel** template from the wizard and create the channel titled as **OnebyTwoChannel**.

       ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ6.png)
    1. Select the channel and click **Edit** from the action bar to open the editor and drag and drop two images (two different zones) to that channel, as shown below.
        ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ7.png)

1. **Creating a Channel with one full screen video**

    1. Select the **Channels** folder and click **Create** from the action bar to open the wizard to create a channel.

    1. Select **Sequence Channel** template from the wizard and create the channel titled as **FullScreensVideo**.

       ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ8.png)
    1. Select the channel and click **Edit** from the action bar to open the editor and drag and drop the video component to that channel and then add the desired video, as shown below.
        ![screen_shot_2019-02-21at35932pm](assets/SZtoMZ9.png)