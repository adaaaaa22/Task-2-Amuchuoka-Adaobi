# 🗄️ SQL E-Commerce Sales Analysis | Internship Project
<img width="594" height="315" alt="Screenshot 2026-06-18 021849" src="https://github.com/user-attachments/assets/2aa12f03-4706-4900-a27b-4b1622177d67" />
<img width="592" height="312" alt="Screenshot 2026-06-18 021833" src="https://github.com/user-attachments/assets/04f6a260-2fdf-4da9-bd7a-7955eda7e8fd" />
<img width="604" height="311" alt="Screenshot 2026-06-18 021802" src="https://github.com/user-attachments/assets/52d25084-163d-4211-b53f-63c58319a2ad" />
<img width="607" height="311" alt="Screenshot 2026-06-18 021744" src="https://github.com/user-attachments/assets/911c8f1d-a6ce-4d1f-9fd9-c02fb94ddd21" />

# 📖 Project Overview

This project was completed during my Data Analytics Internship to demonstrate practical SQL skills in data extraction, filtering, aggregation, and business analysis.

Using SQL Server, I queried an E-Commerce Sales Database to answer key business questions related to sales performance, customer behavior, product performance, payment preferences, referral effectiveness, and operational efficiency.

The project showcases proficiency in:

- SQL Query Writing
- Data Retrieval
- Data Filtering
- Data Aggregation
- Business Intelligence
- Data Exploration
- Performance Analysis

---

# 🎯 Business Objectives

The analysis was conducted to answer the following business questions:

### Sales Performance
- What products generate the highest revenue?
- Which products sell the highest quantity?

### Customer Behavior
- Which payment methods are most frequently used?
- What is the average order value by payment method?

### Marketing Effectiveness
- Which referral sources drive the most orders?
- Which referral channels generate the most revenue?

### Operational Analysis
- How are orders distributed across different statuses?
- How many orders have been successfully shipped?

### Promotional Performance
- Which coupon codes are used most frequently?
- How much revenue is generated through coupon-based purchases?

---

# 🗂️ Database Information

### Database Name

```sql
INTERNSHIP PROJECTS
```

### Table Used

```sql
[e-commerce sales data]
```

### Key Columns

| Column Name | Description |
|------------|-------------|
| OrderID | Unique order identifier |
| Date | Transaction date |
| CustomerID | Unique customer identifier |
| Product | Product purchased |
| Quantity | Number of units purchased |
| UnitPrice | Price per unit |
| TotalPrice | Total order value |
| PaymentMethod | Customer payment option |
| OrderStatus | Order fulfillment status |
| ReferralSource | Customer acquisition source |
| CouponCode | Promotional code used |
| ItemsInCart | Number of items added to cart |

---

# 🛠 SQL Concepts Applied

### Data Retrieval

```sql
SELECT * 
FROM [e-commerce sales data];
```

Used to retrieve all records from the dataset.

---

### Column Selection

```sql
SELECT OrderID,
       Product,
       Quantity,
       Date,
       OrderStatus,
       ReferralSource,
       TotalPrice
FROM [e-commerce sales data];
```

Used to retrieve only relevant business columns.

---

### Filtering Data

#### Shipped Orders

```sql
SELECT *
FROM [e-commerce sales data]
WHERE OrderStatus = 'Shipped';
```

#### High-Value Transactions

```sql
SELECT OrderID,
       Product,
       TotalPrice
FROM [e-commerce sales data]
WHERE TotalPrice > 1000;
```

#### Cancelled Credit Card Orders

```sql
SELECT *
FROM [e-commerce sales data]
WHERE PaymentMethod = 'Credit Card'
AND OrderStatus = 'Cancelled';
```

---

### Sorting Data

#### Highest Revenue Orders

```sql
SELECT OrderID,
       Product,
       TotalPrice
FROM [e-commerce sales data]
ORDER BY TotalPrice DESC;
```

#### Lowest Revenue Orders

```sql
SELECT OrderID,
       Product,
       TotalPrice
FROM [e-commerce sales data]
ORDER BY TotalPrice ASC;
```

#### Products in Alphabetical Order

```sql
SELECT *
FROM [e-commerce sales data]
ORDER BY Product ASC;
```

---

# 📊 Exploratory Data Analysis (EDA)

## 1️⃣ Total Orders by Product

```sql
SELECT Product,
       COUNT(*) AS TotalOrders
FROM [e-commerce sales data]
GROUP BY Product;
```

### Business Purpose

Determine which products are ordered most frequently.

---

## 2️⃣ Orders by Status

```sql
SELECT OrderStatus,
       COUNT(*) AS NumberOfOrders
FROM [e-commerce sales data]
GROUP BY OrderStatus;
```

### Business Purpose

Monitor operational performance and fulfillment efficiency.

---

## 3️⃣ Revenue by Product

```sql
SELECT Product,
       SUM(TotalPrice) AS TotalRevenue
FROM [e-commerce sales data]
GROUP BY Product
ORDER BY TotalRevenue DESC;
```

### Business Purpose

Identify top revenue-generating products.

---

## 4️⃣ Quantity Sold by Product

```sql
SELECT Product,
       SUM(Quantity) AS TotalQuantitySold
FROM [e-commerce sales data]
GROUP BY Product;
```

### Business Purpose

Measure product demand.

---

## 5️⃣ Average Order Value by Payment Method

```sql
SELECT PaymentMethod,
       AVG(TotalPrice) AS AvgOrderValue
FROM [e-commerce sales data]
GROUP BY PaymentMethod;
```

### Business Purpose

Understand spending behavior based on payment preferences.

---

## 6️⃣ Average Quantity Purchased by Referral Source

```sql
SELECT ReferralSource,
       AVG(Quantity) AS AvgQuantity
FROM [e-commerce sales data]
GROUP BY ReferralSource;
```

### Business Purpose

Evaluate customer purchasing behavior across acquisition channels.

---

## 7️⃣ Revenue Generated from Shipped Orders

```sql
SELECT Product,
       SUM(TotalPrice) AS Revenue
FROM [e-commerce sales data]
WHERE OrderStatus = 'Shipped'
GROUP BY Product
ORDER BY Revenue DESC;
```

### Business Purpose

Identify products contributing most to successfully fulfilled sales.

---

## 8️⃣ Orders and Revenue by Referral Source

```sql
SELECT ReferralSource,
       COUNT(*) AS Orders,
       SUM(TotalPrice) AS TotalRevenue
FROM [e-commerce sales data]
GROUP BY ReferralSource
ORDER BY Orders DESC;
```

### Business Purpose

Determine which marketing channels generate the highest business value.

---

## 9️⃣ Coupon Performance Analysis

```sql
SELECT CouponCode,
       COUNT(*) AS TimesUsed,
       SUM(TotalPrice) AS Revenue
FROM [e-commerce sales data]
GROUP BY CouponCode
ORDER BY Revenue DESC;
```

### Business Purpose

Measure promotional campaign effectiveness.

---

# 📈 Key Insights Generated

### Product Analysis

- Identified top-performing products by revenue.
- Measured product demand using quantity sold.
- Evaluated order frequency across products.

### Customer Behavior

- Analyzed preferred payment methods.
- Measured average customer spending.

### Marketing Performance

- Determined the most effective referral channels.
- Evaluated revenue contribution from acquisition sources.

### Operational Performance

- Assessed order status distribution.
- Evaluated successfully shipped orders.

### Promotion Analysis

- Identified the most effective coupon campaigns.
- Measured revenue generated from discounts.

---

# 💡 Business Recommendations

## Product Strategy

- Increase stock levels for high-demand products.
- Prioritize marketing efforts on top revenue-generating products.

## Customer Experience

- Investigate factors contributing to cancelled orders.
- Improve order fulfillment processes.

## Marketing Optimization

- Allocate more budget to high-performing referral channels.
- Develop targeted campaigns based on customer acquisition insights.

## Promotional Strategy

- Continue using high-performing coupon codes.
- Retire underperforming promotions.

---

# 📸 Project Screenshots

## SQL Query Execution

Include screenshots of:

- Data Retrieval Queries
- Filtering Operations
- Aggregation Queries
- Revenue Analysis
- Group By Operations
- Business Intelligence Queries

### Example

```text
Screenshots/
│
├── SQL_Query_1.png
├── SQL_Query_2.png
├── SQL_Query_3.png
```

---

# 🧰 Tools Used

| Tool | Purpose |
|--------|----------|
| SQL Server | Database Management |
| SQL | Data Querying |
| SSMS / Azure Data Studio | Query Execution |
| GitHub | Project Documentation |

---

# 📚 Skills Demonstrated

- SQL Query Writing
- Data Filtering
- Data Aggregation
- Data Exploration
- Business Analysis
- Data Storytelling
- Database Management
- Problem Solving

---

# 📁 Repository Structure

```text
SQL-Ecommerce-Sales-Analysis/
│
├── Dataset/
│   └── Ecommerce_Sales_Data.csv
│
├── SQL Queries/
│   └── ecommerce_analysis.sql
│
├── Screenshots/
│   ├── Query_Execution_1.png
│   ├── Query_Execution_2.png
│   └── Query_Execution_3.png
│
└── README.md
```

---

# 🎓 Internship Outcome

This project strengthened my practical SQL skills by applying real-world business scenarios to an e-commerce dataset.

The analysis demonstrated how SQL can be used to transform raw transactional data into valuable business insights that support strategic decision-making.

---

## 👩‍💻 Author

### Amuchuoka Adaobi Lilian

**Data Analyst | Business Intelligence Enthusiast**

### Connect With Me

- LinkedIn: www.linkedin.com/in/amuchuoka-adaobi-lilian-1492492a6
- Email: amuchuokaadaobi@gmail.com

---

⭐ If you found this project helpful, feel free to star the repository.# Task-2-Amuchuoka-Adaobi
