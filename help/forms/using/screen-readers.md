---
title: Screen readers for HTML5 forms
seo-title: Screen readers for HTML5 forms
description: null
seo-description: Lists the screen readers supported with HTML5 forms.
uuid: 29a4a976-a464-4cdd-a01c-5a52794c5d0a
acrolinxdate: 2016-05-31T06 46 54.177-0400
acrolinxlastcheckedby: vishgupt
acrolinxpagestatus: red
acrolinxreporturl: http //checkstyle.corp.adobe.com 8031/output/en/screen_readers_admin_5e12de0b318c6865_2097_report.xml
acrolinxsentences: 19
acrolinxwords: 319
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 47c9cc18-3e8a-4bac-85bc-5cfd498a70a3
firstpublishqadate: 2013-02-28T07 03 50.265-0500
isreadyforlocalization: false
lastpublishqadate: 2015-06-12T04 29 43.479-0400
publishqadate: 2015-06-12T04 29 43.479-0400
publishqaurl: https //helpx-preview.corp.adobe.com/content/help/en/aem-forms/6-1/html5-forms/screen-readers.html
index: y
internal: n
snippet: y
---

# Screen readers for HTML5 forms{#screen-readers-for-html-forms}

HTML5 forms components render XFA form template to a HTML5 format. All standard browsers supporting HTML5 can render these forms. To support similar data capture experience across PDF and HTML5 forms, the layout of PDF forms is retained in HTML5 forms.

HTML5 forms use standard HTML constructs allowing regular accessibility tools for HTML to be used with these forms. If a form is designed according to the best practices for accessible forms, it works with any supported screen reader. Additionally, such forms are enabled for keyboard navigation.

### Accessibility standards {#accessibility-standards}

HTML5 forms comply to section 508 for accessibility with known exceptions. See [VPAT for HTML5 forms](http://www.adobe.com/mena_en/accessibility/compliance/livecycle-mobile-forms-es4-section-508-vpat.html) for details.

### Certified screen readers for HTML5 forms {#certified-screen-readers-for-html-forms}

* JAWS 14.0 on Microsoft Windows
* VoiceOver on Mac OS X and iPad

#### JAWS {#jaws}

All default keystrokes and shortcuts work for HTML5 forms. For more information on using JAWS, visit [http://www.freedomscientific.com/jaws-hq.asp](http://www.freedomscientific.com/jaws-hq.asp).

#### VoiceOver {#voiceover}

HTML5 forms support all the default keystrokes and gestures of Voice over. For more information on setting up and using VoiceOver, see [http://www.apple.com/accessibility/voiceover/](http://www.apple.com/accessibility/voiceover/).

### Known issues {#known-issues}

* **(Internal Explorer 9 only)** In HTML5 forms, the pages are loaded on demand (dynamically). On-demand page load causes issues with the functioning of screen readers. When focus of the screen reader is on the last field of the page and the user presses tab, instead of setting the focus on the first field of the next page, the screen reader returns focus to the first field of first page of the form. 
* **(Internal Explorer 9 only)** The Date Picker control in HTML5 forms is not fully accessible with keyboard. In the Date Picker control, if you press Up/Down keys multiple times, the Date Picker control closes and focus moves to next/last field.  

* VoiceOver is unable to detect arrow keys on the date widget on iPad safari.

[**Contact Support**](https://www.adobe.com/account/sign-in.supportportal.html)
