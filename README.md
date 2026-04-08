# 📊 Amazon Sales Dashboard - Power BI

## Overview

This project presents a **visual-centric Power BI dashboard** built to
analyze Amazon product sales and reviews.\
The focus of the dashboard is **clear storytelling, strong UX/UI design,
and interactive analytics**.

The report allows users to quickly evaluate **sales performance, product
category contribution, and review trends** while dynamically filtering
insights by category, quarter, and Top N products.

------------------------------------------------------------------------

## Dashboard Preview

![Dashboard Preview](/images/View.png)

------------------------------------------------------------------------

## Key Insights from the Dashboard

### 💰 Sales Performance

-   **\$2.18M YTD Sales** generated across product categories.
-   **+33.5% YoY growth**, indicating strong upward sales momentum.
-   **QTD Sales: \$811K**, showing sustained quarterly demand.

### 📦 Product Performance

-   **Men Shoes dominate sales**, contributing **43.18% of total YTD
    revenue**.
-   Camera and Men Clothes categories are the **second and third
    strongest contributors**.
-   Lower-performing categories like **Mobile Accessories contribute
    under 2%**, highlighting potential optimization opportunities.

### ⭐ Customer Engagement

-   **19.42M product reviews** across the catalog.
-   **Reviews declined by 12.5% YoY**, indicating potential changes in
    customer engagement or review activity.

### 📈 Trend Patterns

-   Sales show a **strong upward trend toward the end of the year**,
    suggesting seasonal demand peaks.
-   Weekly sales patterns reveal **periodic spikes**, indicating
    promotional or high-demand periods.

------------------------------------------------------------------------

## Dashboard Features

### 🎯 KPI Summary Cards

-   YTD Sales
-   QTD Sales
-   YTD Products Sold
-   YTD Reviews
-   **Year-over-Year comparison indicators**
-   Positive/negative growth highlighted using **conditional
    formatting**.

------------------------------------------------------------------------

### 📈 Time Trend Analysis

-   **Monthly Sales Trend**
-   **Weekly Sales Distribution**
-   Dynamic titles update based on applied filters.

------------------------------------------------------------------------

### 📊 Product Analysis

-   **Top Product Categories by YTD Sales**
-   **Top Selling Products**
-   **Top Reviewed Products**

These visuals help quickly identify **best performing categories and
products**.

------------------------------------------------------------------------

### 🔎 Interactive Filters

-   **Category slicer**
-   **Quarter slicer**
-   **Top N slicer** for dynamically ranking products

Users can switch between **Top 5 / Top 10 / Top 15 products**.

------------------------------------------------------------------------

### 🧠 Custom Analytics Tooltips

The dashboard includes **custom report tooltips** that act as a **mini
analytical panel** when hovering over products.

Tooltip displays: - Product sales - YoY growth - Total reviews -
Quarterly sales trend

![Tooltip Preview](/images/Tooltip.png)

------------------------------------------------------------------------

### ⏱ Data Freshness Indicator

A **dynamic "Last Refreshed" timestamp** is included to show when the
dataset was last updated, helping users trust the recency of the
insights.

------------------------------------------------------------------------

## DAX Measures Used

### Total Sales

``` dax
Total Sales =
SUM(Amazon_Data[Price(Dollar)])
```

### Total Sales Last Year

``` dax
Total Sales LY =
CALCULATE([Total Sales], SAMEPERIODLASTYEAR(Dim_Date[Date]))
```

### YoY Growth

``` dax
YTD Sales YOY % =
DIVIDE([Total YTD] - [Total YTD LY], [Total YTD LY])
```

### KPI Label with Indicator

``` dax
Sales KPI Label =
VAR yoy = [YTD Sales YOY %]
RETURN
IF(
    [YTD Sales YOY %] >= 0,
    [Sales YTD Icon] & " +" & FORMAT([YTD Sales YOY %], "0.0%") & " vs LY",
    [Sales YTD Icon] & " " & FORMAT([YTD Sales YOY %], "0.0%") & " vs LY"
)
```

### Dynamic Chart Title

``` dax
Sales Trend Title =
"Total Sales By Month - Category: "
& [Selected Category]
& " | Quarter: "
& [Selected Quarter]
```

------------------------------------------------------------------------

## Tools & Technologies

-   **Power BI**
-   **DAX**
-   **Power Query**
-   **Data Visualization & Dashboard Design**
-   **UX/UI Dashboard Principles**

------------------------------------------------------------------------

## Project Focus

This project demonstrates:

-   Visual storytelling with data
-   Clean and structured dashboard design
-   Interactive analytics using slicers and tooltips
-   Practical DAX implementation for business insights
-   User-focused dashboard experience

------------------------------------------------------------------------

