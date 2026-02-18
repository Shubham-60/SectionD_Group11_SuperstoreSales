<div align="center">

# Data Cleaning Documentation

*Superstore Sales: raw to analysis-ready.*

<img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&size=18&pause=1000&color=2D3748&center=true&vCenter=true&width=600&lines=Cleaning+Raw+Data...;Standardizing+Formats...;Validating+Quality...;Ready+for+Analysis" />

<br>

![Records](https://img.shields.io/badge/Records-12,617-blue?style=flat-square)
![Columns](https://img.shields.io/badge/Columns-18-green?style=flat-square)
![Completeness](https://img.shields.io/badge/Completeness-100%25-success?style=flat-square)
![Period](https://img.shields.io/badge/Period-2014--2017-orange?style=flat-square)

</div>

---

## 📊 Overview

Transformed raw Superstore sales data into a clean, analysis-ready dataset with complete coverage across all fields.

**At a glance**

| Item | Value |
|------|-------|
| Records | 12,617 |
| Columns | 18 |
| Period | 2014-2017 |
| Completeness | 100% |
| Output file | Cleaned_Dataset.xlsx |

---

## 🔄 Cleaning Pipeline

```mermaid
flowchart LR
    A[Raw Data<br/>19 Columns] --> B[Remove Row ID]
    B --> C[Fix Dates]
    C --> D[Impute Region]
    D --> E[Standardize Categories]
    E --> F[Clean Financials]
    F --> G[Clean Data<br/>18 Columns]

    style A fill:#fee2e2,color:#111827
    style G fill:#dcfce7,color:#111827
    style B fill:#dbeafe,color:#111827
    style C fill:#dbeafe,color:#111827
    style D fill:#dbeafe,color:#111827
    style E fill:#dbeafe,color:#111827
    style F fill:#dbeafe,color:#111827
```

---

## 🛠️ Cleaning Actions

| Column | Issue | Solution | Result |
|--------|-------|----------|--------|
| **Row ID** | Redundant identifier | Dropped column | Leaner structure |
| **Order Date** | Text format | Convert to datetime | Time-series ready |
| **Ship Date** | Text format | Convert to datetime | Logistics ready |
| **Region** | 638 missing (5%) | Postal code mapping | 100% coverage |
| **Category** | 4 variants | Standardize to 3 labels | Consistent grouping |
| **Sales** | Currency strings | Convert to float | Calculation ready |
| **Discount** | 910 missing (7%) | Fill with 0.00 | Complete dataset |
| **Profit** | 882 missing (7%) | Clean and convert | Analysis ready |

---

## 📂 Dataset Structure

| Group | Fields |
|-------|--------|
| Identifiers | Order ID, Customer ID, Product ID |
| Time | Order Date (datetime), Ship Date (datetime) |
| Geography | Country, Region, State, City, Postal Code |
| Shipping | ShipMode (4 types) |
| Products | Category (3 types), Sub Category (17 types), Product Name |
| Metrics | Sales (float), Quantity (int), Discount (float), Profit (float) |

---

## 📋 Data Quality

**Before cleaning**
- ❌ 2,430 missing values (11%)
- ❌ Inconsistent date formats
- ❌ Mixed category naming
- ❌ Currency formatting issues

**After cleaning**
- ✅ 0 missing values (0%)
- ✅ Standardized datetime format
- ✅ 3 clean categories
- ✅ Numeric financial data

---

## 🎯 Key Transformations

**Region imputation**
- Method: Postal code lookup table
- Coverage: 638 missing → 0 missing (100%)
- Regions: East, West, Central, South

**Category standardization**
- `Tech` → `Technology`
- `Furni` → `Furniture`
- `OfficeSupply` → `Office Supplies`

**Financial cleanup**
- Sales: Remove currency symbols, convert to float
- Discount: Fill missing with 0.00 (no-discount assumption)
- Profit: Clean text, convert to numeric

---

## ✅ Validation Results

| Check | Status | Notes |
|-------|--------|-------|
| Missing values | ✅ 0 across all columns | Complete dataset |
| Date consistency | ✅ Ship Date ≥ Order Date | Valid chronology |
| Discount range | ✅ 0.0 - 0.8 | Range validated |
| Category values | ✅ 3 standardized | No outliers |
| Region values | ✅ 4 standardized | All mapped |
| Numeric formats | ✅ All converted | Sales, Discount, Profit |

---

<div align="center">

**Status:** Ready For Calculation  
**Quality Score:** 100%  
**File:** Cleaned_Dataset.xlsx

</div>