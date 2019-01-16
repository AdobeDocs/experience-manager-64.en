---
title: Request Analysis Script
seo-title: Request Analysis Script
description: null
seo-description: The request analysis script is made to ease the analysis of the access.log files producing a readable report for later processing
uuid: ae819ec3-f6b2-4452-aae7-b7217641af17
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: e60e222f-841b-46c8-9f7d-db659b69a704
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Request Analysis Script{#request-analysis-script}

## Download {#download}

[This script is made to ease the analysis of the access.log files producing a readable report for later processing.](assets/analyse-access.sh)

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
