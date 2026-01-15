# 📊 Data Catalog — Gold Layer

## 🔍 Overview
The **Gold Layer** represents **business-ready, curated data** designed for **analytics, dashboards, and reporting**.  
It follows a **star schema** structure and consists of:

- **Dimension tables** for descriptive business entities  
- **Fact tables** for measurable business events  

---

## 🟨 Dimension Tables

---

### 1. `gold.dim_customers`

**Purpose**  
Stores enriched customer information, including demographic and geographic attributes, to support customer-level analysis.

| Column Name       | Data Type     | Description |
|-------------------|---------------|-------------|
| customer_key      | INT           | Surrogate key uniquely identifying each customer record. |
| customer_id       | INT           | System-generated unique identifier for the customer. |
| customer_number   | NVARCHAR(50)  | Business-friendly alphanumeric customer identifier. |
| first_name        | NVARCHAR(50)  | Customer’s first name. |
| last_name         | NVARCHAR(50)  | Customer’s last (family) name. |
| country           | NVARCHAR(50)  | Country of residence (e.g., Australia). |
| marital_status    | NVARCHAR(50)  | Marital status (e.g., Married, Single). |
| gender            | NVARCHAR(50)  | Gender of the customer (e.g., Male, Female, N/A). |
| birthdate         | DATE          | Customer’s date of birth (YYYY-MM-DD). |
| create_date       | DATE          | Date when the customer record was created. |

---

### 2. `gold.dim_products`

**Purpose**  
Contains product master data and classification attributes for product-level analysis.

| Column Name            | Data Type     | Description |
|------------------------|---------------|-------------|
| product_key            | INT           | Surrogate key uniquely identifying each product record. |
| product_id             | INT           | Internal system identifier for the product. |
| product_number         | NVARCHAR(50)  | Business alphanumeric product code. |
| product_name           | NVARCHAR(50)  | Descriptive product name including type and attributes. |
| category_id            | NVARCHAR(50)  | Identifier for the product category. |
| category               | NVARCHAR(50)  | High-level product classification (e.g., Bikes). |
| subcategory            | NVARCHAR(50)  | Detailed product grouping within the category. |
| maintenance_required   | NVARCHAR(50)  | Indicates whether maintenance is required (Yes/No). |
| cost                   | INT           | Base cost of the product in monetary units. |
| product_line           | NVARCHAR(50)  | Product line or series (e.g., Road, Mountain). |
| start_date             | DATE          | Date the product became available. |

---

## 🟦 Fact Tables

---

### 3. `gold.fact_sales`

**Purpose**  
Captures transactional sales data at the order-line level for revenue and performance analysis.

| Column Name     | Data Type     | Description |
|-----------------|---------------|-------------|
| order_number    | NVARCHAR(50)  | Unique sales order identifier (e.g., SO54496). |
| product_key     | INT           | Foreign key linking to `gold.dim_products`. |
| customer_key    | INT           | Foreign key linking to `gold.dim_customers`. |
| order_date      | DATE          | Date the order was placed. |
| shipping_date   | DATE          | Date the order was shipped. |
| due_date        | DATE          | Payment due date for the order. |
| sales_amount    | INT           | Total sales value for the line item. |
| quantity        | INT           | Number of units sold. |
| price           | INT           | Unit selling price. |

---

## ✅ Design Notes
- Surrogate keys used for all dimension joins  
- Optimized for BI tools and analytical workloads  
- Clear separation between facts and dimensions  
