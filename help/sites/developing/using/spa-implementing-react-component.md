---
title: Implementing a React Component for SPA
seo-title: Implementing a React Component for SPA
description: This article presents an example of how to adapt a simple, existing React component to work with the AEM SPA Editor.
seo-description: This article presents an example of how to adapt a simple, existing React component to work with the AEM SPA Editor.
uuid: 8a2ff996-e8ce-4171-978c-5a2f2aa7310d
contentOwner: bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: spa
content-type: reference
discoiquuid: c413176e-69d7-4f0f-9eda-d13b83d1975a
index: y
internal: n
snippet: y
---

# Implementing a React Component for SPA{#implementing-a-react-component-for-spa}

Single page applications (SPAs) can offer compelling experiences for website users. Developers want to be able to build sites using SPA frameworks and authors want to seamlessly edit content within AEM for a site built using SPA frameworks.

The SPA authoring feature offers a comprehensive solution for supporting SPAs within AEM. This article presents an example of how to adapt a simple, existing React component to work with the AEM SPA Editor.

## Introduction {#introduction}

Thanks to the simple and lightweight contract that is required by AEM and established between the SPA and the SPA Editor, taking an existing Javascript application and adapting it for use with an SPA in AEM is a straightforward matter.

This article illustrates the example of the weather component on the We.Retail Journal sample SPA.

You should be familiar with the [structure of an SPA application for AEM](../../../sites/developing/using/spa-getting-started-react.md) before reading this article.

## The Weather Component {#the-weather-component}

The weather component is found in the top-left of the We.Retail Journal app. It displays the current weather of a defined location, pulling weather data dynamically.

### Using the Weather Widget {#using-the-weather-widget}

![](assets/screen_shot_2018-06-08at143224.png)

When authoring content of the SPA in the SPA Editor, the weather component appears as any other AEM component, complete with a toolbar, and is editable.

![](assets/screen_shot_2018-06-08at143304.png)

The city can be updated in a dialog just like any other AEM component.

![](assets/screen_shot_2018-06-08at143446.png)

The change is persisted and the component updates itself automatically with new weather data.

![](assets/screen_shot_2018-06-08at143524.png) 

### Weather Component Implementation {#weather-component-implementation}

The weather component is actually based on a publicly-available React component, called [React Open Weather](https://www.npmjs.com/package/react-open-weather), that has been adapted to work as a component within the We.Retail Journal sample SPA application.

The following are snippets of the NPM documentation of the usage of the React Open Weather component.

![](assets/screen_shot_2018-06-08at144723.png) ![](assets/screen_shot_2018-06-08at144215.png)

Reviewing the code of the customized weather component ( `Weather.js`) in the We.Retail Journal application:

* **Line 16**: The React Open Weather widget is loaded as required.
* **Line 46**: The `MapTo` function relates this React component to a corresponding AEM component so that it can be edited in the SPA Editor.

* **Lines 22-29**: The `EditConfig` is defined, checking if the city has been populated and defining the value if empty.

* **Lines 31-44**: The Weather component extends the `Component` class and provides the required data as defined in the NPM usage documentation for the React Open Weather component and renders the component.

```
/*~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
 ~ Copyright 2018 Adobe Systems Incorporated
 ~
 ~ Licensed under the Apache License, Version 2.0 (the "License");
 ~ you may not use this file except in compliance with the License.
 ~ You may obtain a copy of the License at
 ~
 ~     http://www.apache.org/licenses/LICENSE-2.0
 ~
 ~ Unless required by applicable law or agreed to in writing, software
 ~ distributed under the License is distributed on an "AS IS" BASIS,
 ~ WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 ~ See the License for the specific language governing permissions and
 ~ limitations under the License.
 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~*/
import React, {Component} from 'react';
import ReactWeather from 'react-open-weather';
import {MapTo} from '@adobe/cq-react-editable-components';

require('./Weather.css');

const WeatherEditConfig = {

    emptyLabel: 'Weather',

    isEmpty: function() {
        return !this.props || !this.props.cq_model || !this.props.cq_model.city || this.props.cq_model.city.trim().length < 1;
    }
};

class Weather extends Component {

    render() {
        let apiKey = "12345678901234567890";
        let city;

        if (this.props.cq_model) {
            city = this.props.cq_model.city;
            return <ReactWeather key={'react-weather' + Date.now()} forecast="today" apikey={apiKey} type="city" city={city} />
        }

        return null;
    }
}

MapTo('we-retail-journal/global/components/weather')(Weather, WeatherEditConfig);

```

Although a back-end component must already exist, the front-end developer can leverage the React Open Weather component in the We.Retail Journal SPA with very little coding.

## Next Step {#next-step}

For further information about developing SPAs for AEM see the article [Developing SPAs for AEM](../../../sites/developing/using/spa-architecture.md).

>[!MORE_LIKE_THIS]
>
>* [Using the SPA Editor framework with AEM Sites](https://helpx.adobe.com/experience-manager/kt/sites/using/spa-editor-framework-feature-video-use.html)
>* [Overview of Single Page Applications (SPA)](https://helpx.adobe.com/experience-manager/kt/sites/using/spa-overview-feature-video.html)
>* [Getting Started with the AEM SPA Editor - Hello World Tutorial](https://helpx.adobe.com/experience-manager/kt/sites/using/spa-editor-helloworld-tutorial-use.html)
>* [Understanding SPA components in AEM SPA Editor](https://helpx.adobe.com/experience-manager/kt/sites/using/spa-editor-components-technical-video-understand.html)
>* [do not publish](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/chapter-0-project-setup.html)
>* [Template DO NOT PUBLISH](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-spa-wknd-tutorial-develop/react/template.html)
