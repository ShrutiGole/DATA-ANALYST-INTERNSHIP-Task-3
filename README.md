# DATA-ANALYST-INTERNSHIP-Task-3
SQL for Data Analysis

# 🛒 E-Commerce Database Management System - SQL Data Analysis

This repository is a part of a University course project for **Database Management Systems (COMP 213)**, and focuses on using **SQL for structured data analysis**. The project combines the development of a normalized database schema with hands-on analytical queries to extract business insights.

---

## 📌 Objective
To apply SQL for advanced **data extraction, manipulation, and analysis** using a fully relational E-Commerce database. The goal was to explore customer behavior, vendor performance, product popularity, and logistics management using real-world inspired queries.

---

## 🔧 Technologies Used
- **Database**: Microsoft SQL Server
- **Language**: SQL (Transact-SQL)
- **Tools**: SSMS / Azure Data Studio / DBeaver (recommended for querying and screenshots)

---

## 🗃️ Database Schema Overview

The database is structured in a highly normalized form, supporting:

| Domain | Tables |
|--------|--------|
| Customer & Address | `Customer`, `Address`, `City`, `Province`, `Country`, `ZipCode` |
| Product & Catalog | `Category`, `Product`, `Vendor`, `VendorProduct` |
| Sales & Orders | `Orders`, `OrderedProduct` |
| Logistics | `Courier`, `VendorCourier` |
| Reviews & Feedback | `Review` |
| Cart System | `Cart`, `CartProduct` |

> Full ER Diagram and Schema Diagrams are available in the `/Images` directory.

---

## 🔨 Implementation Structure

### 📁 `/Database & Table Creation`
Contains all scripts required to:
- Create the database `OnlineShopping`
- Define tables with proper primary and foreign keys
- Implement relationships between vendors, customers, orders, and couriers

### 📁 `/Data Insertion`
Includes scripts for populating:
- Sample categories, products, cities, orders, customers, and reviews
- All sample data is fictitious and used for demonstration purposes

---

## 🔍 SQL Query Highlights

### ✅ SELECT, GROUP BY, ORDER BY

```sql
-- Total number of orders per customer
SELECT c.CustomerID, CONCAT(c.FirstName, ' ', c.LastName) AS FullName, COUNT(o.OrderID) AS TotalOrders
FROM Customer c
JOIN Orders o ON c.CustomerID = o.CustomerID
GROUP BY c.CustomerID, c.FirstName, c.LastName
ORDER BY TotalOrders DESC;
