---
title: Request Analysis Script
seo-title: Request Analysis Script
description: The request analysis script is made to ease the analysis of the access.log files producing a readable report for later processing
seo-description: The request analysis script is made to ease the analysis of the access.log files producing a readable report for later processing
uuid: 3bb77f06-07e6-4f19-8682-fed7a44e6dc9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 436a4dff-fa8d-4b0e-9054-65b507867ff2
index: y
internal: n
snippet: y
---

# Request Analysis Script{#request-analysis-script}

## Download {#download}

This script is made to ease the analysis of the access.log files producing a readable report for later processing.

[Get File](assets/analyse-access.sh)

## Description {#description}

This script is made to ease the analysis of the access.log files producing a readable report for later processing.

It produces the overall requests number, GET vs POST, Request distribution over time and more.

The output will be in Markdown syntax therefore it will be easier to convert it to PDFs with tools like pandoc or showing it in a browser with plugins like markdown viewer.

It can analyse as well custom path provided on the command line.

Taking from the comment within the file that will tell you how to run it:

Analyse CQ access.log extrapolating various informations and producing a MarkDown output on stdout

## Usage {#usage}

# ./analyse-access.sh access.log.2013-&#42;

#

# you can provide additional custom paths to analyse on the command line

# ./analyse-access.sh access.log.2013-&#42; /my/custom/path/1 /my/custom/path/2

#

# you can save the output by a simple piping

# ./analyse-access.sh access.log.2013-&#42; | tee yr2013.md
