# 🚦 Real-Time Urban Mobility & Traffic Analytics Platform

A city-scale analytics platform built to monitor **traffic congestion**, **accident risk hotspots**, and **weather-driven mobility patterns** using large-scale datasets and modern data engineering workflows.

This project integrates **traffic volume records**, **hourly weather conditions**, and downstream analytical modeling in **BigQuery**, enabling real-time congestion monitoring and accident probability insights.

---

## 📌 Project Highlights

- Ingested and integrated **12M+ traffic volume records**, **6M+ accident records**, and **hourly weather data** into **Google BigQuery**
- Processed **~250K records/day** using **Apache Spark (PySpark)** for time-series aggregation and anomaly detection
- Built **25+ advanced SQL analytical models** using:
  - CTEs  
  - Window functions  
  - Rolling averages  
  - Hotspot ranking  
- Optimized BigQuery performance with:
  - **Date partitioning**
  - **Location clustering**
  - Reduced query costs by **32%**
- Developed **6 interactive Power BI dashboards** tracking:
  - Congestion hotspots  
  - Peak-hour accident risk  
  - Seasonal variation  
  - Weather-linked accident probability  
- Identified rainfall-linked risk patterns contributing to a **14% higher accident probability during rainy hours**

---

## 🏗️ System Architecture

```text
          +--------------------+
          | Traffic Volume CSV |
          +--------------------+
                    |
                    v
          +--------------------+
          | Spark / PySpark ETL|
          | Hourly Aggregation |
          +--------------------+
                    |
                    v
   +-------------------------------------------+
   | Open-Meteo Archive Weather API Integration |
   | Hourly Temp, Rainfall, Wind, Pressure     |
   +-------------------------------------------+
                    |
                    v
         +----------------------------+
         | BigQuery Data Warehouse    |
         | Partitioned + Clustered    |
         +----------------------------+
                    |
                    v
       +------------------------------+
       | SQL Analytics + Power BI     |
       | Dashboards + Risk Insights   |
       +------------------------------+
