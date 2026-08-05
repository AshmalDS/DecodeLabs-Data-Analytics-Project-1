# Data Analytics — Project 1
## E-Commerce Dataset: Data Cleaning & Exploratory Data Analysis

This project is **Project 1** of my Data Analytics portfolio. The objective was to clean and prepare the provided **Dataset for Data Analytics**, then perform exploratory data analysis to uncover business performance, customer behavior, and product/marketing insights.

## Dataset

* **Rows:** 1,200
* **Columns:** 14
* **File:** `Dataset for Data Analytics.xlsx`
* **Fields:** OrderID, Date, CustomerID, Product, Quantity, UnitPrice, ShippingAddress, PaymentMethod, OrderStatus, TrackingNumber, ItemsInCart, CouponCode, ReferralSource, TotalPrice

## Tools & Technologies

* Python
* Pandas / NumPy
* Matplotlib / Seaborn
* Jupyter Notebook
* Excel

---

## Part 1: Data Cleaning & Preparation 🧹

### 1. Dataset Inspection
* Examined the first few records using `head()`
* Checked the number of rows and columns
* Reviewed column information and data types using `info()`
* Used `describe()` to understand numerical and categorical columns

### 2. Missing Values
Missing values were identified using Pandas. The `CouponCode` column contained **309 missing values**, handled by replacing them with:
```text
No_CouponCode
```

### 3. Duplicate Records
The dataset was checked for completely duplicated rows. **Result:** 0 duplicate rows.

### 4. Duplicate Order IDs
`OrderID` was checked to ensure each order had a unique identifier. **Result:** 0 duplicate OrderIDs.

### 5. Date Validation
The `Date` column was converted to datetime format and checked for invalid dates. **Result:** 0 invalid dates.

### 6. Text Cleaning
Leading and trailing whitespace was removed from the `Product` column to improve consistency.

### Final Data Validation

| Check              |           Result |
| ------------------ | ---------------: |
| Missing values     |                0 |
| Duplicate rows     |                0 |
| Duplicate OrderIDs |                0 |
| Invalid dates      |                0 |
| Date data type     | `datetime64[ns]` |

---

## Part 2: Exploratory Data Analysis 📊

### Business Performance
* **Total Revenue:** $1,264,761.96
* **Average Order Value:** $1,053.97
* **Total Orders:** 1,200
* **Total Customers:** 1,189
* **Total Quantity Sold:** 3,535 units

### Customer Behavior
* Only **11 customers (0.93%)** placed more than one order; **1,178 (99.07%)** ordered exactly once
* No customer placed more than two orders
* Top spender (`C38840`) is the only repeat customer among the top 10 by spending

### Time-Based Trends
* **June** was the strongest month ($170,616.13); **September** the weakest ($69,321.65)

### Product Performance
* **Chair** ($195,620.11) and **Printer** ($195,612.61) are the top revenue-generating products, followed closely by Laptop, Tablet, Monitor, Desk, and Phone
* Same ranking roughly holds by quantity sold

### Payment Methods
* **Credit Card** generates the highest revenue ($263,847.63), followed by Online, Cash, Gift Card, and Debit Card

### Order Status
* **Cancelled orders** carry the highest associated order value ($276,396.21) — despite being lost sales, worth flagging as a business risk since this isn't realized revenue

### Coupons
* **FREESHIP** is the most-used coupon (313 orders) and generates the highest coupon-associated revenue ($335,036.99)

### Referral Sources
* **Instagram** is the leading referral source by order count (259 orders)

### Relationships Between Variables
* **UnitPrice vs Quantity:** correlation of 0.015 — no meaningful relationship; purchase quantity appears driven by need rather than price sensitivity

---

## Key Insights

1. The dataset contains **1,200 orders** from **1,189 unique customers**, generating total revenue of approximately **$1.26M** at an average order value of **$1,053.97**
2. Customer retention is very low — only **0.93%** of customers placed more than one order
3. **Chair** and **Printer** are the top revenue-generating products, generating almost identical revenue
4. **Credit Card** generated the highest revenue among payment methods (**$263,847.63**)
5. **June** recorded the highest monthly revenue; **September** recorded the lowest
6. **FREESHIP** was the most frequently used coupon and generated the highest coupon-associated revenue
7. **UnitPrice and Quantity** show almost no linear relationship (r = 0.015)
8. **Cancelled orders** were associated with the highest total order value of any status — this should not be treated as realized revenue
9. **Instagram** was the most common referral source by order count

## Business Recommendations

1. **Improve customer retention** — the repeat rate is only 0.93%; consider loyalty programs, personalized offers, and post-purchase engagement
2. **Focus on high-performing products** — maintain strong inventory and targeted promotions for Chair and Printer
3. **Investigate cancelled orders** — identify root causes to recover lost revenue
4. **Evaluate promotional strategy** — confirm FREESHIP is net-positive for acquisition and order value, not just usage volume
5. **Plan around seasonality** — investigate what drives the June peak and September trough, and align marketing/inventory accordingly
6. **Strengthen high-performing channels** — Instagram drives the most orders; consider increasing marketing investment there
7. **Use customer data for segmentation** — since most customers purchase only once, targeted re-engagement campaigns could improve lifetime value

## Conclusion

This project demonstrated the complete data analyst workflow — from data cleaning and validation through exploratory data analysis and visualization — using Python, Pandas, Matplotlib, and Seaborn. The dataset was cleaned by handling missing values, checking duplicates, validating dates, cleaning text fields, and performing final validation. EDA then uncovered patterns in business performance, customer behavior, product performance, payment methods, order status, coupon usage, referral sources, and relationships between numerical variables.

The analysis provided actionable insights — including low repeat purchasing, strong performance from Chair and Printer, Credit Card as the top-revenue payment method, FREESHIP's strong coupon performance, and significant seasonal revenue differences — that can guide retention strategy, cancellation investigation, promotion optimization, and channel-focused marketing.

## How to Run

```bash
pip install pandas numpy matplotlib seaborn openpyxl
jupyter notebook ecommerce-sales-eda.ipynb
```

## Repository Contents

```
├── ecommerce-sales-eda.ipynb   # Full analysis notebook
├── Dataset for Data Analytics.xlsx
└── README.md
```
