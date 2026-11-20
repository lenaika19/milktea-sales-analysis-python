# Milk Tea Shop Sales Analysis (Python)

> 🚧 **Status: In Progress.** Data cleaning and the fact table are done. KPI analysis is underway (5 of 8 steps complete); charts and insights come next.

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
milktea-sales-analysis-python/
│
├── 1_data_cleaning.ipynb      # Cleaning all 3 files
├── 2_kpi_analysis.ipynb       # Fact table and KPIs (in progress)
├── fact_table.csv             # Transactions merged with menu and branches
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
- [x] Fact table (8,888 rows)
- [ ] KPI analysis
    - [x] Overall KPIs
    - [x] Revenue by branch, region and category
    - [x] Top 5 items
    - [x] Monthly, day-of-week and hourly patterns
    - [ ] Payment method share
    - [ ] Average rating by branch
    - [ ] Profit margin by category
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
| Missing customer type | Filled with "No Membership" |
| Inconsistent menu categories (milk tea, MilkTea, Snack…) | Standardized to 5 categories |
| Missing item cost (Takoyaki) | Filled with 45 |
| Inconsistent region labels (ncr, extra spaces) | Standardized |

Calculated fields added: `line_revenue` (qty × unit price), `line_expense` (qty × unit cost), `line_profit`.

---

## KPI Results So Far

| KPI | Value |
|---|---|
| Total revenue | ₱1,618,265 |
| Total transactions | 8,888 |
| Average order value (AOV) | ₱182.07 |
| Items sold | 16,489 |
| Profit margin | 65.5% |

**Early findings**
- **SM North** is the top branch (₱270,915); **Vista Mall Antipolo** is the lowest (₱119,950).
- **NCR** earns the most revenue, but it also has 4 of the 8 branches.
- **Milk Tea** is the top category (₱726,555), and 4 of the top 5 items by quantity are milk teas (led by Classic Milk Tea).
- **May** is the best month and **February** the weakest. **Fruit Tea** sales roughly double in April–May, during the hot season.
- **Saturday and Sunday** bring in the most revenue, and the busiest hour is **4 PM**.

## Next Steps

- Payment method share, average rating by branch and profit margin by category
- Charts: monthly revenue, revenue by branch, sales by hour, payment method share
- Written insights and recommendations

---

## Tools

Python · pandas · NumPy · Matplotlib · Jupyter Notebook

---

*Author: Aika Lynn Rueco*
