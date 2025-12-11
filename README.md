
# Car Sales Data Analytics Project – Power BI
Overview

This project demonstrates a complete end-to-end data analytics workflow using Power BI. It includes loading and cleaning a dataset, building a data model, creating DAX measures, designing an interactive dashboard, generating insights, and preparing a report and presentation.
The goal is to analyse car sales performance and provide clear, actionable insights to support decision-making.

Dataset

Source: Car Sales Dataset (Excel/CSV)
Contains fields such as:

Car ID, Date, Dealer Name

Company, Model, Body Style, Color

Engine, Transmission, Region

Price ($), Customer Details

Data Cleaning Performed

Removed duplicates and empty rows

Fixed incorrect data types (date, numeric, text)

Renamed and standardized columns

Created a Calendar table for time-intelligence

Built structured relationships for accurate filtering

Tools Used

Power BI Desktop – Data modeling, DAX, dashboards

Power Query – Data cleaning and transformation

Gamma – Presentation creation

Excel / CSV – Source dataset

GitHub – Documentation and version control

Project Steps
1. Load the Dataset

Imported the raw dataset into Power BI and reviewed structure and data quality.

2. Clean the Data in Power Query

Removed duplicates and null rows

Standardized naming conventions

Converted column types

Created a date table for YTD/MTD/YOY calculations

3. Build the Data Model

Designed a star schema

Established relationships

Marked Calendar table as the official date table

Ensured proper filter direction for visuals

4. Create DAX Measures

Developed time-intelligence measures for YTD, MTD, YOY and comparison metrics.

(See DAX Highlights section below.)

5. Build the Dashboard

Created two interactive pages:

Overview Page

YTD & MTD KPI cards

YOY performance indicators

Weekly sales trend

Sales by Body Style

Sales by Color

Regional sales map

Company-wise YTD summary

Slicers for Body Style, Dealer, Engine, Transmission

Details Page

Full transaction-level table

Includes model, body style, color, price, region, and sale date

Supports drill-down and operational checks

6. Add Page Navigation

Added buttons for easy movement between the Overview and Details pages, creating a clean and intuitive experience.

7. Create Report & Presentation

Exported a written report summarising insights

Designed a clean PPT-style presentation using Gamma

Dashboard

The dashboard provides a quick and interactive view of performance, helping users understand trends, compare companies, analyse customer preferences, and review detailed records.

It is designed to support decisions in sales planning, inventory management, and marketing strategy.

DAX Highlights

These are some of the key DAX measures used in this project:

-- Sales Measures
YTD Total Sales = TOTALYTD(SUM(car_data[Price ($)]), 'Calender Table'[Date])
Sales Difference = [YTD Total Sales] - [PYTD Total Sales]
YOY Sales Growth = [Sales Difference] / [PYTD Total Sales]
MTD KPI = CONCATENATE("MTD Total Sales : ", FORMAT([MTD Total Sales] / 1000000, "$0.00M"))

-- Average Price Measures
YTD Avg Price = TOTALYTD([Avg Price], 'Calender Table'[Date])
Avg Price Diff = [YTD Avg Price] - [PYTD Avg Price]
YOY Avg Price Growth = [Avg Price Diff] / [PYTD Avg Price]
MTD Avg Price KPI = CONCATENATE("MTD Avg Price : ", FORMAT([MTD Avg Price] / 1000, "$0.00K"))

-- Cars Sold Measures
YTD Cars Sold = TOTALYTD(COUNT(car_data[Car_id]), 'Calender Table'[Date])
Cars Sold Diff = [YTD Cars Sold] - [PYTD Cars Sold]
YOY Car Sold Growth = [Cars Sold Diff] / [YTD Cars Sold]
MTD Cars Sold KPI = CONCATENATE("MTD Cars Sold : ", FORMAT([MTD Cars Sold] / 1000, "$0.00K"))

Results

Clear visibility into YTD, MTD and YOY sales trends

Identification of top-selling body styles and colors

Understanding of strong and weak performing regions

Company-wise comparison to evaluate brand contribution

Insight into customer preferences and purchasing patterns

Easy drill-down for transaction-level validation

How to Run This Project
To View the Dashboard

Download the Car_Sales_Dashboard.pbix file

Open it in Power BI Desktop

Use slicers and navigation buttons to explore insights

To View the Report

Open the PDF included in the repository.

To View the Presentation

Open the Gamma presentation link or PPT file
