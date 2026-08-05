# 🛒 E-Commerce Sales Analysis

### Data Cleaning, Exploratory Data Analysis & Business Insights

## 📌 Project Overview

This project demonstrates an end-to-end **Data Analytics workflow** using an e-commerce sales dataset.

The objective was to clean, validate, analyze, and visualize the data to uncover insights related to **business performance, customer behavior, product performance, payment methods, promotions, referral channels, and sales trends**.

The project was completed using **Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook, and Excel**.

---

## 📂 Dataset

**File:** `E_Commerce Dataset.xlsx`

| Attribute           |     Details |
| ------------------- | ----------: |
| Rows                |       1,200 |
| Columns             |          14 |
| Unique Customers    |       1,189 |
| Total Quantity Sold | 3,535 units |

### Dataset Fields

`OrderID`, `Date`, `CustomerID`, `Product`, `Quantity`, `UnitPrice`, `ShippingAddress`, `PaymentMethod`, `OrderStatus`, `TrackingNumber`, `ItemsInCart`, `CouponCode`, `ReferralSource`, `TotalPrice`

---

# 🧹 Part 1 — Data Cleaning & Preparation

### 1. Dataset Inspection

The dataset was initially inspected to understand its structure and quality.

Performed:

* Previewed records using `head()`
* Checked dataset dimensions using `shape`
* Reviewed column names and data types using `info()`
* Examined numerical and categorical distributions using `describe()`

### 2. Missing Values

Missing values were identified using Pandas.

The `CouponCode` column contained **309 missing values**.

Since a missing coupon code indicates that no coupon was recorded for the order, these values were replaced with:

```text
No_CouponCode
```

### 3. Duplicate Records

The dataset was checked for completely duplicated rows.

**Result:** 0 duplicate rows found.

### 4. Duplicate Order IDs

`OrderID` was checked to ensure that each order had a unique identifier.

**Result:** 0 duplicate OrderIDs found.

### 5. Date Validation

The `Date` column was converted to Pandas datetime format and checked for invalid or missing dates.

**Result:** 0 invalid dates found.

### 6. Text Cleaning

Leading and trailing whitespace was removed from the `Product` column to ensure consistent product names during analysis and grouping.

### ✅ Final Data Validation

| Data Quality Check |           Result |
| ------------------ | ---------------: |
| Missing values     |                0 |
| Duplicate rows     |                0 |
| Duplicate OrderIDs |                0 |
| Invalid dates      |                0 |
| Date data type     | `datetime64[ns]` |

---

# 📊 Part 2 — Exploratory Data Analysis

The cleaned dataset was analyzed from several business perspectives.

## 💰 Business Performance

Key metrics identified during the analysis:

* **Total order value:** $1,264,761.96
* **Average order value:** $1,053.97
* **Total orders:** 1,200
* **Unique customers:** 1,189
* **Total quantity sold:** 3,535 units

> **Note:** Order values associated with cancelled orders should not automatically be interpreted as realized revenue. Cancellation impact was therefore analyzed separately.

---

## 👥 Customer Behavior

Customer purchasing behavior revealed extremely low repeat purchasing.

* **11 customers (0.93%)** placed more than one order
* **1,178 customers (99.07%)** placed exactly one order
* No customer placed more than two orders
* `C38840` was the only repeat customer appearing among the top 10 customers by spending

### Key Insight

The business appears to have a significant **customer retention opportunity**, as the overwhelming majority of customers made only one purchase.

---

## 📅 Monthly Sales Trends

Monthly analysis showed considerable variation in order value.

* 🟢 **June:** Highest monthly order value — **$170,616.13**
* 🔴 **September:** Lowest monthly order value — **$69,321.65**

### Key Insight

The large difference between peak and low months suggests that the business could investigate seasonal demand, promotions, customer activity, and inventory availability.

---

## 🛍️ Product Performance

The leading products by total order value were:

1. **Chair** — $195,620.11
2. **Printer** — $195,612.61
3. Laptop
4. Tablet
5. Monitor
6. Desk
7. Phone

Chair and Printer generated almost identical order values and were the strongest-performing products in the dataset.

The product ranking was also broadly similar when examining quantity sold.

### Key Insight

High-performing products such as Chair and Printer should receive appropriate attention in inventory planning, merchandising, and promotional campaigns.

---

## 💳 Payment Method Analysis

Revenue/order value by payment method showed:

1. **Credit Card** — $263,847.63
2. Online
3. Cash
4. Gift Card
5. Debit Card

### Key Insight

Credit Card transactions represented the highest-value payment segment in the dataset.

---

## 📦 Order Status

Cancelled orders had an associated order value of:

**$276,396.21**

However, these orders should **not be treated as realized revenue**.

### Key Insight

The high value associated with cancelled orders represents a potential business risk. Understanding why high-value orders are cancelled could help identify operational, payment, delivery, inventory, or customer-experience problems.

---

## 🎟️ Coupon Analysis

`FREESHIP` was the most frequently used coupon:

* **313 orders**
* **$335,036.99** in associated order value

### Key Insight

FREESHIP appears to be an important promotional mechanism. However, high usage alone does not prove that the campaign is profitable.

Further analysis should compare:

* Orders with vs. without coupons
* Average order value
* Customer acquisition
* Repeat purchases
* Discount/shipping costs
* Profitability

---

## 📱 Referral Source Analysis

**Instagram** generated the highest number of orders:

**259 orders**

### Key Insight

Instagram appears to be the strongest referral source by order count and may represent an important channel for customer acquisition.

However, conversion volume should ideally be evaluated alongside revenue, customer retention, and acquisition cost before increasing marketing investment.

---

## 🔗 Relationship Analysis

The correlation between **UnitPrice** and **Quantity** was:

**r = 0.015**

This indicates an almost nonexistent linear relationship between product unit price and quantity purchased in this dataset.

### Key Insight

Within this dataset, higher-priced products were not strongly associated with either higher or lower purchase quantities.

> Correlation does not establish causation, and the result only describes the linear relationship observed in this dataset.

---

# 🔎 Key Business Insights

### 1. Customer retention is the biggest opportunity

Only **0.93% of customers placed more than one order**, indicating very low repeat purchasing.

### 2. Chair and Printer are the strongest products

Both generated approximately **$195.6K** in associated order value and were the leading products.

### 3. Credit Card is the leading payment method by order value

Credit Card generated approximately **$263.8K** in associated order value.

### 4. Sales vary significantly across months

June was the strongest month, while September was the weakest.

### 5. FREESHIP is the most-used coupon

The coupon appeared on **313 orders** and was associated with approximately **$335K** in order value.

### 6. Cancelled orders represent a significant risk

Cancelled orders were associated with **$276.4K** in order value, making cancellation analysis an important business opportunity.

### 7. Instagram is the leading referral channel

Instagram generated the highest number of orders among the referral sources.

### 8. Price and quantity have almost no linear relationship

The correlation coefficient of **0.015** suggests virtually no linear relationship between UnitPrice and Quantity.

---

# 💡 Business Recommendations

### 1. Improve Customer Retention

With only a 0.93% repeat-customer rate, the business should consider:

* Loyalty programs
* Personalized offers
* Post-purchase emails
* Re-engagement campaigns
* Customer segmentation

### 2. Prioritize High-Performing Products

Maintain appropriate inventory levels for strong-performing products such as **Chair and Printer** and consider targeted promotional campaigns.

### 3. Investigate Cancelled Orders

Analyze cancellation reasons and identify whether cancellations are related to:

* Payment issues
* Inventory problems
* Delivery delays
* Customer behavior
* Order processing issues

### 4. Evaluate Coupon Effectiveness

FREESHIP has high usage, but usage alone does not demonstrate profitability.

The business should measure its impact on:

* Average order value
* Customer acquisition
* Repeat purchases
* Shipping costs
* Profit margins

### 5. Investigate Seasonal Patterns

Analyze the reasons behind the June peak and September decline to improve:

* Marketing campaigns
* Inventory planning
* Promotional timing
* Sales forecasting

### 6. Strengthen High-Performing Acquisition Channels

Instagram generated the highest number of orders. Further analysis should determine whether Instagram also produces high-value and high-retention customers.

### 7. Segment Customers

Customer segmentation could help identify:

* One-time customers
* Repeat customers
* High-value customers
* Coupon-driven customers
* Channel-specific customers

This could support more targeted marketing and improve customer lifetime value.

---

# 🛠️ Tools & Technologies

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook**
* **Microsoft Excel**

---

# 📁 Repository Structure

```text
E-Commerce-Sales-Analysis/
│
├── E_Commerce_Data_Analytics.ipynb
├── E_Commerce Dataset.xlsx
└── README.md
```

---

# 🎯 Conclusion

This project demonstrates a complete **data analyst workflow**, from raw data inspection and cleaning to exploratory analysis, visualization, and business recommendations.

The dataset was systematically prepared by handling missing values, validating dates, checking duplicate records and identifiers, cleaning text fields, and performing final data-quality validation.

Exploratory analysis then examined **business performance, customer behavior, product performance, payment methods, order status, coupon usage, referral channels, and variable relationships**.

The analysis highlighted several important business opportunities, particularly **improving customer retention, investigating cancelled orders, optimizing promotional campaigns, understanding seasonal demand, and strengthening effective customer acquisition channels**.

Overall, the project demonstrates how Python-based data analysis can transform a raw e-commerce dataset into **structured insights that can support business decision-making**.
