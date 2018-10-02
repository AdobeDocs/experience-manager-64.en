---
uuid: 00a47827-1bc0-4809-af13-d674d2593a36
index: y
internal: n
snippet: y
translate: y
---

# Forms Repository Restructuring in AEM 6.4

As described on the parent [Repository Restructuring in AEM 6.4](repository-restructuring.md) page, customers upgrading to AEM 6.4 should use this page to assess the work effort associated with repository changes impacting the AEM Forms Solution. Some changes require work effort during the AEM 6.4 upgrade process, while others can be deferred until a 6.5 upgrade.

**With 6.4 Upgrade**

* [Misc](forms-repository-restructuring-in-aem-6-4.md#main-pars_header_1531137065)

**Prior to 6.5 Upgrade**

* [Echosign Cloud Service Configuration](forms-repository-restructuring-in-aem-6-4.md#EchosignCloudServiceConfiguration)
* [Recaptcha Cloud Service Configurations](forms-repository-restructuring-in-aem-6-4.md#RecaptchaCloudServiceConfigurations)
* [Typekit Cloud Service Configurations](forms-repository-restructuring-in-aem-6-4.md#TypekitCloudServiceConfigurations)
* [Misc](forms-repository-restructuring-in-aem-6-4.md#main-pars_header)

---

## With 6.4 Upgrade

### Misc

| **Previous location** | `/etc/clientlibs/fd/fp` |
|---|---|
| **New location(s)** | `/libs/fd/fp/components` |
| **Restructuring guidance** |Any explicit references in custom code to the Legacy location must be updated to the New location. |
| **Notes** |These client libraries should not be modified or extended. |

| **Previous location** | `/etc/clientlibs/fd/rte` |
|---|---|
| **New location(s)** | `/libs/fd/rte` |
| **Restructuring guidance** |For the resources in the client libs that can be referred byabsolute paths, you need to use newer paths in fresh assets. |
| **Notes** |N/A |

| **Previous location** | `/etc/clientlibs/fd/af` |
|---|---|
| **New location(s)** | `/libs/fd/af/authoring/clientlibs` |
| **Restructuring guidance** |For the resources in the client libs that can be referred byabsolute paths, you need to use newer paths in fresh assets. |
| **Notes** |N/A |

| **Previous location** | `/etc/clientlibs/fd/xfaforms` |
|---|---|
| **New location(s)** | `/libs/fd/xfaforms/clientlibs/` |
| **Restructuring guidance** |For the resources in the client libs that can be referred byabsolute paths, you need to use newer paths in fresh assets. |
| **Notes** |N/A |

| **Previous location** | `/etc/clientlibs/fd/af` |
|---|---|
| **New location(s)** | `/libs/fd/af/runtime/clientlibs` |
| **Restructuring guidance** |For the resources in the client libs that can be referred byabsolute paths, you need to use newer paths in fresh assets. |
| **Notes** |N/A |

| **Previous location** | `/etc/clientlibs/fd/af` |
|---|---|
| **New location(s)** | `/libs/fd/af/runtime/clientlibs` |
| **Restructuring guidance** |For the resources in the client libs that can be referred byabsolute paths, you need to use newer paths in fresh assets. |
| **Notes** |N/A |

| **Previous location** | `/etc/clientlibs/fd/expeditor` |
|---|---|
| **New location(s)** | `/libs/fd/expeditor/clientlibs` |
| **Restructuring guidance** |For the resources in the client libs that can be referred byabsolute paths, you need to use newer paths in fresh assets. |
| **Notes** |N/A |

| **Previous location** | `/etc/clientlibs/fd/fmaddon` |
|---|---|
| **New location(s)** | `/libs/fd/fmaddon` |
| **Restructuring guidance** |Changing these clientlibs was never recommended or supported. If modifications have been made to these clientlibs, they should be rolled back to use the AEM-provided code. |
| **Notes** |N/A |

| **Previous location** | `/etc/aep` |
|---|---|
| **New location(s)** | `/var/fd/content/annotations` |
| **Restructuring guidance** |Changing these clientlibs was never recommended or supported. If modifications have been made to these clientlibs, they should be rolled back to use the AEM-provided code. |
| **Notes** |N/A |

---

## Prior to 6.5 Upgrade

### Echosign Cloud Service Configuration

| **Previous location** | `/etc/cloudservices/echosign` |
|---|---|
| **New location(s)** | `/conf/<tenant>/settings/cloudconfigs/echosign` |
| **Restructuring guidance** |The [Lazy Content Migration](lazy-content-migration.md) utility to be triggered from Forms Migration UI. |
| **Notes** |N/A |

### Recaptcha Cloud Service Configurations

| **Previous location** | `/etc/cloudservices/recaptcha` |
|---|---|
| **New location(s)** | `/conf/<tenant>/settings/cloudconfigs/recaptcha` |
| **Restructuring guidance** |The [Lazy Content Migration](lazy-content-migration.md) utility to be triggered from Forms Migration UI. |
| **Notes** |N/A |

### Typekit Cloud Service Configurations

| ****Previous location** | `/etc/cloudservices/typekit` |
|---|---|
| **New location(s)** | `/conf/<tenant>/settings/cloudconfigs/typekit` |
| **Restructuring guidance** |The [Lazy Content Migration](lazy-content-migration.md) utility to be triggered from Forms Migration UI. |
| **Notes** |N/A |

### Misc

| **Previous location** | `/etc/cloudservices/fdm` |
|---|---|
| **New location(s)** | `/conf/<tenant>/settings/cloudconfigs/fdm` |
| **Restructuring guidance** |The [Lazy Content Migration](lazy-content-migration.md) utility to be triggered from Forms Migration UI. |
| **Notes** |N/A |

| **Previous location** | `/etc/designs/fd/fp` |
|---|---|
| **New location(s)** | `/libs/fd/fp` |
| **Restructuring guidance** |Any references to the /etc templates should eventually be updated to point to their `/libs` counterparts. |
| **Notes** |N/A |

