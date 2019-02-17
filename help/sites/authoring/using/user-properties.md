---
title: Configuring your account environment
seo-title: Configuring your account environment
description: AEM provides you with the capability to configure your account and certain aspects of the author environment
seo-description: AEM provides you with the capability to configure your account and certain aspects of the author environment
uuid: 76573c9e-ff1d-4490-a28e-6027564787d7
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: e9e8d778-4f36-483e-b03a-21f323886490
index: y
internal: n
snippet: y
---

# Configuring your account environment{#configuring-your-account-environment}

AEM provides you with the capability to configure your account and certain aspects of the author environment.

Using the [User](../../../sites/authoring/using/user-properties.md#main-pars-title-3) option in the [header](../../../sites/authoring/using/basic-handling.md#main-pars-title-21) and the associated [My Preferences](#userpreferences) dialog, you can modify your user options such as.

Begin by acessing the [User](../../../sites/authoring/using/user-properties.md#main-pars-title-3) option in the header.

### User Settings {#user-settings}

The **User** settings dialog gives you access to:

* Impersonate as

    * With the [Impersonate as](../../../sites/administering/using/security.md#main-pars-title-23) functionality a user can work on behalf of another user.

* Profile

    * Offers a convenient link to your [user settings](../../../sites/administering/using/security.md))

* [My Preferences](../../../sites/authoring/using/user-properties.md#main-pars-title-2)

    * Specify various preference settings unique to your user

![](assets/screen_shot_2018-03-20at103808.png)

### My Preferences {#my-preferences}

The **My Preferences** dialog is access via the [User](../../../sites/authoring/using/user-properties.md#main-pars-title-3) option in the header.

Each user can set certain properties for himself or herself.

![](assets/screen_shot_2018-03-20at102118.png)

* This defines the language to use for the UI of the authoring environment. Select the required language from the available list.

  This configuration is also used for the classic UI.

* This defines the behavior or opening windows. Select either:

    * **Multiple Windows** (Default)

        * Pages will be opened in a new window.

    * **Single Window**

        * Pages will be opened in the current window.

* This option requires the Assets companion app or Create Cloud desktop app.
* This defines the default color used when making annotations.

    * Click the color block to open the swatch selector to select a color.
    * Alternatively, enter the hex code for the desire color in the field.

* To improve readability, AEM will render dates within the last seven days as relative dates (e.g. Three days ago) and older dates as exact dates (e.g. 20 March 2017).

  This option defines how dates in the system are displayed. The following options are available:

    * **Always show exact date**: The exact date is always displayed (never a relative date).
    * **1 Day**: The relative date is shown for dates within one day, otherwise an exact date is shown.  
    
    * **7 Days (default)**: The relative date is shown for dates within seven days, otherwise an exact date is shown.  
    
    * **1 Month**: The relative date is shown for dates within one month, otherwise an exact date is shown.  
    
    * **1 Year**: The relative date is shown for dates within one year, otherwise an exact date is shown.  
    
    * **Always show relative date**: Exact dates are never shown and only relative dates are shown.

* AEM supports a number of keyboard shortcuts that make authoring more efficient.

    * [Keyboard shortcuts for editing pages](../../../sites/authoring/using/page-authoring-keyboard-shortcuts.md)
    * [Keyboard shortcuts for consoles](../../../sites/authoring/using/keyboard-shortcuts.md)

  This option enables keyboard shortcuts. By default they are enabled, but can be disabled for example if a user has certain accessibility requirements.

* This option enables [classic UI](/sites/classic-ui-authoring/user-guide)-based page authoring. By default the standard UI is used.  

* This option will only be available if your system administrator has enabled Assets Home Page experience for the entire organization.

