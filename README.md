# **Car Sales Performance Dashboard – README**

## 📌 **Overview**

This project analyzes car sales performance using Power BI. The goal is to track key business metrics such as total sales, average price, cars sold, and year-over-year performance. The project includes data loading, cleaning, KPI creation using DAX, interactive dashboard development, a detailed report, and a presentation built using Gamma.

---

## 📊 **Dataset**

The dataset contains detailed car sales information, including:

* Car model, body style, and color
* Price and quantity sold
* Dealer region
* Company name
* Sales date

The data was imported into Power BI and prepared using Power Query.

---

## 🛠 **Tools & Technologies**

* Power BI Desktop – data modeling, visuals, KPI metrics
* Power Query – data cleaning and transformations
* DAX – KPI and measure creation
* Gamma.app – presentation design
* GitHub – documentation and version control

---

## 🔍 **Project Steps**

### **1. Load Data into Power BI**

* Imported the dataset into Power BI Desktop.
* Validated data types and ensured the Date column supported time-intelligence functions.

### **2. Data Cleaning (Power Query)**

* Removed duplicates and corrected format issues.
* Standardized color, body style, and company names.
* Ensured Price and Date fields were correctly formatted.

### **3. Data Modeling**

* Created a **Calendar Table** for time-based analysis.
* Defined relationships between the sales table and the calendar table.
* Built clean model views for improved performance.

---

## 📐 **4. KPI Development (DAX Measures)**

The following DAX measures were used to calculate YTD, MTD, YOY growth, and variances for sales, average price, and cars sold.

---

### 🧮 **Sales Measures**

```
YTD Total Sales = TOTALYTD(SUM(car_data[Price ($)]),'Calender Table'[Date])

Sales Difference = [YTD Total Sales] - [PYTD Total Sales]

YOY Sales Growth = [Sales Difference] / [PYTD Total Sales]

MTD KPI = CONCATENATE(
    "MTD Total Sales : ",
    FORMAT([MTD Total Sales] / 1000000, "$0.00M")
)
```

---

### 💰 **Average Price Measures**

```
YTD Avg Price = TOTALYTD([Avg Price], 'Calender Table'[Date])

Avg Price Diff = [YTD Avg Price] - [PYTD Avg Price]

YOY Avg Price Growth = [Avg Price Diff] / [PYTD Avg Price]

MTD Avg Price KPI = CONCATENATE(
    "MTD Avg Price : ",
    FORMAT([MTD Avg Price] / 1000, "$0.00K")
)
```

---

### 🚗 **Cars Sold Measures**

```
YTD Cars Sold = TOTALYTD(COUNT(car_data[Car_id]), 'Calender Table'[Date])

Cars Sold Diff = [YTD Cars Sold] - [PYTD Cars Sold]

YOY Car Sold Growth = [Cars Sold Diff] / [YTD Cars Sold]

MTD Cars Sold KPI = CONCATENATE(
    "MTD Cars Sold : ",
    FORMAT([MTD Cars Sold] / 1000, "$0.00K")
)
```

---

## 📊 **5. Dashboard Overview**

The Power BI dashboard highlights major KPIs and insights.

### **Key Metrics**

* Total customers (cars sold)
* YTD & MTD sales
* YOY growth metrics
* Average price trends
* Cars sold breakdown

### **Visuals Included**

* Weekly YTD Sales Trend – line chart
* Sales by Body Style – pie chart
* Sales by Color – pie chart
* Cars Sold by Region – map
* Company-wise YTD Sales – table
* Full Sales Detail Table – all transactional data

### **Interactive Slicers**

* Body style
* Color
* Dealer region
* Company
* Date

---

## 📈 **6. Results & Insights**

* Identified top-performing car models and body styles.
* Analyzed color preferences and their impact on sales.
* Highlighted regions with the highest sales.
* YOY trends helped identify growth areas and performance gaps.
* KPIs provided visibility into sales, pricing, and dealership performance.

---

## ▶ **7. How to Run This Project**

### **1. Download the PBIX File**

Open it in **Power BI Desktop**.

### **2. Refresh the Data**

Power Query will automatically run all transformations.

### **3. Explore the Dashboard**

Use slicers to filter by region, company, body style, color, or date.

### **4. View the Report & PPT**

* Open the included PDF project report.
* Review the Gamma presentation link for summarized insights.

---

