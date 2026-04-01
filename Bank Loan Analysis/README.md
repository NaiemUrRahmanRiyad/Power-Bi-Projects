<div align="center">

<!-- ANIMATED HEADER BANNER -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a7a4a,50:2ecc71,100:145a32&height=200&section=header&text=🏦%20Bank%20Loan%20Analysis&fontSize=42&fontColor=ffffff&fontAlignY=38&desc=Power%20BI%20Dashboard%20Project&descAlignY=60&descSize=18&animation=fadeIn" width="100%"/>

<!-- BADGES ROW 1 -->
<br/>

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Measures-00897B?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power%20Query-M%20Language-217346?style=for-the-badge&logo=microsoft&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-Data%20Source-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)

<!-- BADGES ROW 2 -->

![Status](https://img.shields.io/badge/Status-✅%20Completed-2ecc71?style=flat-square)
![Pages](https://img.shields.io/badge/Pages-3%20Interactive-1abc9c?style=flat-square)
![Records](https://img.shields.io/badge/Records-38.6K%20Loans-16a085?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-27ae60?style=flat-square)
![Last Updated](https://img.shields.io/badge/Last%20Updated-2024-2ecc71?style=flat-square)

<br/>

> ### *"Turning raw loan data into clarity — one insight at a time."*

<br/>

</div>

---

<div align="center">

## 📸 Dashboard Snapshots

</div>

<table>
<tr>
<td align="center" width="33%">

### 📋 Summary View
![Summary](screenshots/b3.png)
*Executive KPIs + Good/Bad Loan split*

</td>
<td align="center" width="33%">

### 🗺️ Overview View
![Overview](screenshots/b2.png)
*Trends, maps & distribution charts*

</td>
<td align="center" width="33%">

### 🔍 Details View
![Details](screenshots/b1.png)
*Record-level loan drill-through*

</td>
</tr>
</table>

---

## 🌟 Why This Dashboard?

<table>
<tr>
<td>

```
📊  38,576 loans analyzed
💰  $435.8M total funded
💵  $473.1M total received
📈  15.8% MoM growth
✅  86.18% good loan rate
⚠️   13.82% charge-off rate
```

</td>
<td>

This Power BI dashboard transforms raw bank loan data into a **strategic decision-making tool** for:

- 🏛️ **Bank Executives** — portfolio health at a glance
- 📊 **Financial Analysts** — deep-dive trend analysis
- 🔍 **Risk Officers** — bad loan segmentation
- 💼 **Loan Officers** — borrower behavior insights

</td>
</tr>
</table>

---

## 🗂️ Project Architecture

```
╔══════════════════════════════════════════════════════════════════╗
║                    BANK LOAN ANALYSIS PIPELINE                   ║
╠══════════════════════════════════════════════════════════════════╣
║                                                                  ║
║   📥 RAW DATA          🔧 TRANSFORM         📊 VISUALIZE        ║
║   ─────────────        ─────────────        ──────────────       ║
║   loan_data.csv   →    Power Query     →    3 Report Pages       ║
║   (38.6K rows)         M Language           Summary              ║
║                        Data Cleaning        Overview             ║
║                        Type casting         Details              ║
║                              ↓                                   ║
║                        DAX Measures                              ║
║                        KPIs / MTD / MoM                          ║
║                        Good/Bad Loan %                           ║
╚══════════════════════════════════════════════════════════════════╝
```

---

## 📊 Dashboard Deep Dive

### ━━━ Page 1 · SUMMARY ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

<div align="center">

#### 🔢 Top KPI Cards

| 🏷️ Metric | 📌 Total | 📅 MTD | 📈 MoM |
|-----------|---------|--------|--------|
| 📝 Loan Applications | **38.6K** | 4,314 | `+6.9%` ↑ |
| 💸 Funded Amount | **$435.8M** | $54.0M | `+13.0%` ↑ |
| 💰 Amount Received | **$473.1M** | $58.1M | `+15.8%` ↑ |
| 📉 Avg Interest Rate | **12.0%** | 12.4% | `+3.5%` ↑ |
| ⚖️ Avg DTI | **13.3%** | 13.7% | `+2.7%` ↑ |

</div>

<br/>

#### 🟢 Good Loans vs 🔴 Bad Loans

```
  GOOD LOANS ████████████████████████████████████░░░░░░  86.18%
  BAD  LOANS ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░██████  13.82%
```

<table>
<tr>
<td align="center">

**✅ GOOD LOANS**

| Metric | Value |
|--------|-------|
| Applications | `33,200` |
| Funded Amount | `$370.2M` |
| Received Amount | `$435.8M` |
| Return Ratio | `117.7%` ✅ |

</td>
<td align="center">

**❌ BAD LOANS (Charged Off)**

| Metric | Value |
|--------|-------|
| Applications | `5,300` |
| Funded Amount | `$65.5M` |
| Received Amount | `$37.3M` |
| Recovery Rate | `56.9%` ⚠️ |

</td>
</tr>
</table>

#### 📋 Loan Status Breakdown

| Loan Status | Applications | Funded Amount | Amount Received | MTD Funded | Avg Interest | Avg DTI |
|:-----------:|:------------:|:-------------:|:---------------:|:----------:|:------------:|:-------:|
| ✅ Fully Paid | `32,145` | $351,358,350 | $411,586,256 | $41,302,025 | 11.64% | 13.17% |
| 🔄 Current | `1,098` | $18,866,500 | $24,199,914 | $3,946,625 | 15.10% | 14.72% |
| ❌ Charged Off | `5,333` | $65,532,225 | $37,284,763 | $8,732,775 | 13.88% | 14.00% |
| **Grand Total** | **38,576** | **$435,757,075** | **$473,070,933** | **$53,981,425** | **12.05%** | **13.33%** |

---

### ━━━ Page 2 · OVERVIEW ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

#### 📈 Monthly Trend — Amount Received

```
$60M ┤                                                    ●─● $58M
$55M ┤                                               ●─●
$50M ┤                                          ●─●
$45M ┤                                     ●─●
$40M ┤                               ●─●
$35M ┤                          ●─●
$30M ┤                     ●─●
$28M ┤  ●─●─●─●
     └──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──┬──
       Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec
```

> 📌 **Insight:** Consistent month-over-month growth — repayments nearly **doubled** from January to December.

<br/>

#### 🍩 Loan Term Distribution

```
  ╭─────────────────────────────╮
  │   36 Months  ████████  62%  │  ≈ $294M
  │   60 Months  █████     38%  │  ≈ $179M
  ╰─────────────────────────────╯
```

#### 👷 Repayments by Employment Length

| Employment | Amount | Share |
|-----------|--------|-------|
| 10+ years | **$126M** | `████████████` 26.9% |
| 2 years | $49M | `████░░░░░░░░` 10.5% |
| 3 years | $48M | `████░░░░░░░░` 10.2% |
| < 1 year | $48M | `████░░░░░░░░` 10.2% |
| 4 years | $41M | `███░░░░░░░░░` 8.7% |
| 5 years | $40M | `███░░░░░░░░░` 8.5% |

#### 🎯 Repayments by Loan Purpose

| Purpose | Amount | Visual |
|---------|--------|--------|
| 🔄 Debt Consolidation | **$0.25bn** | `████████████████░░░░` |
| 💳 Credit Card | $0.07bn | `████░░░░░░░░░░░░░░░░` |
| 🏠 Home Improvement | $0.04bn | `██░░░░░░░░░░░░░░░░░░` |
| 📦 Other | $0.03bn | `█░░░░░░░░░░░░░░░░░░░` |
| 🏢 Small Business | $0.02bn | `█░░░░░░░░░░░░░░░░░░░` |
| 🛒 Major Purchase | $0.02bn | `█░░░░░░░░░░░░░░░░░░░` |

---

### ━━━ Page 3 · DETAILS ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Fully interactive drill-through table with row-level loan data. Every row is clickable and filterable.

| ID | Purpose | Ownership | Grade | Issue Date | Funded | Int Rate | Installment | Received |
|:--:|---------|:---------:|:-----:|:----------:|-------:|:--------:|:-----------:|--------:|
| 54734 | Debt Consolidation | RENT | `B4` | 09-08-2021 | $25,000 | 12% | $829.10 | $29,330 |
| 55742 | Credit Card | RENT | `B5` | 08-05-2021 | $7,000 | 11% | $228.22 | $8,216 |
| 57416 | Debt Consolidation | RENT | `C3` | 09-11-2021 | $10,800 | 14% | $366.86 | $13,208 |
| 58915 | Debt Consolidation | RENT | `B3` | 08-04-2021 | $7,500 | 10% | $162.34 | $5,844 |
| 61419 | Debt Consolidation | RENT | `D2` | 10-02-2021 | $5,600 | 15% | $194.02 | $6,475 |
| 68381 | Debt Consolidation | RENT | `A5` | 08-03-2021 | $6,625 | 9% | $209.54 | $7,542 |
| 69550 | Debt Consolidation | RENT | `D3` | 10-05-2021 | $11,200 | 15% | $268.40 | $15,924 |

---

## 🎛️ Interactive Filters

All pages are connected via **4 global slicers**:

```
┌─────────────────────────────────────────────────────────────────┐
│  🔘 Select Measure    🗺️ State (All)    📊 Grade (All)           │
│     Total Funded      ▼ Filter by       ▼ A B C D E F G         │
│     Total Received       US State                               │
│     Avg Interest                        🎯 Purpose (All)        │
│     Avg DTI                             ▼ Debt Consolidation    │
│                                            Credit Card          │
│                                            Home Improvement...  │
└─────────────────────────────────────────────────────────────────┘
```

---

## ⚙️ DAX Measures Reference

<details>
<summary>📐 <strong>Click to expand — All DAX Measures</strong></summary>

```DAX
-- ═══════════════════════════════════
-- 📝 LOAN APPLICATIONS
-- ═══════════════════════════════════

Total Loan Applications =
    COUNT(loan_data[id])

MTD Loan Applications =
    CALCULATE(COUNT(loan_data[id]),
    DATESMTD(loan_data[issue_date]))

PMTD Loan Applications =
    CALCULATE(COUNT(loan_data[id]),
    DATESMTD(EOMONTH(loan_data[issue_date], -1)))

MoM Loan Applications % =
    DIVIDE(
        [MTD Loan Applications] - [PMTD Loan Applications],
        [PMTD Loan Applications]
    )


-- ═══════════════════════════════════
-- 💰 FUNDED & RECEIVED AMOUNTS
-- ═══════════════════════════════════

Total Funded Amount =
    SUM(loan_data[loan_amount])

MTD Funded Amount =
    CALCULATE(SUM(loan_data[loan_amount]),
    DATESMTD(loan_data[issue_date]))

Total Amount Received =
    SUM(loan_data[total_payment])

MTD Amount Received =
    CALCULATE(SUM(loan_data[total_payment]),
    DATESMTD(loan_data[issue_date]))

MoM Amount Received % =
    DIVIDE(
        [MTD Amount Received] - [PMTD Amount Received],
        [PMTD Amount Received]
    )


-- ═══════════════════════════════════
-- 📉 INTEREST RATE & DTI
-- ═══════════════════════════════════

Avg Interest Rate =
    AVERAGE(loan_data[int_rate])

MTD Avg Interest Rate =
    CALCULATE(AVERAGE(loan_data[int_rate]),
    DATESMTD(loan_data[issue_date]))

Avg DTI =
    AVERAGE(loan_data[dti])

MTD Avg DTI =
    CALCULATE(AVERAGE(loan_data[dti]),
    DATESMTD(loan_data[issue_date]))


-- ═══════════════════════════════════
-- ✅ GOOD LOAN MEASURES
-- ═══════════════════════════════════

Good Loan Applications =
    CALCULATE(COUNT(loan_data[id]),
    loan_data[loan_status] IN {"Fully Paid", "Current"})

Good Loan % =
    DIVIDE([Good Loan Applications], [Total Loan Applications])

Good Loan Funded Amount =
    CALCULATE(SUM(loan_data[loan_amount]),
    loan_data[loan_status] IN {"Fully Paid", "Current"})

Good Loan Received Amount =
    CALCULATE(SUM(loan_data[total_payment]),
    loan_data[loan_status] IN {"Fully Paid", "Current"})


-- ═══════════════════════════════════
-- ❌ BAD LOAN MEASURES
-- ═══════════════════════════════════

Bad Loan Applications =
    CALCULATE(COUNT(loan_data[id]),
    loan_data[loan_status] = "Charged Off")

Bad Loan % =
    DIVIDE([Bad Loan Applications], [Total Loan Applications])

Bad Loan Funded Amount =
    CALCULATE(SUM(loan_data[loan_amount]),
    loan_data[loan_status] = "Charged Off")

Bad Loan Received Amount =
    CALCULATE(SUM(loan_data[total_payment]),
    loan_data[loan_status] = "Charged Off")
```

</details>

---

## 🗂️ Data Dictionary

<details>
<summary>📋 <strong>Click to expand — All Fields Explained</strong></summary>

| # | Column | Data Type | Description |
|---|--------|-----------|-------------|
| 1 | `id` | Integer | Unique loan identifier |
| 2 | `loan_status` | Text | Fully Paid / Current / Charged Off |
| 3 | `loan_amount` | Currency | Amount of loan funded ($) |
| 4 | `funded_amnt_inv` | Currency | Amount funded by investors |
| 5 | `term` | Text | 36 months / 60 months |
| 6 | `int_rate` | Decimal | Annual interest rate (%) |
| 7 | `installment` | Currency | Monthly repayment amount |
| 8 | `grade` | Text | A → G credit grade |
| 9 | `sub_grade` | Text | A1–G5 sub-grade |
| 10 | `emp_length` | Text | Employment duration |
| 11 | `home_ownership` | Text | RENT / MORTGAGE / OWN |
| 12 | `annual_inc` | Currency | Borrower's annual income |
| 13 | `issue_date` | Date | Loan origination date |
| 14 | `purpose` | Text | Reason for the loan |
| 15 | `addr_state` | Text | U.S. state code |
| 16 | `dti` | Decimal | Debt-to-income ratio |
| 17 | `total_payment` | Currency | Total amount repaid |

</details>

---

## 🛠️ Tech Stack

<div align="center">

| Tool | Version | Role |
|------|---------|------|
| ![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-F2C811?logo=powerbi&logoColor=black) | Latest | Visualization & Publishing |
| ![Power Query](https://img.shields.io/badge/Power%20Query-M%20Language-217346?logo=microsoft) | — | ETL & Data Transformation |
| ![DAX](https://img.shields.io/badge/DAX-Expressions-00897B?logo=microsoftexcel) | — | KPIs, MTD, MoM, % Measures |
| ![Excel](https://img.shields.io/badge/Excel%20%2F%20CSV-Data%20Source-217346?logo=microsoftexcel) | — | Raw Dataset |

</div>

---

## 🚀 Getting Started

### Prerequisites
- ✅ [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
- ✅ The `loan_data.csv` file from `/data` folder

### Installation

```bash
# 1️⃣  Clone the repository
git clone https://github.com/your-username/bank-loan-analysis-dashboard.git

# 2️⃣  Navigate into the project folder
cd bank-loan-analysis-dashboard
```

```
# 3️⃣  Open Power BI Desktop
   File → Open Report → Bank_Loan_Analysis.pbix

# 4️⃣  Update Data Source (if needed)
   Home → Transform Data → Data Source Settings
   → Update path to your local loan_data.csv

# 5️⃣  Click Refresh & Explore! 🎉
```

---

## 📁 Repository Structure

```
🏦 bank-loan-analysis-dashboard/
│
├── 📊 Bank_Loan_Analysis.pbix        ← Main Power BI Report
│
├── 📂 data/
│   └── 📄 loan_data.csv              ← Raw dataset (38.6K rows)
│
├── 📂 screenshots/
│   ├── 🖼️ b1.png                     ← Details Page
│   ├── 🖼️ b2.png                     ← Overview Page
│   └── 🖼️ b3.png                     ← Summary Page
│
└── 📄 README.md                      ← You are here!
```

---

## 💡 Key Business Insights

> 🔍 Findings from the dashboard analysis:

| # | Insight | Impact |
|---|---------|--------|
| 1 | ✅ **86.18% Good Loan Rate** | Portfolio is healthy & low-risk |
| 2 | ⚠️ **$28.2M net loss on bad loans** ($65.5M funded, only $37.3M recovered) | Tighten credit scoring for D/E/F grades |
| 3 | 📅 **Repayments doubled Jan → Dec** ($28M → $58M) | Strong portfolio maturation trend |
| 4 | 🏦 **Debt consolidation = 55%+ of all loans** | Core product driving revenue |
| 5 | 👷 **10+ yr employees repay 2.5x more** than < 1 yr employees | Employment stability = repayment reliability |
| 6 | ⏱️ **36-month loans dominate** (62%) | Borrowers prefer shorter commitments |
| 7 | 🏠 **RENT borrowers are the largest segment** | Target demographic for product design |

---

## 🔮 Future Enhancements

- [ ] 🤖 Add **predictive default scoring** using ML integration
- [ ] 📧 Set up **automated email alerts** for high-risk loan spikes
- [ ] 🌐 Publish to **Power BI Service** with scheduled refresh
- [ ] 📱 Create a **mobile-optimized** layout
- [ ] 🔗 Connect to **live SQL database** instead of static CSV
- [ ] 📊 Add **YoY (Year-over-Year)** comparison metrics
- [ ] 🗺️ Drill-down to **county-level** geographic analysis

---

## 🤝 Contributing

Contributions are warmly welcome! Here's how:

```
1. 🍴 Fork this repo
2. 🌿 Create a branch:  git checkout -b feature/amazing-feature
3. 💾 Commit changes:   git commit -m "✨ Add amazing feature"
4. 📤 Push:             git push origin feature/amazing-feature
5. 🔁 Open a Pull Request
```

---

## 📄 License

```
MIT License — feel free to use, modify, and distribute.
See LICENSE file for full details.
```

---

## 👤 Author

<div align="center">

**Your Name**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github)](https://github.com/your-username)
[![Portfolio](https://img.shields.io/badge/Portfolio-Visit-2ecc71?style=for-the-badge&logo=firefox)](https://your-portfolio.com)

</div>

---

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:145a32,50:2ecc71,100:1a7a4a&height=120&section=footer&animation=fadeIn" width="100%"/>

### ⭐ If this project helped you, please give it a star!

*Made with ❤️ and Power BI*

</div>
