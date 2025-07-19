# 🚲 NYC CitiBike Usage Analysis (BigQuery + Tableau Dashboard)

This project analyzes and visualizes **NYC CitiBike usage trends** using 
**Google BigQuery for data extraction and transformation**, and **Tableau** 
for interactive dashboards. The analysis combines trip data, geographic 
details, and weather data to uncover urban mobility patterns.

🔗 **[View Tableau Dashboard](https://public.tableau.com/app/profile/usman.khalid4491/viz/NYCCitiBikesUsage/TrendsDeepDive)**

---

## 🧰 Tools & Technologies Used

- **Google BigQuery** – SQL-based data extraction, aggregation and transformation
  - Query available in the other file named:
- **Public Datasets**:
  - `bigquery-public-data.new_york_citibike.citibike_trips`
  - `bigquery-public-data.noaa_gsod.gsod20*`
- **Custom ZIP Code Table** – Joined from `cyclistic-stations-bi.us_geo.zip_codes`
- **Tableau** – Dashboard creation, interactive filtering, mapping
- **Mapbox** – Used within Tableau for geo-boundary mapping

---

## 🧠 Project Overview

The project explores:
- Monthly and seasonal ride trends  
- Usage trend differences **Subscribers** and **Customers**  
- High-volume ZIP codes and neighborhoods  
- Route patterns across boroughs  
- Weather’s impact on ride volume  

---

## 🔍 Process Thinking

### 1. **Data Aggregation via SQL in BigQuery**

A complex SQL query was written to:
- Join **citibike trips** with **ZIP code geographies** using `ST_WITHIN`
- Enrich trips with **weather data** from Central Park (`wban = 94728`)
- Map coordinates to **boroughs and neighborhoods**
- Round trip durations to 10-minute bins for aggregation

```

> Resulting dataset from the query was exported from BigQuery and imported into Tableau.

---

### 2. **Data Modeling & Calculations**
- Created **trip_count**, **trip_minutes**, and **aggregated KPIs**  
- Weather fields used: `temp`, `wdsp`, `prcp`  
- All aggregations done in SQL to reduce Tableau load

---

### 3. **Dashboard Design in Tableau**
- Used filters for `Usertype`, `Neighborhood`, and `Time`  
- Enabled map-driven interactivity  
- Used clean, color-coded layouts with consistent labeling

---

## 📊 Key Dashboards

### 📈 Summer Trend Analysis
- Monthly stacked bars comparing user types

### 🔥 Trip Count Heatmap
- Heatmap of ZIPs by month, colored by trip volume

### 🧭 Start-End Dive Table
- Matrix of start/end neighborhoods with average trip time

### 🗺️ Borough Mapping
- Map of boroughs and their activity volume

---

## 🧑‍💻 Author

Built by [Usman Khalid](https://public.tableau.com/app/profile/usman.khalid4491/vizzes)  
This project is part of the **Google BI Specialization** – Data Visualization Capstone

## 🔖 Tags

`#BigQuery` `#SQL` `#Tableau` `#CitiBike` `#NYC` `#UrbanMobility`  
`#GeospatialAnalysis` `#PublicDatasets` `#GoogleBISpecialization` `#DataVisualization`
