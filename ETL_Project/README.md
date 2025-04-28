# ETL Projects using SSIS

This folder contains ETL (Extract, Transform, Load) projects/packages designed and implemented as part of my Database Management coursework.  
The projects focus on building professional ETL pipelines using Microsoft SQL Server Integration Services (SSIS), solving real-world business integration challenges.

The destination for all ETL projects is a database called **BI_Database**.  
(Created a new database in SSMS and called it BI_Database. All of the tables were created in ETL projects 1-8 and then stored in this database)
![Screenshot 2025-04-28 191437](https://github.com/user-attachments/assets/d37ac369-918d-4c56-88b7-a36853f33ff4)

**BI_Database** is a Business Intelligence database designed to support analytical reporting by consolidating, transforming, and preparing transactional data from multiple sources.  

Throughout the projects, data is extracted from the operational **PracticeDatabase**(uploaded), transformed as needed, and loaded into **BI_Database**.
Additionally, ETL DW projects involve loading (or populating the) clean, transformed data into the custom-built data warehouse **Meghana_Swamy_DW**.
(Refer Data-Warehousing Project file)
---

## 📚 Contents:
- **ETL Project 1:** Relational database to relational database transfer
- **ETL Project 2:** Text file to relational database transfer
- **ETL Project 3:** Conditional Split transformation
- **ETL Project 4:** Multicast task and aggregations
- **ETL Project 5:** Pivoting data using Pivot transformation
- **ETL Project 6:** Derived Column transformations for business calculations
- **ETL Project 7:** Fuzzy Lookup for data cleansing
- **ETL Project 8:** XML file import into relational database
- **ETL DW Project 1:** Populating DimCustomer table
- **ETL DW Project 2:** Populating DimProduct table
- **ETL DW Project 3:** Populating DimDates table

---

## 🚀 Projects

### 📦 ETL Project 1 – RDBMS to RDBMS
**Business Goal:**  
Transfer order data from a transactional relational database (`PracticeDatabase`) to a new relational database (`BI_Database`).

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
 ![P1](https://github.com/user-attachments/assets/1e39ea34-0f42-41ae-bb46-227c856b10f7)
- SSMS Result in BI_Database:  
 ![Screenshot 2025-04-28 192320](https://github.com/user-attachments/assets/a8020eb9-b547-4720-b529-0fe3ef26209c)

---

### 📦 ETL Project 2 – Import Export Wizard
**Business Goal:**  
Transfer customer data from a flat text file into a relational database (`BI_Database`) using the Import-Export Wizard.

**Tasks Used:**
- Flat File Source
- OLE DB Destination
- Data Conversion (for datatype adjustments)

**Screenshots:**
- SSIS Package Running:  
  ![ETL_Project2_Package](./screenshots/ETL_Project2_Package.png)
- SSMS Result in BI_Database:  
  ![ETL_Project2_Result](./screenshots/ETL_Project2_Result.png)

---

### 📦 ETL Project 3 – Conditional Split
**Business Goal:**  
Transfer inventory information by splitting data conditionally (e.g., Products to order, Products on order).

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Conditional Split
- OLE DB Destination (multiple based on conditions)

**Screenshots:**
- SSIS Package Running:  
  ![ETL_Project3_Package](./screenshots/ETL_Project3_Package.png)
- SSMS Result in BI_Database:  
  ![ETL_Project3_Result](./screenshots/ETL_Project3_Result.png)

---

### 📦 ETL Project 4 – Multicast Task
**Business Goal:**  
Generate multiple aggregate datasets from product data.

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Multicast
- Aggregate Transformations
- OLE DB Destinations

**Screenshots:**
- SSIS Package Running:  
  ![ETL_Project4_Package](./screenshots/ETL_Project4_Package.png)
- SSMS Result in BI_Database:  
  ![ETL_Project4_Result](./screenshots/ETL_Project4_Result.png)

---

### 📦 ETL Project 5 – Pivoting Data
**Business Goal:**  
Automatically generate a pivot table summarizing quantity sold by year and by state.

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Pivot Transformation
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
  ![ETL_Project5_Package](./screenshots/ETL_Project5_Package.png)
- SSMS Result in BI_Database:  
  ![ETL_Project5_Result](./screenshots/ETL_Project5_Result.png)

---

### 📦 ETL Project 6 – Derived Column Transformation
**Business Goal:**  
Create calculated and concatenated fields (such as Customer Name, Order Year, Subtotals) for easier reporting.

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Derived Column Transformation
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
  ![ETL_Project6_Package](./screenshots/ETL_Project6_Package.png)
- SSMS Result in BI_Database:  
  ![ETL_Project6_Result](./screenshots/ETL_Project6_Result.png)

---

### 📦 ETL Project 7 – Fuzzy Lookup
**Business Goal:**  
Segment customers based on fuzzy matching of addresses (Street, Avenue, etc.).

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Fuzzy Lookup
- Conditional Split (for high vs low similarity matches)
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
  ![ETL_Project7_Package](./screenshots/ETL_Project7_Package.png)
- SSMS Result in BI_Database:  
  ![ETL_Project7_Result](./screenshots/ETL_Project7_Result.png)

---

### 📦 ETL Project 8 – XML Data Import
**Business Goal:**  
Import order data from an XML file into a relational database (`BI_Database`).

**Tasks Used:**
- Data Flow Task
- XML Source
- Data Conversion
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
  ![ETL_Project8_Package](./screenshots/ETL_Project8_Package.png)
- SSMS Result in BI_Database:  
  ![ETL_Project8_Result](./screenshots/ETL_Project8_Result.png)

---

# 📚 ETL Homework Projects (Data Warehouse Loading)

### 📦 ETL Homework Project 1 – Populate DimCustomer Table
**Business Goal:**  
Move customer-related data into the `DimCustomer` dimension table in the `Meghana_Swamy_DW` warehouse.

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Derived Column Transformation (for adding historical tracking fields)
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
  ![ETL_HW1_Package](./screenshots/ETL_HW1_Package.png)
- SSMS Result in Meghana_Swamy_DW:  
  ![ETL_HW1_Result](./screenshots/ETL_HW1_Result.png)

---

### 📦 ETL Homework Project 2 – Populate DimProduct Table
**Business Goal:**  
Move product-related data into the `DimProduct` dimension table in `Meghana_Swamy_DW`.

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Derived Column Transformation
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
  ![ETL_HW2_Package](./screenshots/ETL_HW2_Package.png)
- SSMS Result in Meghana_Swamy_DW:  
  ![ETL_HW2_Result](./screenshots/ETL_HW2_Result.png)

---

### 📦 ETL Homework Project 3 – Populate DimDates Table
**Business Goal:**  
Move and derive date attributes for the `DimDates` table.

**Tasks Used:**
- Data Flow Task
- OLE DB Source
- Derived Column Transformation (for year, quarter, month, week)
- OLE DB Destination

**Screenshots:**
- SSIS Package Running:  
  ![ETL_HW3_Package](./screenshots/ETL_HW3_Package.png)
- SSMS Result in Meghana_Swamy_DW:  
  ![ETL_HW3_Result](./screenshots/ETL_HW3_Result.png)

---

## 🛠️ Tools Used
- Microsoft SQL Server
- SQL Server Management Studio (SSMS)
- SQL Server Integration Services (SSIS)
- Visual Studio 2022 (Integration Services Projects)
