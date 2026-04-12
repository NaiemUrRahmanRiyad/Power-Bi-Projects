<div align="center">

<!-- Header Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100=0f3460&height=200&section=header&text=Jaboo%20Trip%20Analysis&fontSize=48&fontColor=e94560&fontAlignY=38&desc=Power%20BI%20Business%20Intelligence%20Dashboard&descAlignY=58&descSize=18&descColor=a8b2d8&animation=fadeIn" width="100%"/>

<br/>

<!-- Badges Row 1 -->
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Advanced-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](https://learn.microsoft.com/en-us/dax/)
[![Star Schema](https://img.shields.io/badge/Star%20Schema-Data%20Model-6C3483?style=for-the-badge&logo=databricks&logoColor=white)](https://en.wikipedia.org/wiki/Star_schema)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)](https://github.com/)

<!-- Badges Row 2 -->
[![Dataset Size](https://img.shields.io/badge/Dataset-103%2C000%2B%20Rows-FF6B35?style=for-the-badge&logo=databricks&logoColor=white)](#-dataset)
[![File Size](https://img.shields.io/badge/File%20Size-~12%20MB-blue?style=for-the-badge&logo=files&logoColor=white)](#-dataset)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](./LICENSE)
[![Last Updated](https://img.shields.io/badge/Updated-2025-9B59B6?style=for-the-badge)](https://github.com/)

<br/>

<p align="center">
  <strong>Transforming raw ride-sharing data into strategic business intelligence.</strong><br/>
  <em>Built with Power BI · Powered by Advanced DAX · Designed for Decision Makers</em>
</p>

</div>

---

## 📌 Table of Contents

| Section | Description |
|:--------|:------------|
| [🎯 Business Problem](#-business-problem) | What question this dashboard answers |
| [📊 Dataset](#-dataset) | Source, size, schema, and download |
| [💡 Key Insights](#-key-insights) | Strategic findings at a glance |
| [📐 Data Model](#-data-model) | Star schema design |
| [⚙️ DAX Measures](#️-key-dax-measures) | Core business logic |
| [📈 Dashboard Highlights](#-dashboard-highlights) | Visual features breakdown |
| [🧠 Skills Demonstrated](#-skills-demonstrated) | Technical competencies |
| [🚀 How to Run](#-how-to-run) | Setup instructions |
| [📈 Business Impact](#-business-impact) | Real-world value |
| [🧪 Future Improvements](#-future-improvements) | Roadmap |
| [👨‍💻 Author](#-author) | About the creator |

---

## 🎯 Business Problem

> **"When, where, and how are trips happening — and how can the business improve?"**

Ride-sharing companies like Uber operate in a highly competitive, data-rich environment. Raw trip logs alone reveal nothing — this dashboard transforms them into a **living intelligence system** that answers critical operational questions:

```
📊  Where is demand peaking?          🚕  Are vehicles allocated efficiently?
💰  Which routes generate most revenue?   😊  What drives customer satisfaction?
⏰  What hours need surge pricing?        📍  Which locations are underserved?
```

---

## 📊 Dataset

<table>
<thead>
<tr>
<th>Property</th>
<th>Detail</th>
</tr>
</thead>
<tbody>
<tr>
<td>📁 <strong>File Name</strong></td>
<td><code>Uber Trip Details.csv</code> &amp; <code>Location Table.csv</code></td>
</tr>
<tr>
<td>📏 <strong>Total Rows</strong></td>
<td>103,000+ trip records</td>
</tr>
<tr>
<td>📐 <strong>Total Columns</strong></td>
<td>14 fields across fact &amp; dimension tables</td>
</tr>
<tr>
<td>💾 <strong>Raw File Size</strong></td>
<td>~12 MB (CSV) · ~8 MB (compressed)</td>
</tr>
<tr>
<td>📅 <strong>Date Range</strong></td>
<td>January 2024 – December 2024 (Full Year)</td>
</tr>
<tr>
<td>🌍 <strong>Coverage</strong></td>
<td>Multiple cities across the United States</td>
</tr>
<tr>
<td>🔗 <strong>Source</strong></td>
<td><a href="https://www.kaggle.com/">Kaggle Open Dataset</a></td>
</tr>
<tr>
<td>📥 <strong>Download</strong></td>
<td><a href="https://www.kaggle.com/datasets"><strong>⬇️ Click to Download Dataset</strong></a></td>
</tr>
</tbody>
</table>

### 🗂️ Dataset Schema

```
Fact Table: Trips
├── Trip_ID           → Unique identifier
├── Pickup_Time       → Timestamp of pickup
├── Dropoff_Time      → Timestamp of dropoff
├── Pickup_Location   → FK → Location Table
├── Dropoff_Location  → FK → Location Table
├── Vehicle_Type      → UberX, UberXL, Black, etc.
├── Trip_Distance     → Miles traveled
├── Total_Amount      → Booking revenue
└── Payment_Type      → Card, Cash, Digital Wallet

Dimension Tables
├── 📅 Date           → Year, Month, Week, Day, Hour, Day Type
├── 📍 Location       → Location Name, Borough, Coordinates
└── 🚗 Vehicle        → Vehicle Category, Tier, Capacity
```

---

## 💡 Key Insights

<table>
<tr>
<td align="center">🕐</td>
<td><strong>Peak Hours: 4 PM – 8 PM</strong><br/>Afternoon–evening drives 40% of all daily bookings</td>
</tr>
<tr>
<td align="center">🚗</td>
<td><strong>UberX Dominates</strong><br/>~68% of all trips — clear preference for budget-tier vehicles</td>
</tr>
<tr>
<td align="center">💳</td>
<td><strong>Digital-First Payments</strong><br/>82% of revenue flows through card & digital wallets</td>
</tr>
<tr>
<td align="center">📅</td>
<td><strong>Weekend Surge</strong><br/>Saturday & Sunday show 35% higher trip volume than weekdays</td>
</tr>
<tr>
<td align="center">📍</td>
<td><strong>Top 5 Pickup Zones</strong><br/>Account for 28% of total bookings (Pareto-driven concentration)</td>
</tr>
<tr>
<td align="center">🌙</td>
<td><strong>Night Trips: Longer, Higher Value</strong><br/>Night trips average 23% more revenue per trip than daytime</td>
</tr>
</table>

---

## 📐 Data Model

```
                    ┌─────────────┐
                    │  📅 Date    │
                    │─────────────│
                    │ DateKey     │
                    │ Year        │
                    │ Month       │
                    │ Day Type    │
                    │ Hour        │
                    └──────┬──────┘
                           │
          ┌────────────────▼────────────────┐
          │           ⭐ Trips (Fact)        │
          │────────────────────────────────│
          │ Trip_ID  ← Primary Key          │
          │ DateKey  → FK: Date             │
          │ Pickup_LocationID → FK: Location │
          │ Vehicle_TypeID → FK: Vehicle     │
          │ Total_Amount                    │
          │ Trip_Distance                   │
          │ Payment_Type                    │
          └──────┬──────────────┬───────────┘
                 │              │
    ┌────────────▼──┐     ┌─────▼──────────┐
    │  📍 Location  │     │   🚗 Vehicle   │
    │───────────────│     │────────────────│
    │ LocationID    │     │ VehicleTypeID  │
    │ Location Name │     │ Vehicle Name   │
    │ Borough       │     │ Tier           │
    │ Coordinates   │     │ Capacity       │
    └───────────────┘     └────────────────┘
```

> Designed using a **Star Schema** — optimized for fast aggregation, clean relationships, and scalable DAX calculations.

---

## ⚙️ Key DAX Measures

```dax
-- ─────────────────────────────────────────────
-- CORE KPIs
-- ─────────────────────────────────────────────

Total Bookings =
    COUNT(Trips[Trip_ID])

Total Revenue =
    SUM(Trips[Total_Booking_Amount])

Average Booking Value =
    AVERAGE(Trips[Total_Booking_Amount])

Total Distance (mi) =
    SUM(Trips[Total_Trip_Distance])


-- ─────────────────────────────────────────────
-- TIME INTELLIGENCE
-- ─────────────────────────────────────────────

Revenue MoM % Change =
VAR CurrentMonth = [Total Revenue]
VAR PrevMonth = CALCULATE([Total Revenue], DATEADD('Date'[Date], -1, MONTH))
RETURN
    DIVIDE(CurrentMonth - PrevMonth, PrevMonth, 0)

Bookings YTD =
    TOTALYTD([Total Bookings], 'Date'[Date])


-- ─────────────────────────────────────────────
-- BEHAVIORAL SEGMENTATION
-- ─────────────────────────────────────────────

Day/Night Trip =
IF(
    HOUR(Trips[Pickup_Time]) >= 6 &&
    HOUR(Trips[Pickup_Time]) < 18,
    "Day",
    "Night"
)

Trip Duration (min) =
    DATEDIFF(Trips[Pickup_Time], Trips[Dropoff_Time], MINUTE)

Revenue per Mile =
    DIVIDE([Total Revenue], [Total Distance (mi)], 0)
```

---

## 📈 Dashboard Highlights

### 🔷 Page 1 — Executive Overview
> *C-suite snapshot: everything critical at a glance*

- **KPI Cards**: Total Bookings · Total Revenue · Avg Booking Value · Total Distance
- **Trend Line**: Monthly revenue trajectory with MoM comparison
- **Donut Charts**: Payment type split · Vehicle type distribution
- **Slicer Panel**: Date range · City · Vehicle type

---

### 🔷 Page 2 — Time Intelligence
> *Understand WHEN demand happens*

- **Hourly Heatmap**: 24-hour × 7-day demand matrix
- **Peak Hour Bar**: Hourly trip volume with conditional formatting
- **Day Type Comparison**: Weekday vs. weekend performance split
- **Day/Night KPI Toggle**: Switch between behavioral segments

---

### 🔷 Page 3 — Location & Vehicle Analysis
> *Understand WHERE and HOW trips happen*

- **Map Visual**: Pickup hotspots by geographic cluster
- **Top 10 Locations Table**: Ranked by booking volume & revenue
- **Vehicle Type Matrix**: Revenue, distance, and bookings per vehicle class
- **Drill-Through**: Click any location → trip-level breakdown

---

## 🧠 Skills Demonstrated

```
Data Engineering          Business Intelligence       Design & Communication
──────────────────        ────────────────────────    ─────────────────────────
✔ Power Query (M)         ✔ KPI Framework Design      ✔ Dashboard UX Design
✔ Data Cleaning           ✔ Executive Reporting        ✔ Color-coded Insights
✔ Star Schema Modeling    ✔ Time Intelligence DAX      ✔ Storytelling with Data
✔ Relationship Mgmt       ✔ Aggregations & Ratios      ✔ Slicer-driven Interactivity
✔ Calculated Columns      ✔ Conditional Logic          ✔ Cross-page Drill-Through
```

---

## 🚀 How to Run

```bash
# Step 1 — Clone the repository
git clone https://github.com/yourusername/jaboo-trip-analysis.git
cd jaboo-trip-analysis
```

```
# Step 2 — Download the dataset
Place the following files in the /data folder:
  ├── Uber Trip Details.csv
  └── Location Table.csv

Dataset link: https://www.kaggle.com/datasets/[your-dataset-link]
```

```
# Step 3 — Open in Power BI Desktop
File → Open → JabooTripDashboard.pbix
```

```
# Step 4 — Refresh data source
Home → Transform Data → Close & Apply → Refresh
```

```
# Step 5 — Explore
Use the slicers (Date Range, City) in the top panel to filter and explore all 3 pages.
```

> **Requirements**: Power BI Desktop (June 2024 or later) · Windows 10/11

---

## 📈 Business Impact

| Use Case | How This Dashboard Helps |
|:---------|:------------------------|
| 📊 **Demand Forecasting** | Heatmaps reveal predictable daily/weekly patterns for proactive fleet staging |
| 🚕 **Fleet Distribution** | Location analysis identifies underserved zones with high latent demand |
| 💰 **Revenue Optimization** | Revenue-per-mile metrics expose low-performing vehicle routes |
| 📍 **Expansion Strategy** | Cluster analysis highlights cities and zones ripe for growth |
| 😊 **Driver Experience** | Peak hour data helps drivers maximize earnings during surge windows |

---

## 🧪 Future Improvements

- [ ] 🔄 **Real-time Integration** — Connect to live Uber API or Azure Event Hub stream
- [ ] 🤖 **Predictive Forecasting** — Embed Python/R visuals with ARIMA or Prophet models
- [ ] 👥 **Customer Segmentation** — RFM clustering for loyalty & churn analysis
- [ ] ☁️ **Power BI Service Deployment** — Publish to workspace with scheduled refresh
- [ ] 📱 **Mobile Layout** — Optimize for Power BI Mobile app
- [ ] 🔔 **Data Alerts** — Threshold alerts for revenue drops or demand spikes

---

## 👨‍💻 Author

<table>
<tr>
<td align="center" width="120">
<img src="https://avatars.githubusercontent.com/u/000000?v=4" width="80" style="border-radius:50%;" alt="Rahman Riyad"/><br/>
<sub><b>Rahman Riyad</b></sub>
</td>
<td>

**Aspiring Data Analyst · Power BI Enthusiast**

I build dashboards that turn messy data into clear decisions. Passionate about business intelligence, DAX, and data storytelling.

[![GitHub](https://img.shields.io/badge/GitHub-000?style=flat&logo=github)](https://github.com/yourusername)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/yourprofile)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=flat&logo=google-chrome&logoColor=white)](https://yourportfolio.com)

</td>
</tr>
</table>

---

## ⭐ Why This Project Stands Out

```
✔  Real-world business use case — ride-sharing analytics at scale
✔  103,000+ rows of cleaned, modeled trip data
✔  Advanced DAX — time intelligence, ratios, conditional logic
✔  Star schema — production-grade relational model
✔  Insight-driven storytelling across 3 focused dashboard pages
✔  Clean, professional UI with executive-ready design
```

---

<div align="center">

**If this project helped you, please consider giving it a ⭐ — it means a lot!**

<br/>

*Built with ❤️ using Power BI · © 2025 Rahman Riyad*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100=0f3460&height=100&section=footer" width="100%"/>

</div>
