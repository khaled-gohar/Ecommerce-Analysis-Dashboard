# 🛒 Ecommerce-Analysis-Dashboard

This project showcases a complete end-to-end data analysis workflow for Brazilian e-commerce data using **PostgreSQL**, **DBeaver**, and **Power BI**. It focuses on transforming raw transactional data (OLTP) into a structured analytical model (OLAP) entirely within the database using SQL — with clean and meaningful visual insights delivered through a Power BI dashboard.

---

## 🎯 Business Scenario

A simulated business use case that required:

- Extracting and preparing data from a transactional PostgreSQL database.
- Restructuring data for reporting through OLAP modeling.
- Building a Power BI dashboard to monitor performance, analyze customers, and evaluate product trends.
- Answering specific business questions and presenting insights in a PDF report.

---

## 🛠 Tools & Technologies

- **Neon PostgreSQL** – Source and target database
- **DBeaver** – SQL development, schema transformation, and ERD generation
- **SQL** – For data cleaning, joining, and transforming OLTP to OLAP
- **Power BI** – Dashboard creation and data visualization
- **DAX** – For KPIs, RFM segmentation, and calculated fields
- **PDF Report** – Business findings and recommendations

---

## 🧱 Project Workflow

### 1. **Schema Understanding**
- Explored and documented the normalized OLTP schema using **DBeaver**.
- Generated the **ERD** to visualize relationships between tables.

### 2. **Data Cleaning & Transformation**
- Wrote SQL scripts in **DBeaver** to:
  - Clean the data (handle nulls, duplicates, invalid values).
  - Join multiple tables.
  - Derive new fields (order value, customer lifespan, etc.).
- Transformed the OLTP model into an **OLAP star schema** (Fact & Dimension tables).
- Created a **new schema in PostgreSQL** to store the cleaned OLAP tables.

### 3. **Data Modeling & Dashboarding**
- Connected Power BI directly to the **OLAP schema in PostgreSQL**.
- Created calculated columns, DAX measures, and RFM segments.
- Built an interactive dashboard with consistent themes, slicers, filters, and tooltips.
- Documented findings in a **PDF report**.

---

## 🗂 Schema Design: OLTP vs OLAP

### 🔹 OLTP Schema

Normalized source schema from Neon PostgreSQL.

![OLTP ERD](images/erd_oltp.png)


---

### 🔸 OLAP Schema (Star Schema)

Restructured for reporting and analytics with `FactSales` and associated `Dim` tables.

![OLAP ERD](images/erd_olap.png)
*Generated using DBeaver*

| OLTP Table           | OLAP Equivalent          | Purpose                                       |
|----------------------|--------------------------|-----------------------------------------------|
| Orders + Payments    | `fact_sales`             | Central table for transactional facts         |
| Customers            | `dim_customers`          | Customer profile and identity details         |
| Products             | `dim_product`            | Product catalog and metadata                  |
| Sellers              | `dim_sellers`            | Seller information                            |
| Reviews              | `review` *(aggregated)*  | Pre-aggregated average review score per order |
| Payments             | `dim_payment`            | Payment method and type per order             |
| Dates                | `Calendar`               | Date dimension for filtering and trends       |
| RFM Segmentation     | `RFM Table`              | Customer segmentation using RFM scores        |
| Order Metadata       | `order_id_B_table`       | Supplementary order-level detail              |

---

## 📊 Dashboard Overview

The Power BI dashboard includes **3 main pages**:

1. **📈 Summary Performance**
   - KPIs: Total Revenue, Total Orders, AOV
   - Sales trends and heatmaps

2. **👥 Customers**
   - RFM Segmentation
   - Repeat customers, retention trends

3. **📦 Products**
   - Best sellers by category/state
   - Profitability and sales contribution

### Key Features

- **Global Slicers**: Category, State, Date, etc., consistent across all pages
- **Filter Tags**: Easily track and clear applied filters
- **Tooltips**: Show additional insights on hover
- **Consistent UI**: Unified color scheme, font, and layout
- **RFM Analysis**: Segment customers based on Recency, Frequency, and Monetary value
- **PDF Report**: Summarized business insights and recommendations

---

## 🧠 Business Questions Answered

- What are the top-performing product categories?
- Who are the most valuable customers?
- What’s the average order value?
- Which regions contribute most to revenue?
- Are there noticeable seasonality trends?

---

## ✅ Outcomes

- Transformed normalized OLTP data into an OLAP model using SQL only.
- Stored clean Fact and Dimension tables in a new PostgreSQL schema.
- Built a Power BI dashboard directly connected to the OLAP schema.
- Delivered business insights and recommendations in a PDF report.
- Used DBeaver for development and schema documentation.

---

## 📁 Folder Structure
/olis-ecommerce-dashboard
│
├── /images
│ ├── erd_oltp.png
│ └── erd_olap.png
│
├── /sql
│ └── transform_to_olap.sql
│
├── /pdf
│ └── business_insights_report.pdf
│
└── README.md


---

## 🚀 Try It Out

- [Open Power BI Dashboard 🔗](#) *(insert link if available online)*
- [Download PDF Report 📄](pdf/business_insights_report.pdf)

---

## 📌 Future Enhancements

- Automate schema refresh with PostgreSQL functions or cron jobs
- Add user-level access with PostgreSQL roles and views
- Add churn and cohort analysis
- Expand to marketing and operational data

---

## 🙌 Let's Connect

If you found this project interesting or have feedback, feel free to reach out:

- 📧 Email: [your.email@example.com](mailto:your.email@example.com)
- 💼 LinkedIn: [linkedin.com/in/your-profile](https://linkedin.com/in/your-profile)

---


