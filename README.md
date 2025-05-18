# 📊 Power-BI-Capstone-Projects

This repository contains two comprehensive Power BI projects designed to deliver actionable insights into global sales operations. These projects demonstrate my hands-on expertise in data modeling, ETL pipelines, Snowflake integration, DAX, Power BI Service features, and real-world business analysis.

---

## 🚗 Project 1: Dream Craft Sales Analytics Dashboard (Power BI + Snowflake)

### 🏢 Scenario
Dream Craft is a multinational company specializing in miniaturized classic car models. The client faced challenges consolidating sales data across multiple geographic regions. To solve this, I built a centralized data warehouse using Snowflake and developed rich, interactive dashboards using Power BI.

### 🔧 Technical Implementation

#### 🔹 Database Design (Snowflake):
- Designed and implemented a normalized ER model comprising:
  - **Tables**: Offices, Employees, Customers, ProductLines, Products, Orders, OrderDetails, Payments
  - **Relationships**: Used foreign keys for referential integrity across sales, employees, and products
- **Transformations & Enhancements**:
  - Created calculated fields like `Markup_Percentage = (MSRP - BuyPrice)/BuyPrice` and `Total_Cost = QuantityOrdered * UnitPrice`
  - Filled null values with defaults (e.g., 'NA', 0)
  - Removed high-null columns like `AddressLine2`, `HTMLDescription`

#### 🔹 SQL Logic:
- Views:
  - `Sale_Details`: Consolidates sales with product and customer data
  - `High_Value_Customers`: Filters customers with high credit limits
- Stored Procedures:
  - `GET_MARKUP_HIGHER(value)`: Returns products with markup above a given threshold
  - `GET_HIGHCREDIT_CUSTOMER(value)`: Lists customers exceeding a credit limit

#### 📈 Power BI Visualizations:
- **KPI Charts**: Card for Total Revenue, Orders, Customers
- **Charts**:
  - Gauge chart: Markup Percentage
  - Tree map: Customer count by country
  - Stacked bar: Top 10 Customers by Revenue
  - Column chart: Monthly Revenue trends
  - Donut & Pie: Shipment Status, Yearly Order Count
- **Interactive Features**:
  - Slicers for Year, Country, Product Line
  - Q&A feature trained for natural language queries
  - Dashboard pinned tiles from multiple reports

#### ☁️ Power BI Service:
- Published reports with:
  - **Lineage View**
  - **Usage Metrics**
  - Axis customization & Data labels
  - Dashboard with pinned visuals

---

## 🛒 Project 2: Global Super Store Sales Dashboard (Power BI + RLS)

### 🌍 Scenario
This project involved building a report for Global Super Store, a multi-category international retailer. The objective was to analyze sales performance and customer behavior using historical sales data to improve planning and business strategies.

### 🔧 Technical Implementation

#### 📊 Data Preparation:
- Loaded multi-sheet Excel data and transformed it using **Power Query Editor**
- Built relationships between fact and dimension tables (Orders, Customers, Products, Categories, Regions)

#### 🧮 DAX Measures:
- `Total Sales = SUM(Sales[SalesAmount])`
- `Profit = SUM(Sales[Profit])`
- `Profit Ratio = DIVIDE(SUM(Profit), SUM(SalesAmount))`

#### 📈 Visualizations:
- Page 1: **Sales Summary**
  - Category & Subcategory analysis using bar/column charts
  - Profit breakdown by Region, Year, and Manager
  - Slicers for Year, Region, Market
- Page 2: **Q&A Insights**
  - Natural language Q&A visual trained with synonyms:
    - Revenue = Sales
    - Income = Profit
    - Income Percentage = Profit Ratio

#### 🔐 Row-Level Security (RLS):
- Implemented dynamic RLS rules to restrict manager-level access based on their assigned markets
- Created RLS roles and tested role-view access within Power BI Service

#### ☁️ Power BI Service:
- Published reports to a shared workspace
- Assigned viewer access to users with role-based permissions
- Enabled:
  - **Usage metrics**
  - **Lineage tracking**
  - **Workspace collaboration**

---

## 🛠️ Tools & Technologies Used

| Tool            | Usage                                  |
|-----------------|-----------------------------------------|
| Power BI Desktop| Dashboard development, DAX, Q&A         |
| Power BI Service| Report publishing, RLS, dashboarding    |
| Snowflake       | Cloud data warehouse, SQL scripting     |
| SQL             | Table creation, views, procedures       |
| Power Query     | Data transformation, filtering          |
| Excel           | Source data for Super Store analysis    |

---

## 📁 Folder Structure

