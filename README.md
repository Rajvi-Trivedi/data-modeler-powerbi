# Data Modeler – Power BI
## Project Overview

This project focuses on designing and implementing an optimized data model in Power BI to support scalable and high-performance reporting.

The solution follows dimensional modeling best practices, using a Star Schema architecture to ensure clarity, efficient filtering, and reliable analytical outcomes for business intelligence scenarios.

---

## Data Model Architecture

The model is structured using a **Star Schema**, with `Sales_Fact` as the central transactional table connected to multiple dimension tables.

### Fact Tables

* **Sales_Fact** – Transaction-level sales data including revenue, quantity, customer, product, region, and date keys
* **Returns_Fact** – Product return transactions enabling return-specific performance analysis

### Dimension Tables

* **Customer_Dim** – Customer demographics and segmentation attributes
* **Product_Dim** – Product name, category, subcategory, and brand
* **Region_Dim** – Geographic hierarchy (country, state, city)
* **Date_Dim** – Calendar attributes including month, quarter, and fiscal year

---

## Relationship Design

* All relationships were manually created using primary key–foreign key logic
* One-to-many (1:*) relationships established between dimension tables and `Sales_Fact`
* Single-direction cross-filtering applied for controlled filter propagation and optimized performance
* An inactive relationship was created between `Returns_Fact` and `Date_Dim` using `ReturnDateKey` to manage multiple date contexts

---

## Challenge & Resolution

An ambiguous filter path occurred due to multiple relationships between fact tables and the `Date_Dim` table.

This was resolved by:

* Keeping the `Sales_Fact – Date_Dim` relationship active
* Setting the `Returns_Fact – Date_Dim` relationship as inactive

This approach eliminated ambiguity while maintaining analytical flexibility and aligns with industry-standard BI modeling practices.

---

## Key Outcomes

* Optimized and scalable Star Schema model
* Improved report performance and filter clarity
* Proper separation of fact and dimension tables
* Support for time-based and return-focused analysis

---

## Tools & Technologies

* Microsoft Power BI Desktop
* Power Query (Data Transformation)
* DAX (Data Analysis Expressions)

---

## File Information

* File Name: `Data_Modeler.pbix`
* Model Type: Star Schema with secondary fact table

---

## Use Cases

* Sales performance tracking
* Category and region-wise revenue analysis
* Customer segmentation insights
* Return trend and fiscal year evaluation

---

## Author

Rajvi Trivedi
Data Analyst | Business Analyst

---
