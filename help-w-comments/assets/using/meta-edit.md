---
title: How to edit or add metadata
seo-title: How to edit or add metadata
description: Learn about asset metadata in AEM Assets an various ways by which you can edit asset metadata.
seo-description: Learn about asset metadata in AEM Assets an various ways by which you can edit asset metadata.
uuid: ae8e0b24-06a0-4592-96bd-ac655bac9ead
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: bcf8048a-2316-40b1-b805-4155d34b0df5
index: y
internal: n
snippet: y
---

# How to edit or add metadata{#how-to-edit-or-add-metadata}

Metadata is additional information about the asset that can be searched. It is automatically extracted when you upload an image. You can edit the existing metadata or add new metadata properties to existing fields (for example, when a metadata field is blank).

Because companies need controlled and reliable metadata vocabularies, AEM Assets does not allow for adhoc adding of new metadata properties. Although authors cannot add new metadata fields for assets, developers can. See [Creating New Metadata Property for Assets](../../assets/using/meta-edit.md#main-pars-title).

## Editing metadata for an asset {#editing-metadata-for-an-asset}

To edit metadata:

1. Do one of the following:

    * From the Assets UI, select the asset and click/tap the View Properties icon from the toolbar.
    * From the asset thumbnail, select the View Properties quick action.
    * From the asset page, click/tap the View Properties icon from the toolbar.

   ![](assets/chlimage_1-170.png)

   The asset page displays all of the asset's metadata. This metadata was automatically extracted when it was uploaded (ingested) into AEM Assets.

   ![](assets/chlimage_1-171.png)

1. Make edits to the metadata under the various tabs, as required, and when completed, click/tap **Save** from the toolbar to save your changes. Click/tap **Close** to return to the Assets UI.

   >[!NOTE]
   >
   >If a text field is empty, there is no existing metadata set. You can enter a value into the field and save it to add that metadata property.

Any changes to the metadata of an asset are written back to the original binary as part of its XMP data. This is done via AEM's Metadata write-back workflow. Changes made to the existing properties (such as `dc:title`) are overwritten and newly created properties (including custom properties like `cq:tags`) are added together with the schema.

XMP write-back is supported and enabled for the platforms and file formats described in [Technical Requirements.](../../sites/deploying/using/technical-requirements.md)

## Editing Metadata Schema {#editing-metadata-schema}

<!--
Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2017-11-30T05:30:09.387-0500
<p>The information in "Creating New Metadata Property for Assets" is incomplete and some of it is wrong. Please check the remarks below (copied from page "Customizing and Extending CQ DAM".) These notes have originally been added by myself - please ask me in case something is unclear.</p>
<p>&gt; [...] by configuring the metadata dialog box.<br /> What is the metadata dialog box?</p>
<p>&gt; To configure a new metadata property so that it is available for all assets:<br /> Wrong. The form items defined in /apps/dam/content/asseteditor/formitems are not available for all assets. It is the fallback where no MIME type specific form items are defined.</p>
<p><br /> Missing: non-alphanumeric characters in a mime type result in a new collection (see below)<br /> e.g. text/vnd.latex-z &gt;&gt; text/vnd/latex/z<br /> (Maybe a more common sample than tex/vnd.latex-z should be found)</p>
<p>&gt; Format-specific metadata reside at the path image/<em>format</em>/formitems.xml<br /> Wrong/unclear: They reside at the path <em>format</em>/formitems.xml where format consists of at least two items (e.g image/jpeg or text/vnd/latex/z - see note about non-alphanumeric characters above)</p>
<p>Missing: The same mechanism as for the form items can also be used to define different Asset Editors for different MIME types, e.g. different thumbnail sizes, different tabs available. In most cases this feature probably will not be used but maybe this is the place to mention it. WDYT?</p>
-->

<!--
Comment Type: remark
Last Modified By: unknown unknown (kautzman)
Last Modified Date: 2017-11-30T05:30:09.397-0500
<ul>
<li>doubleclicking an asset in DAM Admin opens the Asset Editor</li>
<li>there can be an editor for each mime type, resp. a collection of mime types (best match)<br />
<ul>
<li>non-alphanumeric characters in a mime type ends in a new collection:<br /> image/jpeg &gt;&gt; image/jpeg<br /> image/vnd.fpx &gt;&gt; image/vnd/fpx<br /> text/vnd.latex-z &gt;&gt; text/vnd/latex/z<br /> <br /> </li>
</ul> </li>
<li>the editors and/or the metadata forms are configurable in /apps<br /> </li>
<li>a set of out of the box editors are located in /libs/dam/content/asseteditors. These can be overwritten in /apps<br /> <i>not yet, see <a href="http://bugs.day.com/bugzilla/show_bug.cgi?id=25765">#25765 - Asset Editor: Define sample editors for libs</a></i></li>
<li>for config/overwrite see also <a href="http://bugs.day.com/bugzilla/show_bug.cgi?id=25688">#25688 - Asset Editor: Configurable form</a></li>
</ul>
<p> </p>
<p>The editors for certain mime types can be overwritten in /apps:<br /> <br /> /apps/dam/asseteditors/<br /> asseteditor.xml &gt;&gt; Overwrite Default Asset Editor (fallback)<br /> image/<br /> asseteditor.xml &gt;&gt; Overwrite Image Asset Editor<br /> jpeg/<br /> asseteditor.xml &gt;&gt; Overwrite JPEG Asset Editor</p>
-->

<!--
Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2017-11-30T05:30:09.407-0500
<p>The very same chapter is available on page "Managing Digital Assets".</p>
<p>See my remarks over there.</p>
<p> </p>
<p>AWB - Just moved remarks from Vinzenz and Peeter over here for ease of use. No new info (and now it says all the remarks are mine)</p>
-->

For details on how to edit metadata schema, see [Editing metadata schema forms](../../assets/using/metadata-schemas.md#main-pars-title).

<!--
Comment Type: remark
Last Modified By: Alva Ware-Bevacqui (alvawb)
Last Modified Date: 2017-11-30T05:30:09.425-0500
<p>Will add link to metadata documentation once complete.</p>
-->

## Registering a custom namespace within AEM {#registering-a-custom-namespace-within-aem}

You can add your own namespaces within AEM. Just as there are predefined namespaces such as cq, jcr and sling, you can have a namespace for your repository metadata and xml processing.

1. Go to the node type administration page *http://&lt;host&gt;:&lt;port&gt;/crx/explorer/nodetypes/index.jsp*.
1. Click or tap **Namespaces** at the top of the page. The namespace administration page is displayed in a window.  

1. To add a namespace, click or tap **New** at the bottom.
1. Specify a custom namespace in the XML namespace convention (Specify the id in the form of a URI and an associated prefix for the id), and click or tap **Save**.

