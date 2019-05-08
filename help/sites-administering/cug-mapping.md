---
title: Custom User Group Mapping in AEM 6.4
seo-title: Custom User Group Mapping in AEM 6.4
description: Learn how Custom User Group Mapping works in AEM.
seo-description: Learn how Custom User Group Mapping works in AEM.
page-status-flag: de-activated
uuid: 08b220ea-2df2-4d32-9d2f-82c32cf2d849
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: 3c2e952f-185e-451c-8abb-324b44b10ee3
---

# Custom User Group Mapping in AEM 6.4 {#custom-user-group-mapping-in-aem}

## Comparison of JCR Content related to CUG {#comparison-of-jcr-content-related-to-cug}

<!--converted nested tables. check. Reformat?-->

|Older AEM Versions|AEM 6.4|Comments|
|Property: cq:cugEnabled<br> Declaring node type: N/A, residual property|Authorization:<br> Node: rep:cugPolicy of node type rep:CugPolicy <br>Declaring node type: rep:CugMixin<br>Authentication:<br> Mixin type:<br> granite:AuthenticationRequired|In order to restrict read access a dedicated CUG policy is applied to the target node. <br>NOTE: Policies can only be applied at the configured supported paths. <br>Nodes with name rep:cugPolicy and type rep:CugPolicy are protected and cannot be written using regular JCR API calls; use JCR access control management instead. <br>See [this page](https://jackrabbit.apache.org/oak/docs/security/authorization/cug.html) for more info.<br>In order to enforce authentication requirement on a node it is sufcient to add the mixin type granite:AuthenticationRequired. <br>NOTE: Only respected below the configured supported paths.|
|Property: cq:cugPrincipals <br>Declaring node type: NA, residual property|Property: rep:principalNames <br>Declaring node type: rep:CugPolicy|The property containing the names of those principals that are allowed to read the content below the restricted CUG is protected and cannot be written using regular JCR API calls; use JCR access control management instead. <br>See [this page](https://svn.apache.org/repos/asf/jackrabbit/trunk/jackrabbitapi/src/main/java/org/apache/jackrabbit/api/security/authorization/PrincipalSetPolicy.java) for more details on the implementation.|
|Property: cq:cugLoginPage <br>Declaring node type: NA, residual property|Property: granite:loginPath (optional) <br>Declaring node type: granite:AuthenticationRequired|A JCR node that has the mixin type granite:AuthenticationRequired defned, may optionally defne an alternative login path. <br>NOTE: Only respected below the confgured supported paths.|
|Property: cq:cugRealm <br>Declaring node type: NA, residual property|NA|No longer supported with the new implementation.|

## Comparison of OSGi Services {#comparison-of-osgi-services}

|Older AEM Versions|AEM 6.4|Comments|
|Label: Adobe Granite Closed User Group (CUG) Support <br>Name: com.day.cq.auth.impl.CugSupportImpl|Label: Apache Jackrabbit Oak CUG Configuration <br>Name: org.apache.jackrabbit.oak.spi.security.authorization.cug.impl.CugConfiguration <br>ConfgurationPolicy = REQUIRED<br>Label: Apache Jackrabbit Oak CUG Exclude List <br>Name: org.apache.jackrabbit.oak.spi.security.authorization.cug.impl.CugExcludeImpl <br>ConfgurationPolicy = REQUIRED<br>Name: com.adobe.granite.auth.requirement.impl.RequirementService <br>Label: Adobe Granite Authentication Requirement and Login Path Handler <br>Name: com.adobe.granite.auth.requirement.impl.DefaultRequirementHandler <br>ConfgurationPolicy = REQUIRED|Configuration of the CUG authorization and enable/disable the evaluation.<br>Service to configure exclusion list of principals which should not be afected by the CUG authorization. <br>NOTE: If the CugExcludeImpl is not configured, the CugConfguration will fallback to the default. <br>It is possible to plug a custom CugExclude implementation in case of special needs. <br>OSGi component implementing LoginPathProvider that exposes a matching login path to the LoginSelectorHandler. It has a mandatory reference to a RequirementHandler which is used to register the observer that listens to changed auth requirements stored in the content by the means of the granite:AuthenticationRequired mixin type. <br>OSGi component implementing LoginPathProvider that exposes a matching login path to the LoginSelectorHandler. It has a mandatory reference to a RequirementHandler which is used to register the observer that listens to changed auth requirements stored in the content by the means of the granite:AuthenticationRequired mixin type. <br>OSGi component implementing RequirementHandler that notifes the SlingAuthenticator about changes to authrequirements.<br>As confguration policy for this component is REQUIRE it will only be activated if a set of supported paths is specifed.<br>Enabling the service will launch the RequirementService.|
