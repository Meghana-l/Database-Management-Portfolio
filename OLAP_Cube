# 📊 OLAP Cube Project – AdventureWorksDW Analysis

This project demonstrates the development of an OLAP cube using **SQL Server Analysis Services (SSAS)** with the **AdventureWorksDW** dataset. The goal was to design dimensions, build hierarchies, define relationships, and visualize the cube data using Excel.

---

## 📁 Project Files

- 🔹 `OLAP_LAB.zip`  
  Contains the complete Visual Studio solution folder with:
  - `OLAP_Lab.sln` – The main solution file
  - All necessary SSAS components: cube, dimensions, data source views

- 🔹 `OLAP_Client.xlsx`  
  Excel workbook used to connect to the deployed cube and perform OLAP analysis using pivot tables.

---

## 🛠 Tools Used

- Visual Studio (SSDT – SQL Server Data Tools)
- SQL Server Analysis Services (Multidimensional)
- SQL Server Management Studio (SSMS)
- Microsoft Excel
- AdventureWorksDW sample database

---

## 🔧 Key Steps Performed

### 1. **Setup**
- Configured the `sa` SQL Server login.
- Attached the `AdventureWorksDW` database to the local SQL Server instance.
- Created a new SSAS project: `OLAP_Lab`.

### 2. **Data Source & DSV**
- Defined a data source pointing to `AdventureWorksDW`.
- Created a Data Source View including:
  - `Customer`, `Product`, `Date`, `Geography`, `InternetSales`.

### 3. **Cube and Dimensions**
- Built the cube `Cube_Internet_Sales`.
- Created dimensions for `Customer`, `Product`, and `Date`.
- Added relevant attributes to each dimension and renamed them for clarity.
- Defined hierarchies:
  - **Product Model Line**: Product Line → Model Name → Product Name
  - **Calendar Date**: Year → Semester → Quarter → Month → Date
  - **Customer Geography**: Country → State → City

### 4. **Optimizations**
- Defined **composite key columns** and **name columns** for accurate grouping.
- Added **named calculations** like:
  - `FullName` (Customer)
  - `ProductLineName` (Product)
  - `SimpleDate` (Date)
- Organized attributes into display folders (e.g., `Location`, `Demographic`, `Stocking`, etc.).
- Defined **attribute relationships** to improve performance.

### 5. **Deployment & Reporting**
- Deployed the OLAP cube to the local Analysis Server.
- Connected Excel to the cube using **Pivot Tables**.
- Performed multi-dimensional analysis on sales, geography, and time.

---

## 📊 Excel Pivot Table Report

Open `OLAP_Client.xlsx` to explore:
- Sales amount by Product Line and Calendar Quarter
- Customer location-based breakdowns
- Time-based trends and drill-downs across hierarchies

---

## ✅ Summary

This project reflects my practical understanding of OLAP modeling, cube design, dimensional analysis, and client-side reporting using Excel. All files are original and the cube was built entirely by me following best practices.

