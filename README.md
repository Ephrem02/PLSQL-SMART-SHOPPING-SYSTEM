## 👨🏿‍💻 Author

Manzi Ephrem 27856
Capstone database Project
Lecturer: Mr.Maniraguha Eric

## SMART SHOPPING CART SYSTEM

The Smart Shopping Cart System is an automated retail solution built with Oracle PL/SQL. It enables a scan and go shopping experience that processes payments, updates inventory in real-time, and strictly enforces data 
security using advanced database triggers.

## [Problem Statement](<Smart shopping cart system.pptx>)

## 📌 project Objectives

- Automate the shopping experience using PL/SQL so customers don't have to wait in line
- Secure the data by using Triggers to block unauthorized employee access during weekdays.
- Analyze the results using Business Intelligence queries to help owners track their best-selling products.
- Enhance data integrity, security, and traceability

  ## 🗂️ FILES INCLUDED

  [Full database Implementation script](<Smart_shopping.sql>)
   - Table creation
  - Sample data insertion
  - Procedures and cursors
  - Packages
  - Triggers for weekday/holiday restrictions
  - Auditing and logging logic

  ## 🗂️ Main Database Entities
  - **USERS**: Stores all system users, distinguishing between Customers (who shop), Employees (who manage stock), and Admins.
  - **PRODUCTS**: The central inventory catalog containing all items available for sale. It connects to carts, orders, and logs.
  - **CART**: A temporary holding table for items a customer is currently shopping for. Data here is transient (added/removed frequently).
  - **ORDERS**: Records the summary of a completed transaction, linking a specific user to a date and total cost.
  - **ORDER_DETAILS**: Stores the specific list of products within an order
  - **PAYMENTS**: Records the financial confirmation of the order.
  - **STOCK_LOGS**: An automated history log that records every time the Stock_qty changes in the PRODUCTS table (populated by a Trigger).
  - **SYSTEM_AUDIT_LOG**: A security table that records blocked attempts, such as an Employee trying to modify data on a restricted Weekday
  - **Holiday Table**: Prevents DML operations on set holidays

  ## ⚙️ Features

- **Parameterized Procedures** to fetch and process product data
- **Cursors** to loop through datasets
- **Packages** for reusable business logic
- **Triggers** to:
  - Prevent data manipulation on weekdays and holidays
  - Log all critical changes to sensitive inventory tables
- **Auditing System** to capture user ID, action time, operation, and status (allowed/denied)

## ✅ Usage

1. Execute the `.sql` file in Oracle SQL Developer or SQL*Plus.
2. Test procedures using:
   ```sql
   EXEC get_product_info(1);
   ```
3. Try inserting or updating products on weekdays to trigger security restrictions.

## Business Process Modeling
![](<Business process model.png>)
