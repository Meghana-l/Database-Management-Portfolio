# Data Warehousing Project

This folder contains data warehousing work designed and implemented as part of my Database Management coursework.  
The projects demonstrate real-world warehouse design concepts including conceptual modeling, physical modeling, database schema visualization, and advanced dimensional modeling.

---

## 📚 Contents:
- **Conceptual Model Questions:** Business analytics requirements based on which the dimensional model was designed.
- **DataWarehouse_ConceptualModel.xlsx:** Conceptual dimensional model developed using Microsoft Excel.
- **Physical Model :** Full database physical implementation created using SQL Server Management Studio's Table Designer and Diagramming tools.
- **Physical Model Extension:** Extended physical model with advanced many-to-many relationships and indexing.

---

## 🧩 Conceptual Model

The conceptual dimensional model was designed based on the following business requirements:

- **Calculate units sold** by:
  - Year, Semester, Quarter, Month, Week of the Year, Day of the Year, Day of the Week.

- **Calculate units sold** by customer attributes:
  - Customer Name, Customer State, Customer City, Customer Zip, Customer Address Type (road, street, avenue, boulevard, or drive).

- **Calculate units sold and total sales (with and without discounts)** by supplier attributes:
  - Supplier Company Name, Supplier State, Supplier City, Supplier Zip, Number of Products (Categories: 1–15, 15+).

- **Calculate total sales (considering discounts)** by:
  - Product Name, SKU, Product Price Range (1–10, 11–20, 21–30, 40+).

- **Calculate total sales and units sold** by sales representative attributes:
  - Sales Rep Name, State, City, Zip, Title, Salary Range (three custom ranges), Seniority (1–10 years, 10–20 years, 20+ years).

- **Calculate shipping cost** by:
  - Customer State, Customer City, Customer Zip.

- **Calculate Order Quotation Amount, Order Invoice Amount, and Order Material Cost** by:
  - Product Container Type, Product Quality Rating, Product Ingredient Type.

- **Slowly Changing Dimensions (SCD):**  
  Certain attributes across dimensional tables are tracked using SCD Type II methodology, with additional housekeeping columns (`StartDate`, `EndDate`, `ChangeReason`) to maintain history.

Refer DataWarehouse_ConceptualModel.xlsx to view the Conceptual model
---

## 🏗️ Physical Model - Initial Design 

Following the conceptual design, the initial physical data warehouse model was built by creating the necessary tables and Database Diagram features in Microsoft SQL Server Management Studio (SSMS).  
Key highlights:


- Creation of database `Meghana_Swamy_DW`
- Dimensional tables created:
  - `Meghana_Swamy_DimCustomer`
  - `Meghana_Swamy_DimProduct`
  - `Meghana_Swamy_DimSupplier`
  - `Meghana_Swamy_DimSalesReps`
  - `Meghana_Swamy_DimDate`
- Fact table created:
  - `Meghana_Swamy_FactSales`
- Relationships properly set up with primary and foreign keys
- SCD Type II attributes implemented
- Star schema designed for analytical querying
### 📸 Star Schema Visualization
Below is a simple star schema visualization of the physical design:

![Screenshot 2025-04-27 231348](https://github.com/user-attachments/assets/f5ae9ea0-0328-46f5-9d67-21cbc9916dfa)

### 📸 Physical Model Diagram 
Below is the physical model diagram created using SSMS Database Diagramming:

![Meghana_Swamy_DWLab2_physicalModel](https://github.com/user-attachments/assets/d8ce25cf-fdfa-48dd-8c3c-2e331398e0c3)

---

## 🛠️ Physical Model - Extended Design

In this phase, advanced data warehouse modeling techniques were applied to handle complex business scenarios:

- **Many-to-Many Relationship between Two Dimensions:**
  - Created a new dimension `Meghana_Swamy_DimSupplyChainRoute` to capture supply chain routes.
  - Created a bridge table `Meghana_Swamy_DimSupplierRouteBridge` to connect suppliers and routes.
  - Achieved many-to-many relationship between **DimSupplier** and **DimSupplyChainRoute** through the bridge.

- **Many-to-Many Relationship between FactSales and DimCustomer:**
  - Created a bridge table `Meghana_Swamy_BridgeCustomerGroup` to group customers.
  - Modified the **FactSales** table to connect to customer groups instead of individual customers.
  - Created a unique constraint (index) on `CustomerGroupID` in the FactSales table to maintain integrity.

- **Indexes on Customer Table:**
  - Added indexes on key fields in `DimCustomer` to improve query performance, likely on fields such as `CustomerState` and `CustomerCity`.

### 📸 Extended Physical Model Diagram 
![Meghana_Swamy_DWLab_Homework](https://github.com/user-attachments/assets/7cabeb65-67f9-415e-bec6-a7fa3680008d)

---

## 🚀 Key Skills Demonstrated:
- Conceptual, Logical, and Physical Data Modeling
- Star Schema and Bridge Tables for Many-to-Many Relationships
- Handling Slowly Changing Dimensions (SCD Type II)
- Schema creation using SSMS Table Designer
- Database Diagramming and Visualization
- Indexing Strategies for Query Optimization

---

## 🛠️ Tools Used:
- Microsoft SQL Server
- SSMS (SQL Server Management Studio)
- Microsoft Excel (for conceptual modeling)

![Microsoft SQL Server](https://img.shields.io/badge/Microsoft%20SQL%20Server-Database-red)
![SSMS](https://img.shields.io/badge/SSMS-Management%20Studio-lightgrey)
![Data Warehousing](https://img.shields.io/badge/Data%20Warehousing-Star%20Schema-blue)
![Dimensional Modeling](https://img.shields.io/badge/Dimensional%20Modeling-SCD%20Type%20II-green)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-Modeling-brightgreen)


