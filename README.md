# PL-SQL-Windows-functions
PL/SQL assignment on window functions: ranking, aggregates with frames, navigation, and distribution, To Be Applied on a micro-hub fresh produce business case.

# PL/SQL Window Functions Assignment

## 📌 Business Problem
FreshDirect, a company running micro-fulfillment hubs for fresh produce in Kigali and surrounding regions, needs to analyze sales data to improve decision-making.  
Management wants to:
- Identify top products per hub and quarter
- Track monthly running totals and growth
- Segment customers by revenue quartiles for loyalty programs
- Calculate moving averages to optimize inventory thresholds

---

## 🎯 Success Criteria
1. **Top-5 products per hub & quarter** using `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, and `PERCENT_RANK()`.  
2. **Running monthly sales totals** with `SUM() OVER`.  
3. **Month-over-month growth %** using `LAG()`.  
4. **Customer quartiles** with `NTILE(4)`.  
5. **3-month moving averages** for products using `AVG() OVER`.  

---

##  Database Schema
Entities created in Oracle 21c:

- **Regions(region_id, region_name)**  
- **Hubs(hub_id, hub_name, region_id)**  
- **Farmers(farmer_id, farmer_name, region_id)**  
- **Customers(customer_id, full_name, region_id, join_date)**  
- **Products(product_id, product_name, category, unit_price)**  
- **Orders(order_id, customer_id, hub_id, order_date, status)**  
- **Order_Items(item_id, order_id, product_id, farmer_id, quantity, unit_price, amount)**  

### ER Diagram.
regions (1) --- (M) hubs
regions (1) --- (M) farmers
regions (1) --- (M) customers
hubs (1) --- (M) orders
orders (1) --- (M) order_items
products (1) --- (M) order_items
farmers (1) --- (M) order_items
