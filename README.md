# 🚀 Enterprise E-Commerce ETL Pipeline & Data Cleaning

A robust, production-grade ETL (Extract, Transform, Load) pipeline built in **Python (Pandas & NumPy)** designed to process, audit, and normalize messy multi-branch retail data across 12 stores.

---

## 📊 Project Overview
- **Raw Data Ingestion:** 52,000 raw transactions and 3,076 customer profiles.
- **Data Quality Challenges:** Severe customer duplication, mixed UTC/local timezones, inconsistent SKU and phone formats, missing catalog prices, and invalid future-dated entries.
- **Final Output:** 4 clean, analytics-ready datasets and a comprehensive Executive Audit Report.

---

## 🛠️ Technical Stack & Methods
- **Language:** Python 3.x
- **Core Libraries:** Pandas, NumPy (Vectorized cleaning and transformation)
- **Data Standards Applied:**
  - **Transitive Deduplication:** Merging duplicate customer profiles via email and normalized 10-digit phone matching.
  - **Timezone Normalization:** Converting UTC timestamps to local store time (UTC-3) to prevent end-of-month revenue attribution errors.
  - **Imputation & Validation:** Automated price matching from official product catalogs and rigorous rejection logging.

---

## 📁 Deliverables & Data Schema
1. **`customers_clean.csv`**: 2,500 unique, deduplicated customer profiles (Standardized IDs: `C0001`–`C2500`).
2. **`transactions_clean.csv`**: 45,348 validated sales transactions ($5.06B total reconciled revenue).
3. **`transactions_rejected.csv`**: 2,652 audited rejection logs containing anomalies, future dates, and invalid records.
4. **`monthly_sales.csv`**: Aggregated monthly performance metrics per store.

---

## 📈 Pipeline Performance Summary
| Metric | Raw Input | Cleaned / Processed | Action / Result |
| :--- | :--- | :--- | :--- |
| **Customers** | 3,076 | 2,500 | 576 duplicates merged |
| **Transactions** | 52,000 | 45,348 valid | 4,000 duplicates + 2,652 rejections isolated |
| **Total Revenue** | — | $5.06 Billion | 100% reconciled across 12 stores |
