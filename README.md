**📊 Project-2: Data Modeler (Power BI)**
📌 Project Overview

This project focuses on designing and implementing an optimized data model in Power BI to support efficient reporting and analysis. The solution follows dimensional modeling best practices, ensuring high performance, clarity, and scalability for business intelligence use cases.

🧱 Data Model Architecture

The project is built using a Star Schema design with Sales_Fact as the central fact table. Core dimension tables are directly connected to the fact table to enable fast filtering and aggregation.

Fact Tables

Sales_Fact – Stores transactional sales data including revenue, quantity, customer, product, region, and date keys.

Returns_Fact – Captures product return transactions and supports return-specific analysis.

Dimension Tables

Customer_Dim – Customer demographics and segmentation details

Product_Dim – Product name, category, subcategory, and brand

Region_Dim – Geographic information (country, state, city)

Date_Dim – Calendar attributes such as date, month, quarter, and fiscal year

🔗 Relationship Design

All relationships were manually created using primary key–foreign key logic.

Each dimension table has a one-to-many (1:*) relationship with the Sales_Fact table.

Single-direction cross-filtering was applied to maintain predictable filter behavior and improve performance.

An inactive relationship was created between Returns_Fact and Date_Dim using ReturnDateKey to handle multiple date contexts.

⚠️ Challenges & Resolution

An ambiguous filter path occurred due to multiple relationships between fact tables and the Date_Dim table. This was resolved by:

Keeping the Sales_Fact–Date_Dim relationship active

Setting the Returns_Fact–Date_Dim relationship as inactive

This approach eliminated ambiguity while preserving analytical flexibility and aligns with industry-standard BI modeling practices.

📈 Key Outcomes

Clean and optimized data model

Improved report performance

Clear separation of facts and dimensions

Support for advanced time-based and return analysis

🛠 Tools Used

Power BI Desktop

Power Query (Data Cleaning & Transformation)

DAX (Measures & Calculations)

📂 File Information

File Name: Data Modeler.pbix

Model Type: Star Schema with secondary fact table

✅ Use Cases

Sales performance analysis

Category and region-wise revenue tracking

Customer segmentation insights

Return trend and fiscal year analysis
