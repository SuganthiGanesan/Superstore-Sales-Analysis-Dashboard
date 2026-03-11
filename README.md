# 🏬 Superstore Sales Dashboard

![Dashboard Screenshot](dashboard.png)

This repository contains a comprehensive **Power BI Sales Dashboard** built to analyze the performance of a Superstore. The dashboard leverages advanced Power BI features including Row-Level Security (RLS), Page Navigation, Bookmarks, Drill-through, and complex DAX measures to provide secure, interactive, and deep insights into sales trends, profitability, and regional performance.

## 🚀 Live Dashboard

<!-- Add a link if you have published this online -->
[View Live Dashboard](#) *(Optional: Add your Power BI Service link here)*

## ⚡ Advanced Power BI Features Implemented

### 🔐 Row-Level Security (RLS)
- **Dynamic Data Access:** Implemented RLS to restrict data access based on user roles
- **Role Display:** Shows "No Access" for unauthorized users/regions
- **Dynamic PN (Page Navigation):** West region context applied for personalized viewing
- *Benefit: Ensures sales managers only see data relevant to their region*

### 📑 Page Navigation & Bookmarks
- **Dynamic Page Navigation:** Seamless transition between different dashboard views
- **Bookmarked Views:** Saved specific filter states and visual configurations for quick insights
- *Benefit: Enhanced user experience with guided analytics*

### 🔍 Drill-Through Functionality
- **Contextual Deep-Dive:** Right-click any data point to drill through to detailed analysis pages
- **Cross-Filtering:** Maintains context when navigating from summary to detail
- *Benefit: Enables root-cause analysis without cluttering the main dashboard*

### 📊 Advanced DAX Measures
```dax
// Sample DAX Measures Used:
Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))

Parallel Period Yr = CALCULATE([Total Sales], PARALLELPERIOD('Date'[Date], -1, YEAR))

Profit Margin % = DIVIDE([Total Profit], [Total Sales], 0)

## ✨ Key Performance Indicators (KPIs)

| Metric | Value | DAX Calculation |
|--------|-------|-----------------|
| **Total Sales** | 2.30M | `SUM(Sales[Amount])` |
| **Sales LY (Last Year)** | 1.56M | `CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Date'[Date]))` |
| **Parallel Period (YoY)** | 2.09M | `CALCULATE([Total Sales], PARALLELPERIOD('Date'[Date], -1, YEAR))` |
| **Total Profit** | 286.40K | `SUM(Sales[Profit])` |
| **Average Profit** | 28.66 | `AVERAGE(Sales[Profit])` |

##🛠️ Technical Implementation
Power BI Features Used:
✅ Row-Level Security (RLS) - Role-based data access

✅ Page Navigation - Multi-page dashboard with buttons

✅ Bookmarks - Saved views for different analysis scenarios

✅ Drill-Through - Detailed transaction analysis

✅ DAX Measures - Time intelligence, calculations, KPIs

✅ Tooltips - Hover-based detailed information

✅ Report Themes - Consistent color scheme (Orange/Blue/Green)

📁 Data Model

┌─────────────┐     ┌─────────────┐
│   Sales     │─────│    Date     │
│ (Fact Table)│     │ (Dimension) │
└─────────────┘     └─────────────┘
       │                    │
       │                    │
┌──────▼──────┐     ┌───────▼──────┐
│  Product    │     │   Region     │
│(Dimension)  │     │ (Dimension)  │
└─────────────┘     └──────────────┘
                           │
                           │
                     ┌─────▼─────┐
                     │   RLS     │
                     │  Tables   │
                     └───────────┘

📁 Dataset Information
The dashboard uses the classic "Sample Superstore" dataset, containing information on:

- Orders and Sales Transactions

- Product Categories and Sub-Categories

- Customer Segments

- Geographic Regions and States

- Profit Margins

🎯 Project Objectives

- Create an executive-level business dashboard for quick performance assessment

- Analyze sales trends and patterns across different time periods

- Evaluate product category and regional performance

- Track profitability alongside revenue metrics

- Enable year-over-year comparison for growth analysis

- Implement enterprise-level security with RLS
