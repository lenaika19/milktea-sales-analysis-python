# Milk Tea Shop Sales Analysis (Python)

> 🚧 **Status: In Progress.** Data cleaning is done; KPI analysis, charts and insights are being worked on.

A personal practice project analyzing one year of sales from a milk tea chain with 8 branches across the Philippines. The goal is to clean messy transaction data and answer:

> **Which branches, products and times drive sales, and how do customers pay and rate their orders?**

Built with **Python, pandas, NumPy and Matplotlib** in Jupyter Notebook.

---

## Dataset

| File | Rows | Description |
|---|---|---|
| `transactions.csv` | 9,070 | One row per item sold: date/time, branch, item, quantity, price, payment method, customer type, rating |
| `menu.csv` | 24 | Menu items with category, price and cost |
| `branches.csv` | 8 | Branch name, city, region and opening date |

Period: **January – December 2025**. The data is synthetic, made for practice, and intentionally messy.

---

## Project Structure

```
sales_data_milktea/
│
├── 1_data_cleaning.ipynb      # Cleaning all 3 files
├── branches.csv               # Raw data
├── menu.csv
├── transactions.csv
│
├── cleaned_data/
│   ├── branches_clean.csv
│   ├── menu_clean.csv
│   └── transactions_clean.csv
│
└── README.md
```

---

## Progress

- [x] Data profiling (shape, types, missing values, duplicates)
- [x] Data cleaning
- [ ] KPI analysis
- [ ] Visualizations
- [ ] Insights and recommendations

---

## Data Cleaning

| Issue found | Action taken |
|---|---|
| 70 exact duplicate transactions | Removed |
| Quantity of 0 or negative | Removed |
| Transactions with unknown branch or item (orphans) | Removed |
| Mixed date formats (4 different styles) | Converted to datetime |
| Prices stored as text with ₱ | Removed symbol, converted to number |
| Missing unit prices | Filled with the menu price |
| 13 spellings of payment method (gcash, G-Cash, PayMaya…) | Standardized to GCash, Cash, Card, Maya |
| Missing customer type | Filled with "Unknown" |
| Inconsistent menu categories (milk tea, MilkTea, Snack…) | Standardized to 5 categories |
| Missing item cost (Takoyaki) | Filled with 45 |
| Inconsistent region labels (ncr, extra spaces) | Standardized |

Calculated fields added: `line_revenue` (qty × unit price), `line_expense` (qty × unit cost), `line_profit`.

---

## Planned Analysis

- Total revenue, transactions, average sale per transaction and profit margin
- Revenue by branch, region and category
- Top-selling items
- Monthly, day-of-week and hourly sales patterns
- Payment method share
- Average rating by branch
- Profit margin by category

---

## Tools

Python · pandas · NumPy · Matplotlib · Jupyter Notebook

---

*Author: Aika Lynn Rueco*
