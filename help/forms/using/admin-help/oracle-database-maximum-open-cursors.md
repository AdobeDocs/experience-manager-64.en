---
title: Oracle database maximum open cursors threshold
seo-title: Oracle database maximum open cursors threshold
description: Learn about configuring a maximum value for open cursors in Oracle.
seo-description: Learn about configuring a maximum value for open cursors in Oracle.
uuid: c1d20997-f853-4772-b1c6-8cea73221d0a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_aem_forms_database
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d3565776-1b7d-498c-9840-b17f80170d9b
exl-id: ad14ff27-964f-481f-a8ef-052d9cfb7734
---
# Oracle database maximum open cursors threshold {#oracle-database-maximum-open-cursors-threshold}

>[CAUTION]
>
>AEM 6.4 has reached the end of extended support and this documentation is no longer updated. For further details, see our [technical support periods](https://helpx.adobe.com/support/programs/eol-matrix.html). Find the supported versions [here](https://experienceleague.adobe.com/docs/).

To configure a maximum value for open cursors in Oracle, you may have to tune this value to a number that is appropriate to your application. It is evident that under a moderate load, the average cursors open was 2700. It is recommended that you start with an upper limit of 3000. For more information, go to [https://www.orafaq.com/node/758](https://www.orafaq.com/node/758).
