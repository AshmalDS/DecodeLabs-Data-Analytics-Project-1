# DecodeLabs Data Analytics Internship — Project 1

## Data Cleaning & Preparation 🧹

This project is **Project 1** of my Data Analytics Internship at DecodeLabs.

The objective of this project was to clean and prepare the provided **Dataset for Data Analytics** by identifying missing values, checking duplicates, correcting data formats, and validating the final dataset.

## Dataset

* **Rows:** 1,200
* **Columns:** 14
* **Dataset:** `Dataset for Data Analytics.xlsx`

## Tools & Technologies

* Python
* Pandas
* NumPy
* Jupyter Notebook
* Excel

## Data Cleaning Tasks

### 1. Dataset Inspection

* Examined the first few records using `head()`
* Checked the number of rows and columns
* Reviewed column information and data types using `info()`
* Used `describe()` to understand numerical and categorical columns

### 2. Missing Values

Missing values were identified using Pandas.

The `CouponCode` column contained **309 missing values**.

These missing values were handled by replacing them with:

```text
No_CouponCode
```

### 3. Duplicate Records

The dataset was checked for completely duplicated rows.

**Result:** 0 duplicate rows.

### 4. Duplicate Order IDs

`OrderID` was checked to ensure that each order had a unique identifier.

**Result:** 0 duplicate OrderIDs.

### 5. Date Validation

The `Date` column was converted to the appropriate datetime format and checked for invalid dates.

**Result:** 0 invalid dates.

### 6. Text Cleaning

Leading and trailing whitespace was removed from the `Product` column to improve consistency.

## Final Data Validation

| Check              |           Result |
| ------------------ | ---------------: |
| Missing values     |                0 |
| Duplicate rows     |                0 |
| Duplicate OrderIDs |                0 |
| Invalid dates      |                0 |
| Date data type     | `datetime64[ns]` |


## Conclusion

The dataset was successfully cleaned and validated using Python and Pandas. The final dataset contains no missing values, duplicate rows, duplicate OrderIDs, or invalid dates and is ready for further data analysis.

This project provided practical experience in **data cleaning, data validation, missing-value handling, duplicate detection, data-type validation, and data preparation**.
