---
title: Request Analysis Script
seo-title: Request Analysis Script
description: The request analysis script is made to ease the analysis of the access.log files producing a readable report for later processing
seo-description: The request analysis script is made to ease the analysis of the access.log files producing a readable report for later processing
uuid: ba85e82f-30ef-46e0-9f84-ddbad3d181be
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 931f5913-a216-4d5c-b587-874e89724764
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
