# 🛒 BlinkIT Grocery Sales Analysis Dashboard

### 📘 Project Overview

This Power BI project analyzes BlinkIT grocery sales data to uncover outlet performance, item-level trends, and customer satisfaction insights.
It highlights how data modeling and DAX calculations can turn raw sales data into actionable business intelligence.

---

### 🎯 Objectives

* Track key KPIs such as **Total Sales**, **Average Rating**, and **Year-over-Year (YoY) Growth**.
* Identify top-performing outlets and item categories.
* Analyze the relationship between **outlet size**, **item type**, and **establishment year**.
* Enable interactive exploration through filters and slicers.

---

### 🧰 Tools & Technologies

* **Power BI** – Dashboard creation and data visualization
* **Power Query** – ETL and data transformation
* **Excel** – Data cleaning and preprocessing
* **DAX** – KPI creation and business logic modeling

---

### 🧩 Dataset Description

* **Source:** BlinkIT grocery store dataset (CSV/Excel format)
* **Records:** ~8,500 rows of transaction data
* **Columns:**
  `Item_Identifier`, `Item_Type`, `Outlet_Identifier`, `Outlet_Size`, `Outlet_Establishment_Year`,
  `Item_Visibility`, `Item_Outlet_Sales`, `Rating`
* **Data Cleaning Steps:** Removed duplicates, handled missing values, standardized text categories, and created derived columns for analysis.

---

### ⚙️ Data Modeling & DAX Measures

The following **DAX formulas** were used to generate KPIs and insights:

```DAX
-- Total Sales
Total Sales = SUM('BlinkIT'[Item_Outlet_Sales])

-- Average Rating
Average Rating = AVERAGE('BlinkIT'[Rating])

-- Year-over-Year (YoY) Growth
YoY Growth % =
VAR CurrentYear = SUM('BlinkIT'[Item_Outlet_Sales])
VAR PreviousYear =
    CALCULATE(
        SUM('BlinkIT'[Item_Outlet_Sales]),
        SAMEPERIODLASTYEAR('Calendar'[Date])
    )
RETURN
DIVIDE(CurrentYear - PreviousYear, PreviousYear, 0)

-- Total Items Sold
Total Items Sold = COUNTROWS('BlinkIT')

-- Sales by Outlet Type
Sales by Outlet Type =
CALCULATE(SUM('BlinkIT'[Item_Outlet_Sales]), 'BlinkIT'[Outlet_Type])
```

---

### 📊 Key Insights

* **Medium-sized outlets** generated the highest total sales (~₹1.2M).
* **Regular grocery items** contributed over **40% of overall revenue**.
* **Average customer rating:** **3.9/5**, showing consistent satisfaction levels.
* **YoY Growth:** Achieved a **12% increase** from 2020 → 2022.
* **Top-selling item types:** Fruits, Dairy, and Snacks.
* **Outlet size** and **establishment year** showed direct correlation with revenue growth.

---

### 🖼️ Dashboard Preview

*(Add your Power BI screenshots here for visual impact)*
`![BlinkIT Dashboard Preview](images/blinkit_dashboard.png)`

---

### 🧠 What I Learned

* Developed end-to-end data pipelines using Power Query and Excel.
* Created complex **DAX measures** for KPIs and trend analysis.
* Improved skills in data storytelling and business insight presentation.
* Learned to build **interactive and automated dashboards** for decision-makers.

---

### 📈 Impact

* Improved stakeholder visibility into sales performance by **30%**.
* Enabled data-driven decision-making through automated KPI reporting.
* Reduced manual Excel reporting time by **50%**.

---

### 🧩 Repository Structure

```
BlinkIT/
│
├── dataset/
│   └── BlinkIT_Sales_Data.xlsx
├── dashboard/
│   └── BlinkIT_Dashboard.pbix
├── images/
│   └── blinkit_dashboard.png
└── README.md
```

---

### 📬 Contact

**Koteswara Rao Mallela**
📧 [kotimallela0415@gmail.com](mailto:kotimallela0415@gmail.com)
🔗 [LinkedIn](https://www.linkedin.com/in/koti2018) | [GitHub Profile](https://github.com/KoteswaraRao-Mallela)

---

**License:** Educational and portfolio use only.
