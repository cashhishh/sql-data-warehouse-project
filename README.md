# 📊 Data Warehouse & Analytics Project

A complete **end-to-end Data Warehouse and Analytics solution** built using **SQL Server** and **Medallion Architecture (Bronze, Silver, Gold)**.  
This project demonstrates real-world **data engineering, ETL pipelines, data modeling, and analytics workflows**.

---

## 🚀 Project Overview

The objective of this project is to design and implement a **modern data warehouse** that consolidates data from multiple source systems and transforms it into **business-ready analytics models**.

This project is suitable for:
- Data Engineering portfolios
- SQL & Analytics interview preparation
- Demonstrating real-world warehouse design

---

## 🏗️ Data Architecture

The data warehouse follows the **Medallion Architecture** pattern:

<img width="1694" height="912" alt="data_architecture" src="https://github.com/user-attachments/assets/69c76067-9c9c-410b-bbb2-766734ae314b" />


### 🔹 Bronze Layer (Raw Data)
- Stores raw data **as-is**
- Source systems: ERP & CRM (CSV files)
- No transformations applied

**Details:**
- Object Type: Tables  
- Load Type: Batch / Full Load / Truncate & Insert  
- Transformations: None  

---

### 🔸 Silver Layer (Cleaned & Standardized Data)
- Cleans and standardizes raw data
- Resolves data quality issues
- Prepares data for analytics

**Transformations:**
- Data Cleansing  
- Standardization  
- Normalization  
- Derived Columns  
- Data Enrichment  

**Details:**
- Object Type: Tables  
- Load Type: Batch Processing  

---

### 🟡 Gold Layer (Business-Ready Data)
- Optimized for analytics and reporting
- Implements **Star Schema**
- Used by BI tools and analysts

**Transformations:**
- Business Logic  
- Aggregations  
- Data Integration  

**Data Models:**
- Fact Tables  
- Dimension Tables  
- Aggregated Views  

**Details:**
- Object Type: Views  
- Load: No physical load  
