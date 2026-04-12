# 🏥 Hospital Monitoring Dashboard — Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Dataset](https://img.shields.io/badge/Dataset-55%2C500%20Records-7B2D8B?style=for-the-badge&logo=databricks&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)
![Billing](https://img.shields.io/badge/Total%20Billing-%241.417B-F2C811?style=for-the-badge&logo=stripe&logoColor=black)
![Hospitals](https://img.shields.io/badge/Hospitals-10%20Major-e53935?style=for-the-badge&logo=redcross&logoColor=white)

> A comprehensive, multi-page Power BI dashboard for monitoring hospital operations, patient demographics, admission trends, and treatment costs — designed for healthcare administrators and analysts.

---

## 📸 Dashboard Preview

### Page 1 — Treatment Cost
![Treatment Cost Page](screenshots/h1.png)

### Page 2 — Key Trend
![Key Trend Page](screenshots/h2.png)

### Page 3 — Patient Demographic
![Patient Demographic Page](screenshots/h3.png)

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Dashboard Pages](#-dashboard-pages)
- [Key Features](#-key-features)
- [Data Model & Metrics](#-data-model--metrics)
- [Visuals Used](#-visuals-used)
- [Filters & Slicers](#-filters--slicers)
- [How to Use](#-how-to-use)
- [Requirements](#-requirements)
- [File Structure](#-file-structure)
- [Author](#-author)

---

## 🔍 Overview

This **Hospital Monitoring Dashboard** is a Power BI project built to provide a 360° view of hospital performance. It spans three analytical pages — **Patient Demographic**, **Key Trend**, and **Treatment Cost** — each offering a different lens into the hospital's data.

The dashboard enables:
- Real-time KPI monitoring (Admitted Patients, Rooms, Doctors, Billing, LOS, Age)
- Trend analysis by month, day type, and admission type
- Revenue and billing breakdowns across hospitals and LOS groups
- Patient condition profiling and test result summaries

Total records analyzed: **55,500 patients** across **10 major hospitals**, generating **$1.417 Billion** in total billing.

---

## 📊 Dashboard Pages

### 1. 🧾 Treatment Cost
This page focuses on **revenue analysis and billing patterns** across hospitals, admission types, and Length of Stay (LOS) groups.

**Key Visuals:**
- **Stacked Bar Chart** — Total Billing by LOS Groups and Admission Type (Elective, Emergency, Urgent)
- **Treemap** — Contribution of Hospitals in Revenue (color-coded by hospital)
- **Decomposition Tree** — Drills down from Total Billing → Hospital → Admission Type → Age Group → Gender
- **KPI Cards** — Admitted Patients, Rooms, Doctors, Total Bill, Avg LOS, Avg Age

**Insights Available:**
- Extended Stay (15d+) generates the highest billing at ~$751M
- Houston Methodist Hospital is the top revenue contributor
- Elective admission type leads billing at $177.57M

---

### 2. 📈 Key Trend
This page captures **temporal and distributional trends** in patient admissions over the year.

**Key Visuals:**
- **Donut Chart** — Admitted Patients by Day Type (Weekday 71.49% vs. Weekend 28.51%)
- **Donut Chart** — Admitted Patients by LOS Groups (Short Stay 53.16% is dominant)
- **Line Chart** — Monthly Admissions by Admission Type (Elective, Emergency, Urgent) from Jan–Dec
- **Matrix Table** — Patient Admission Breakdown by Month and Day of Week (with totals)
- **KPI Cards** — Same 6 KPIs for cross-page consistency

**Insights Available:**
- Total admissions: **55,500** across all months
- July is the peak admission month (4,812 patients)
- Wednesday is the least busy day of the week
- Admissions are fairly consistent month-to-month with slight seasonal dips in Feb

---

### 3. 👥 Patient Demographic
This page provides a **profile of patients** — their conditions, test results, age/gender distribution, and hospital-level breakdown.

**Key Visuals:**
- **Condition Description Card** — Dynamic text display per selected condition with an illustration
- **KPI Tiles** — Normal Test Results (1K, 9.57%), Abnormal Test Results (6K, 54.65%), Inclusive Test Results (4K, 35.78%)
- **Clustered Bar Chart** — Admitted Patients by LOS Group and Gender (Female vs. Male)
- **Bar Chart** — Top conditions by patient volume (Arthritis, Asthma, Cancer, Diabetes, Hypertension, Obesity)
- **Matrix Table** — Hospital × Condition breakdown with row/column totals

**Insights Available:**
- Hypertension is the most common condition (2,788 patients)
- Johns Hopkins leads in total patients (2,229)
- Abnormal test results are the largest category at 54.65%
- Female patients slightly outnumber male across most LOS groups

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🔀 Multi-Page Navigation | Intuitive tab-style navigation between 3 dashboard pages |
| 🎛️ Dynamic Slicers | Filter by Year, Month, Condition — all visuals update in sync |
| 💡 KPI Cards | Six consistent KPI tiles across all pages for quick summary |
| 🌲 Decomposition Tree | Interactive drill-down from Total Billing to Gender-level granularity |
| 🗺️ Treemap | Visual revenue contribution by hospital at a glance |
| 📅 Calendar Heatmap | Admission breakdown by month × day of week |
| 🩺 Condition Profiler | Condition description + image + test result tiles per selected condition |
| 🎨 Consistent Theming | Purple/lavender color palette with clean white cards for readability |

---

## 📐 Data Model & Metrics

### Core KPIs (DAX Measures)

```dax
Admitted Patients = COUNTROWS('Patients')

Total Bill = SUM('Billing'[Amount])

Avg LOS = AVERAGE('Patients'[LengthOfStay])

Avg Age of Patients = AVERAGE('Patients'[Age])

Rooms = DISTINCTCOUNT('Rooms'[RoomID])

Doctors = DISTINCTCOUNT('Staff'[DoctorID])
```

### Supporting Measures

```dax
Normal Test % = DIVIDE([Normal Test Count], [Total Tests], 0)

Abnormal Test % = DIVIDE([Abnormal Test Count], [Total Tests], 0)

YoY Change % = DIVIDE([Current Year Value] - [Prior Year Value], [Prior Year Value], 0)
```

### Data Tables (Assumed Schema)

| Table | Key Columns |
|---|---|
| Patients | PatientID, Age, Gender, AgeGroup, AdmissionDate, DischargeDate, LOS, Condition, HospitalID |
| Billing | PatientID, Amount, AdmissionType |
| Hospitals | HospitalID, HospitalName |
| Staff | DoctorID, HospitalID |
| Rooms | RoomID, HospitalID |
| Calendar | Date, Month, DayOfWeek, DayType (Weekday/Weekend) |

---

## 📊 Visuals Used

| Visual Type | Page Used On |
|---|---|
| KPI Cards | All Pages |
| Stacked Bar Chart | Treatment Cost |
| Treemap | Treatment Cost |
| Decomposition Tree | Treatment Cost |
| Donut Charts | Key Trend |
| Line Chart (Multi-series) | Key Trend |
| Matrix / Table | Key Trend, Patient Demographic |
| Clustered Bar Chart | Patient Demographic |
| Bar Chart | Patient Demographic |
| Text / Image Cards | Patient Demographic |
| Slicers (Dropdown) | All Pages |

---

## 🎛️ Filters & Slicers

| Slicer | Available On | Options |
|---|---|---|
| Select Year | All Pages | All, 2021, 2022... |
| Select Month | Key Trend, Patient Demographic | All, Jan–Dec |
| Select Condition | All Pages | All, Arthritis, Asthma, Cancer, Diabetes, Hypertension, Obesity |

All slicers are cross-filtered — selecting a value updates every visual on the page simultaneously.

---

## 🚀 How to Use

### Prerequisites

- **Power BI Desktop** (free) — [Download here](https://powerbi.microsoft.com/desktop/)
- The `.pbix` project file from this repository

### Steps

1. **Clone or download** this repository:
   ```bash
   git clone https://github.com/your-username/hospital-monitoring-dashboard.git
   ```

2. **Open** the `.pbix` file in Power BI Desktop.

3. **Connect your data source** (if applicable):
   - Go to **Home → Transform Data → Data Source Settings**
   - Update the file path or database connection to point to your data

4. **Refresh the data**:
   - Click **Home → Refresh** to load the latest data

5. **Interact with the dashboard**:
   - Use the top navigation tabs to switch between pages
   - Use the dropdown slicers to filter by Year, Month, and Condition
   - Click on any chart element to cross-filter other visuals

6. **Publish to Power BI Service** (optional):
   - Click **Home → Publish** and sign in to your Power BI account
   - Share the dashboard URL with your team

---

## 💻 Requirements

| Requirement | Details |
|---|---|
| Power BI Desktop | Version 2.x or later (October 2023+ recommended) |
| Operating System | Windows 10 / 11 (Power BI Desktop is Windows-only) |
| RAM | 4 GB minimum, 8 GB recommended |
| Data Format | Excel / CSV / SQL Server / any Power BI-supported source |
| Internet | Required only for publishing to Power BI Service |

---

## 📁 File Structure

```
hospital-monitoring-dashboard/
│
├── 📊 HospitalMonitoringDashboard.pbix   # Main Power BI project file
│
├── 📁 data/
│   ├── patients.csv                      # Raw patient records (55,500 rows)
│   ├── billing.csv                       # Billing data
│   └── hospitals.csv                     # Hospital reference table
│
├── 📁 screenshots/
│   ├── h1.png                            # Treatment Cost page
│   ├── h2.png                            # Key Trend page
│   └── h3.png                            # Patient Demographic page
│
└── 📄 README.md                          # This file
```

---

## 🎨 Design Choices

- **Color Palette**: Purple (`#7B2D8B`, `#A855F7`) and lavender (`#E9D5FF`) for a clean medical aesthetic
- **Typography**: Segoe UI — Power BI default, highly readable
- **Card Style**: White rounded cards with subtle shadows for clear data separation
- **Navigation**: Arrow-shaped tabs at the top for intuitive multi-page flow
- **Consistency**: The same 6 KPI cards appear on every page so users always have the baseline context

---

## 📬 Author

**Your Name**
- GitHub: [@your-username](https://github.com/your-username)
- LinkedIn: [linkedin.com/in/your-profile](https://linkedin.com/in/your-profile)
- Email: your.email@example.com

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, adapt, and share with attribution.

---

> ⭐ If you found this project useful, please consider giving it a star on GitHub!
