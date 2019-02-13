---
title: DO NOT PUBLISH | Enable Amazon Cloudfront to serve content
seo-title: Enable Amazon Cloudfront to serve content
description: Use S3-based datastore using AWS Cloudfront to directly serve content.
seo-description: Use S3-based datastore using AWS Cloudfront to directly serve content.
page-status-flag: never-activated
uuid: f20ae2bf-af08-4181-a6fb-9cdff9ae3580
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
discoiquuid: 0ac2e378-763c-4516-8bee-44a8ce53a0c4
index: y
internal: n
snippet: y
---

# DO NOT PUBLISH | Enable Amazon Cloudfront to serve content{#do-not-publish-enable-amazon-cloudfront-to-serve-content}

Use S3-based datastore using AWS Cloudfront to directly serve content.

Normally, when a client requests for content, for example asset renditions, the content bits pass through Adobe Experience Manager (AEM). If the content is not cached locally, it is fetched from the S3 bucket.

In both cases, the AEM instance performs the task of fetching and serving content, which involves multiple input/output operations. If the user-agent is at a distant location, serving content requires multiple network hops, which introduce latency.

This feature uses the global Amazon CloudFront infrastructure to directly serve content to the client, rather than through AEM. It reduces the number of input/output operations and network hops. The content is served faster from an edge server that caches content.

To know more, see [Amazon Simple Storage Service documentation](https://aws.amazon.com/documentation/s3/).

>[!CAUTION]
>
>This feature is incompatible with the Catalog feature. If this feature is enabled, Catalogs do not work.

<!--
Comment Type: draft

<h2>Prerequisites</h2>
-->

<!--
Comment Type: draft

<p>To use the feature, you require the following:</p>
<ul>
<li>Amazon S3 as AEM datastore.</li>
<li>Root access of AWS account to generate or upload CloudFront keys and configure CloudFront access.</li>
<li>AWS Lambda to remove asset name from URL before fetching the asset from the S3 bucket</li>
<li>AEM APIs:
<ul>
<li><span class="code">sling-org-apache-sling-api:2.16.4</span></li>
<li><span class="code">sling-org-apache-sling-jcr-resource:3.0.6</span></li>
<li><span class="code">sling-org-apache-sling-servlets-get:2.1.28</span></li>
</ul> </li>
</ul>
-->

<!--
Comment Type: annotation
Last Modified By: asgupta
Last Modified Date: 2018-07-11T03:21:04.547-0400
Drafting the prerequisites section as requested in CQDOC-11872.
-->

## Security considerations {#security-considerations}

The feature incorporates the following to reduce security risks:

* The CloudFront URI for the requested content is signed using an AWS Cloudfront private key to prevent tampering. The key is stored on a path that is readable from the AEM server. The path is configured in CloudFront UriProvider.
* By default, the CloudFront URI for the requested content expires in 60 seconds to prevent malafide sharing.
* You can enable the feature only on AEM publish instances for publicly accessible content, because the signed URL is not checked for fine-grained access control.
* The CloudFront URI for the requested content is generated based on the contentID of the binary large object (BLOB) entity. It is not available in the Oak API. Therefore, a reflection is used to fetch it. To safeguard against implementation changes in Oak, the Granite URI provider implementation fails to return a URL if it isn't able to get the content. In this case, the requested content is served from AEM.

## Configure the feature {#configure-the-feature}

<!--
Comment Type: annotation
Last Modified By: satyam
Last Modified Date: 2018-06-22T06:43:58.640-0400
I do not think if the 4th point of security considerations is necessary here.
-->

The feature uses Adobe Granite's implementation for `org.apache.sling.api.resource.URIProvider`. It provides signed AWS CloudFront URLs for S3 objects stored in an Oak S3 DataStore.

Before configuring the feature, deploy AEM as TarMK or on MongoMK with a S3 DataStore.

You require the AWS CloudFront key to configure the feature. If you do not have it already, ensure that you have root access to the AWS subscription to manage keys in AWS. See [here](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-trusted-signers.html) for more details.

1. Follow the instructions [here](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-trusted-signers.html#private-content-creating-cloudfront-key-pairs) to generate the keys and upload to AWS.
1. To generate keys for AWS, run the following commands:
1. To generate a #PKCS8 formatted private key, run the following command:

   AWS provides the keyPairID after the public key is uploaded.

1. Configure CloudFront for the S3 bucket that is used as DataStore. See [here](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/GettingStarted.html) for more details.
1. Follow the instructions [here](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html) to enable S3 bucket access from CloudFront.
1. Rewrite the URI generated by `com.adobe.granite.uriprovider` to the appropriate CloudFront URL using the Amazon Lambda@Edge service. For details, see [here](https://docs.aws.amazon.com/lambda/latest/dg/lambda-edge.html).

   Essentially, do the following:

    * Add a Lambda function with the following code: 
    * Add a CloudFront trigger with the following settings:

        * `Distribution ID`: The id of the cloudfront distribution
        * `Event type`: origin-request
        * `Path pattern`: &#42;

    * Enable triggers and replicate.

1. Configure com.adobe.granite.uriprovider from the OSGi console. Provide the location of the CloudFront private key and the key pair Id.

    * Cloud front url: The cloud front URL, including a trailing slash. Normally, it is [http://cloudfrontdomain/](http://cloudfrontdomain/).
    * Ttl: Time in seconds for which each signed URL is valid.
    * Private key file: Path to the #PKCS8 formatted private key file, generally an absolute path.
    * Key pair id: The key pair ID generated by AWS Console when the public key is generated or uploaded.
    * Min size: Minimum size in kb above which a binary is redirected.
    * Forbidden paths: List of forbidden content path regex for which URIs are not provided. For example, to forbid paths that end with `cqdam.pyramid.tiff`, use `.*cqdam\.pyramid\.tiff$.` Set the forbidden paths to:

        * `.*cqdam\.pyramid\.tiff$`
        * `^\/var\/proxy\/jobs\/.*\.indd\/jcr:content\/renditions\/original$`
        * `^\/var\/proxy\/jobs\/.*\.idms\/jcr:content\/renditions\/original$`
        * `^\/var\/proxy\/jobs\/.*\.idml\/jcr:content\/renditions\/original$`

1. Validate the configuration by monitoring the content being served in the browser from AEM. In the browser's network console, you can view requests for content larger than the configured minimum size being redirected to AWS CloudFront.

