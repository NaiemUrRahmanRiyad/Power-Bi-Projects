# 🚖 Jaboo Trip Analysis Dashboard 

---

## 📌 Overview

This project presents a **fully interactive  Trip Analysis Dashboard** built using **Power BI**, focused on transforming raw trip data into **actionable business insights**.

The goal of this project is to simulate a **real-world business intelligence scenario**, where stakeholders can:
- Monitor performance  
- Identify trends  
- Optimize operations  

---

## 🎯 Business Problem

Ride-sharing companies like Uber need to:

- 📊 Understand demand patterns  
- 🚕 Optimize vehicle allocation  
- 💰 Track revenue performance  
- 😊 Improve customer experience  

This dashboard answers a key question:

> **When, where, and how are trips happening — and how can the business improve?**

---

## 💡 Key Insights Delivered

- 📈 Peak demand occurs during afternoon–evening hours  
- 🚗 UberX dominates bookings across all locations  
- 💳 Majority of transactions happen via digital payments  
- 📅 Weekend demand is significantly higher  
- 📍 Certain pickup locations consistently generate high trip volumes  
- 🌙 Clear behavioral difference between **day vs night trips**  

---

## 🧠 Skills Demonstrated

- 🧹 Data Cleaning & Transformation (Power Query)  
- 🧮 Advanced DAX  
- 📊 KPI Development  
- ⏳ Time Intelligence  
- 🔢 Aggregations & Conditional Logic  
- 🧩 Data Modeling (Star Schema)  
- 🎨 Interactive Dashboard Design  
- 📖 Storytelling with Data  

---

## 📊 Dashboard Highlights

### 🔹 Executive Overview
- High-level KPIs for quick decision-making  
- Metrics include revenue, bookings, distance, and averages  

### 🔹 Time-Based Analysis
- Trip trends by hour and day  
- Heatmap visualization for demand patterns  

### 🔹 Detailed Insights
- 🚗 Vehicle performance analysis  
- 📍 Location-based insights  
- 💳 Payment and trip type breakdown  

---

## 📐 Data Model (Simplified)

- **Fact Table:** Trips  
- **Dimension Tables:**  
  - 📅 Date  
  - 📍 Location  
  - 🚗 Vehicle Type  

> Designed using a **star schema** for optimal performance and scalability.

---

## ⚙️ Key DAX Measures

```DAX
Total Bookings = COUNT(Trips[Trip ID])

Total Revenue = SUM(Trips[Total Booking Amount])

Average Booking Value = AVERAGE(Trips[Total Booking Amount])

Total Distance = SUM(Trips[Total Trip Distance])

Day/Night Trip =
IF(
    HOUR(Trips[Pickup Time]) >= 6 &&
    HOUR(Trips[Pickup Time]) < 18,
    "Day",
    "Night"
)
```

---

## 🚀 How to Run

1. Clone this repository  
2. Open the `.pbix` file in **Power BI Desktop**  
3. Refresh data (if needed)  
4. Use slicers (Date, City) to explore insights  

---

## 📈 Business Impact

This dashboard can help:

- 📊 Improve demand forecasting  
- 🚕 Optimize fleet distribution  
- 💰 Increase revenue efficiency  
- 📍 Identify high-performing locations  

---

## 🧪 Future Improvements

- 🔄 Add real-time data integration  
- 🤖 Implement forecasting models  
- 👥 Build user segmentation  
- ☁️ Deploy via Power BI Service  

---

## 👨‍💻 Author

**Rahman Riyad**  
Aspiring Data Analyst | Power BI Enthusiast  

---

## ⭐ Why This Project Stands Out

✔ Real-world business use case  
✔ Strong DAX & data modeling  
✔ Clean and professional UI  
✔ Insight-driven storytelling  
