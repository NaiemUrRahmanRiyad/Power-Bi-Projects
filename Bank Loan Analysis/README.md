# Bank Loan Report - Power BI Dashboard

![Power BI Dashboard](https://i.ibb.co.com/5hNWZ16V/b1.png)

**A comprehensive interactive Power BI dashboard for analyzing bank loan performance, loan applications, funding trends, and risk insights.**

---

## 📋 Project Overview

This Power BI project delivers an **end-to-end business intelligence solution** for a bank’s loan portfolio. It transforms raw loan data into actionable insights through interactive visualizations, key performance indicators (KPIs), and drill-down capabilities.

The dashboard helps stakeholders:
- Monitor overall loan health (good vs. bad loans)
- Track funding and repayment trends over time
- Identify high-risk segments by purpose, grade, state, home ownership, and employment length
- Analyze individual loan details with full filtering

**Dataset Period**: Loans issued primarily in 2021 (based on `Issue Date` column).

**Total Records**: ~38,576 loans (Grand Total from Loan Status table).

---

## ✨ Key Features

### 1. **Executive Summary Dashboard**
- **Top KPIs** (with Month-over-Month % change):
  - Total Loan Applications: **38.6K** (MTD) | +6.9% MoM
  - Total Funded Amount: **$435.8M** (MTD) | +13.0% MoM
  - Total Amount Received: **$473.1M** (MTD) | +15.8% MoM
  - Average Interest Rate: **12.0%** (MTD) | +3.5% MoM
  - Average Debt-to-Income (DTI) Ratio: **13.3%** (MTD) | +2.7% MoM
- **Good Loan Issued** (86.18%)
  - Good Loan Applications: 33.2K
  - Good Loan Received Amount: $435.8M
  - Good Loan Funded Amount: $370.2M
- **Bad Loan Issued** (13.82%)
  - Bad Loan Applications: 5.3K
  - Bad Loan Funded Amount: $65.5M
  - Bad Loan Received Amount: $37.3M
- **Loan Status Breakdown** (table):
  | Loan Status   | Applications | Funded Amount   | Received Amount | MTD Funded | MoM Received | Avg Interest | Avg DTI |
  |---------------|--------------|-----------------|-----------------|------------|--------------|--------------|---------|
  | Fully Paid    | 32,145      | $351.36M       | $411.59M       | $41.30M   | 11.64%      | 12.72%      | 13.17% |
  | Current       | 1,098       | $18.87M        | $24.20M        | $3.95M    | 32.73%      | 15.10%      | 14.73% |
  | Charged Off   | 5,333       | $65.53M        | $37.28M        | $8.73M    | 33.30%      | 13.88%      | 14.00% |
  | **Grand Total** | **38,576** | **$435.76M**  | **$473.07M**  | **$53.98M** | **15.84%** | **12.05%** | **13.33%** |

### 2. **Overview Dashboard**
- **Trend Analysis**:
  - Line chart: **Total Amount Received by Month** (Jan–Dec 2021) — steady growth from $28M → $58M
- **Geographic Analysis**:
  - US Map: **Total Amount Received by State** (color intensity by volume)
- **Segment Analysis**:
  - Pie chart: **Total Amount Received by Term** (36 months vs 60 months)
  - Horizontal bar: **Total Amount Received by Employee Length** (10+ years = $126M — highest)
  - Horizontal bar: **Total Amount Received by Purpose** (Debt consolidation = $0.25bn — dominant)
  - Horizontal bar: **Total Amount Received by Home Ownership** (RENT vs MORTGAGE)

### 3. **Details (Drill-Down) Table**
- Full granular view of every loan with columns:
  - `Id`, `purpose`, `Home Ownership`, `Grade`, `sub_grade`, `Issue Date`
  - `Total Funded Amount`, `Sum of int_rate`, `Sum of installment`, `Total Amount Received`
- All top KPIs and charts are **fully interactive** and filter the table in real-time.

### 4. **Advanced Filters (Slicers)**
- **State** (All / individual states)
- **Grade** (All / A–E)
- **Purpose** (All / Debt consolidation, credit card, etc.)
- **Select Measure** dropdown for dynamic metric switching

---

## 🛠️ Technologies Used

- **Power BI Desktop** (latest version recommended)
- **DAX** (for calculated measures: Good/Bad Loan logic, MoM %, etc.)
- **Power Query** (data cleaning & transformation)
- **Data Model**: Star schema with fact table (`loans`) and dimension tables (`date`, `state`, `grade`, etc.)
- **Visuals**: Native Power BI visuals + custom themes (green banking theme)

---

## 📊 Data Source & Structure

**Source**: Lending Club style loan dataset (CSV/Excel).

**Key Columns**:
- `id`, `purpose`, `home_ownership`, `grade`, `sub_grade`
- `issue_date`, `total_funded_amount`, `int_rate`, `installment`
- `total_amount_received`, `term`, `emp_length`, `addr_state`
- Derived flags: `Good Loan` / `Bad Loan` (based on `loan_status`)

**Data Volume**: ~38.6K rows.

---

## 📸 Screenshots

(Upload your three exported images to a `screenshots/` folder in the repo)

1. `b1.png` → Summary Dashboard
2. `b2.png` → Overview Visualizations
3. `b3.png` → Details Table View

---

## 🚀 How to Use

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/bank-loan-powerbi-dashboard.git

Open Bank Loan Report.pbix in Power BI Desktop.
(Optional) Refresh data if you have the source file.
Interact with slicers and click on any visual to cross-filter.

Live Demo: https://app.fabric.microsoft.com/view?r=eyJrIjoiNTM5M2Q2NDYtYThlYy00YzY4LThhNDItZmRkMTk0Zjk2NzBjIiwidCI6ImM4ODk5ZDQ4LTIyN2MtNDRhZS05YzIxLWQwZDkyYmU5ODRjYyIsImMiOjEwfQ%3D%3D

🔍 Key Business Insights (Extracted from Dashboard)

Portfolio Health: 86.18% of loans are "Good" — strong overall performance.
Repayment Trend: Total Amount Received ($473M) exceeds Funded Amount ($436M) → positive cash flow.
Risk Concentration:
Debt consolidation and credit card loans dominate volume.
RENT home ownership borrowers represent the largest segment.
10+ years employment length borrowers contribute the highest repayment ($126M).

Seasonality: Loan activity and repayments increase steadily through the year, peaking in Q4.
Term Preference: 60-month loans significantly outweigh 36-month loans in total value received.


🛠️ Future Enhancements (Roadmap)

 Predictive modeling (loan default probability using Python/R integration)
 Loan approval recommender (what-if analysis)
 Customer segmentation using clustering
 Mobile-optimized layout
 Automated monthly refresh via Power BI Service + Gateway
 Add repayment schedule forecasting