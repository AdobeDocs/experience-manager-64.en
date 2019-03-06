---
title: Selecting your UI
seo-title: Selecting your UI
description: For convenience to authoring users, the touch-enabled UI does allow for switching to the classic UI when necessary.
seo-description: For convenience to authoring users, the touch-enabled UI does allow for switching to the classic UI when necessary.
uuid: d684e9a1-89d7-4d5f-963c-aaf9c98aaa0a
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: cd908c7c-d09e-41a9-8ef6-7f8ae703e26d
---

# Selecting your UI{#selecting-your-ui}

Since the touch-optimized UI is designed to supersede the classic UI, the user or administrator of the AEM instance must make an active decision to continue using the classic UI. Because the classic UI is no longer maintained, there is no way for the authoring user to simply switch from the classic UI to the equivalent in the touch-optimized UI.

For convenience to authoring users, the touch-optimized UI does allow for switching to the classic UI when necessary. See the [Selecting your UI](../../../sites/authoring/using/select-ui.md) in the standard Authoring documentation for details.

>[!NOTE]
>
>Instances upgraded from a previous version will retain the classic UI for page authoring.
>
>After upgrade, page authoring will not be automatically switched to the touch-optimized UI, but you can configure this using the the [OSGi configuration](../../../sites/deploying/using/configuring-osgi.md) of the **WCM Authoring UI Mode Service** ( `AuthoringUIMode` service). See [UI Overrides for the Editor](#uioverridesfortheeditor).

### Configuring the Default UI for Your Instance {#configuring-the-default-ui-for-your-instance}

A system administrator can configure the UI that is seen at startup and login by using [Root Mapping](../../../sites/deploying/using/osgi-configuration-settings.md#daycqrootmapping).

This can be overridden by user defaults or session settings.
