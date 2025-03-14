---
title: "Use a Chart with a REST Data Source"
url: /howto8/front-end/charts-basic-rest/
weight: 60
tags: ["Charts", "Widgets", "REST", "Studio Pro"]
---

## 1 Introduction

With the Charts widgets, you can use data from a REST Service to plot graphs.

This how-to teaches you how to do the following:

* Publish a REST API
* Use a REST endpoint as a data source for the Charts widget

## 2 Prerequisites

Before starting this how-to, make sure you have completed the following prerequisites:

* Create an app
* Import the latest [Charts Widgets](/appstore/widgets/charts/) from the Mendix Marketplace

## 3 Setting up Data to be Exposed by a REST Endpoint

Mendix allows you to publish REST Web services natively from Studio Pro. Using these capabilities you can publish a REST service and use it in our Charts widget to plot graphs.

To create an Area Chart with data from a REST service, follow these steps:

{{% alert color="info" %}}

For more information on publishing a REST API refer to this Mendix document: [Published REST Operation](/refguide8/published-rest-operation/)

{{% /alert %}}

1. Create a new module in your app.
1. Rename the module to *ChartsREST*.
1. Open the Domain model.
1. Create **Value** and **Series** entities with the attributes and association shown in the picture below.
    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-domain.png" alt="Chart Rest Domain" >}}  
1. Right-click **Value** and select **Generate overview pages...**.
    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-create/charts-rest-generate-overview-pages.png" alt="Chart Rest Enter Data" >}}
1. Add the **Value_NewEdit** page generated to your navigation.
1. Run the app.
1. In your browser, open the NewEdit page.
1. Add values and series by entering data in the appropriate fields.

## 4 Publishing the Service

To use data from a model in the REST service, you need to create a JSON structure.

### 4.1 Creating the Structure

1. Create a **JSON Structure**  
    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/chart-series-json-structure.png" alt="Charts Rest MD" >}}

### 4.2 Configuring the REST Service

To configure the REST service, follow these steps:

1. Add **Published REST service**.
    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-publish.png" alt="Charts Rest Publish" >}}

1. Add REST Service **Microflow**.
    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-microflow.png" alt="Charts Rest Microflow" >}}

1. Add **Export mapping**.
    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-export-mapping.png" alt="Charts Rest Export Mapping" >}}

## 5 Using REST as a Data Source

To use the REST Data source endpoint in your chart, follow these steps:

1. Create a page in your app containing an **Area chart** widget.

1. Double click the **Area chart** widget.

1. In the tab **Chart properties**, add a new chart **Series** property.

1. Add **Series name** and **Entity**.

1. Select **Data source** REST endpoint.

    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-series.png" alt="Chart Rest Series" >}}

1. Add the **REST URL**.

    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-url.png" alt="Chart Rest URL" >}}

1. In the tab **Data points**, select the **X-axis data attribute** and the **Y-axis data attribute**.

    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-create/charts-data-points.png" alt="select Data Points" >}}  

1. Add Parameters to the REST Request. The **contextId**, **series name** are provided by default.

    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-parameters.png" alt="select Data Points" >}} 

1. Run your app and view the chart.

    {{< figure src="/attachments/howto8/front-end/charts-tutorials/charts-basic-rest/charts-rest-area-chart.png" alt="Show Chart" >}}

## 6 Read More

* [Use Chart Data Source REST](/howto8/front-end/charts-basic-create/)
* [Use Any Chart](/howto8/front-end/charts-any-usage/)
* [Use Theme Charts](/howto8/front-end/charts-theme/)
