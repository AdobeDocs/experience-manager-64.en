---
title: Installing and Configuring Video Transcoder with FFmpeg
seo-title: Installing and Configuring Video Transcoder with FFmpeg
description: null
seo-description: null
uuid: b7b2dedf-4cdb-422f-96af-4ffaf2b0687a
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: c569dc35-979d-476a-87aa-45930a872e25
index: y
internal: n
snippet: y
---

# Installing and Configuring Video Transcoder with FFmpeg{#installing-and-configuring-video-transcoder-with-ffmpeg}

<!--
Comment Type: draft

<p>While the video transcoder with FFmpeg works similar to the connector FFmpeg transcoder with Assets (see <a href="../../sites/authoring/using/default-components-foundation.md">Video Components</a>) , you have more control over the process using this version because you are sharing the source code for the same transcoder. If, however, you decide not to use FFmpeg, or you want to use it differently than what is offered with the out-of-the-box transcoder, you can use this source code as a template to build out the transcoder how you want. Also, be aware that when you use FFmpeg, you can copy video renditions to a file system outside of AEM using File Copy Service.</p>
-->

##

<!--
Comment Type: draft

<h3>Installing FFmpeg</h3>
-->

<!--
Comment Type: draft

<p>You will now download and install FFmpeg and verify the installation.</p>
-->

<!--
Comment Type: draft

<ol>
<li><p>Go to <a href="http://www.ffmpeg.org">http://www.ffmpeg.org</a> to download and install the latest version of FFmpeg for your specific environment (Macintoch, Windows, or Linux).</p> <p>Make sure the ffmpeg executable is set in your system path. You should be able to run <span class="code">ffmpeg</span> from any directory in your system.</p> </li>
</ol>
-->

<!--
Comment Type: draft

<note type="note">
<p>AEM 6.2 is compatible with FFmpeg 3.0 and is configured to run correctly with FFmpeg 3.0 (which was the latest version at the time of general availability of 6.2).<br /> As per the FFmpeg documentation at <a href="https://trac.ffmpeg.org/wiki/Encode/AAC">https://trac.ffmpeg.org/wiki/Encode/AAC</a>, FFmpeg 3.0 does not ship with pre-built <span class="code">libvo-aacenc</span> or <span class="code">libaacplus</span> encoders. To use these encoders, install FFmpeg with the <span class="code">--with-fdk-aac</span> and/or <span class="code">--with-faac</span> option(s), or compile FFmpeg from non-free sources.</p>
<p>Because FFmpeg performs all transcoding operations, any reference to default configurations pertains to particular versions of FFmpeg validated by Adobe and may change in future. For more details, see FFmpeg encoding guidelines at <a href="https://trac.ffmpeg.org/wiki/Encode/H.264">https://trac.ffmpeg.org/wiki/Encode/H.264</a> and <a href="https://trac.ffmpeg.org/wiki/Encode/AAC">https://trac.ffmpeg.org/wiki/Encode/AAC</a>.</p>
</note>
-->

<!--
Comment Type: draft

<note type="note">
<p>From software security standpoint, Adobe recommends using the latest releases of all third-party software. However, if it is not possible to upgrade to FFmpeg 3.0, you may try the following:</p>
<ul>
<li>Add <span class="code">-strict -2</span> to the <span class="code">customArgs</span> property of <i>/etc/dam/video/iehq/jcr:content and /etc/dam/video/hq/jcr:content</i>.</li>
<li>Change the <span class="code">audioCodec</span> property of <i>/etc/dam/video/iehq/jcr:content</i> and <i>/etc/dam/video/hq/jcr:content</i> to <span class="code">libvo_aacenc</span> from <span class="code">aac</span>.</li>
</ul>
</note>
-->

<!--
Comment Type: draft

<h3>Installing cq-s7dam-video-core-1.0.jar</h3>
-->

<!--
Comment Type: draft

<p>Following the installation of FFmpeg, you will now verify the s7damVideobundle.</p>
-->

<!--
Comment Type: draft

<ol>
<li><p>Open AEM in your environment.</p> </li>
<li><p>Untar <span class="code">s7damvideobundle.tar</span> and then go to the <span class="code">s7damvideobundle/core</span> directory.</p> <p>You can download <a href="https://marketing.adobe.com/resources/help/en_US/s7/s7damvideobundle.tar">s7damvideobundle.tar here</a>.</p> </li>
<li><p>Run the following command:</p>  <p>The jar file from this project is installed under <span class="code">/libs/dam/install/cq-s7dam-video-core-1.0.jar</span>. Code is derived out of the existing DAM Video application which is part of the CQ Codebase.</p> <p>Three services are installed with the following process labels:</p>
<ul>
<li>"Create Thumbnail with FFMPEG as a pluggable component"</li>
</ul> <p style="margin-left: 40px;">Used as a reference implementation component which you can repurpose for integration with another third-party video encoder.<br /> </p>
<ul>
<li>"Transcode Video with FFMPEG as a pluggable component"</li>
</ul> <p style="margin-left: 40px;">Used for encoding by way of FFMPEG when customization is required. For example, set up of business rules to apply different encoding profiles based on source video aspect ratio.<br /> </p>
<ul>
<li>"Copy Transcoded Videos to NFS Mount"</li>
</ul> <p style="margin-left: 40px;">Used to store resulting encoded files to a server mount for delivery, such as integration with CDN or video packaging services.</p> </li>
</ol>
-->

<!--
Comment Type: draft

<h3>Setting up the Video Services through CQ Workflow</h3>
-->

<!--
Comment Type: draft

<ol>
<li><p>In your running instance of AEM, go to the following:</p>  </li>
<li><p>Tap <strong>Tools </strong>&gt; <strong>Workflow </strong>&gt; <strong>Models</strong>, then on the Workflow Models page, double-click <span class="code">DAM Update Asset</span>.</p> </li>
<li><p>In the <strong>DAM Update Asset</strong> page, in the workflow model, delete any existing <span class="code">FFmpeg thumbnails</span> and <span class="code">FFmpeg transcoding</span> services that may exist.</p> <p>You are now ready to set up the FFmpeg thumbnailing service.</p> </li>
</ol>
-->

<!--
Comment Type: draft

<h3>Setting up the FFmpeg Thumbnailing Service</h3>
-->

<!--
Comment Type: draft

<ol>
<li><p>In the AEM Sidekick, expand the <strong>Workflow</strong> list.</p> </li>
<li><p>Drag-and-drop <strong>Process Step</strong> on to your workflow page.</p>  <img imageRotate="0" src="assets/chlimage_1-397.png" /></li>
<li><p>Double-click the process step to open the <strong>Step Properties</strong> dialog box. In the <strong>Common</strong> tab, type a title such as <span class="code">FFmpeg thumbnail service</span>.</p> <p>Optionally, in the <strong>Description</strong> field, type a description that can further help you identify the process, such as <span class="code">Extracts video poster frame</span>.</p> </li>
<li><p>Tap the <strong>Process</strong> tab. Then in the <strong>Process</strong> drop-down list, select <strong>Create Thumbnail with FFMPEG as a pluggable component</strong>.</p> </li>
<li><p>Check <strong>Handler Advance</strong> option to turn it on.</p> </li>
<li><p>In the <strong>Arguments</strong> field, add the following:</p>  <p>The arguments <span class="code">count</span> and <span class="code">index</span> are explained at the following location:</p>  </li>
<li><p>Click <strong>OK</strong>, and then click <strong>Save</strong> near the upper-left corner of the <strong>Workflow</strong> page.</p> <p>You are now ready to set up the FFMPEG Transcoding Service. This service is used for video encoding by way of FFMPEG when customization is required such as setting up business rules to apply different video encoding profiles based on the source video's aspect ratio.</p> </li>
</ol>
-->

<!--
Comment Type: draft

<h3>Setting up the FFmpeg Transcoding Service</h3>
-->

<!--
Comment Type: draft

<ol>
<li><p>In the AEM Sidekick, in the <strong>Workflow</strong> list, drag and drop <strong>Process Step</strong> on to your workflow immediately below the FFmpeg thumbnails step that you just added earlier.</p> </li>
<li><p>Double-click the process step to open the <strong>Step Properties</strong> dialog box. In the <strong>Common</strong> tab, type a title such as <span class="code">FFmpeg transcoding service</span>.</p> <p>Optionally, in the <strong>Description</strong> field, type a description that can further help you identify the process, such as <span class="code">Creates web-enabled video formats</span>.</p> </li>
<li><p>Click the <strong>Process</strong> tab, in the <strong>Process</strong> drop-down list, select <strong>Transcode Video with FFMPEG as a pluggable component</strong>.</p> </li>
<li><p>Check <strong>Handler Advance</strong> option to turn it on.</p> </li>
<li><p>In the <strong>Arguments</strong> field, add the following:</p>  <p>The transcoding video profiles you add here should reference the out-of-the-box Assets video profiles in the Tools/Assets/Video Profiles folder on the Tools page (/etc/dam/video).</p>  </li>
<li><p>Click <strong>OK</strong>, and then click <strong>Save</strong> near the upper-left corner of the <strong>Workflow</strong> page.</p> <p>You are now ready to set up the network file copy service which is used to store resulting encoded files to a NFS server mount for integration with a Content Delivery Network (CDN) or video packaging services.</p> </li>
</ol>
-->

<!--
Comment Type: draft

<h3>Setting up the Network File Copy Service</h3>
-->

<!--
Comment Type: draft

<ol>
<li><p>In the AEM Sidekick, in the <strong>Workflow</strong> list, drag and drop <strong>Process Step</strong> on to your workflow immediately below the FFmpeg transcoding step that you just added earlier.</p> </li>
<li><p>Double-click the process step to open the <strong>Step Properties</strong> dialog box. In the <strong>Common</strong> tab, type a title such as <span class="code">FFmpeg NFS copy service</span>.</p> <p>Optionally, in the <strong>Description</strong> field, type a description that can further help you identify the process, such as <span class="code">Transcoded files are copied to the directories that are specified by the NFS copy service</span>.</p> </li>
<li><p>Click the <strong>Process</strong> tab, and then select <strong>Copy Transcoded Videos to NFS Mount</strong>.</p> </li>
<li><p>Check <strong>Handler Advance</strong> option to turn it on.</p> </li>
<li><p>In the <strong>Arguments</strong> field, create any shared mounts where you want the transcoded video files and thumbnails placed for global deliver. For example, you could use the following format:</p>  <p>The path above copies transcoded files to the mounts <span class="code">/tmp/cq</span> and <span class="code">/tmp/cq2.</span></p> <p>Creating mounts is useful if you intend to deliver video using various options such as streaming.</p> </li>
<li><p>Click <strong>OK</strong>, and then click <strong>Save</strong> near the upper-left corner of the <strong>Workflow</strong> page.</p> <p>After you set up the three services above, you can upload your videos into Assets. </p> </li>
</ol>
-->

