# 🚖 GCP Uber ETL Data Engineering Project

## 📌 Project Overview

This project demonstrates an end-to-end Data Engineering pipeline built on **Google Cloud Platform (GCP)** using:

- Mage (ETL Orchestration)
- Compute Engine VM
- Google Cloud Storage
- BigQuery
- Looker
- Star Schema Data Modeling

The pipeline ingests raw Uber trip data, transforms it into a dimensional data model (Star Schema), loads it into BigQuery, and enables analytics using Looker.

---

## 🏗️ Architecture

![Architecture](architecture.jpg)

### Flow:

1. Raw Uber CSV stored in Google Cloud Storage
2. Mage running on Compute Engine performs ETL
3. Data transformed into Star Schema
4. Loaded into BigQuery
5. Analytics performed using Looker

---

## 📊 Data Model (Star Schema)

![Data Model](data_model.jpeg)

### Fact Table:
- trip transactions
- fare, tip, tax, total_amount
- foreign keys to dimension tables

### Dimension Tables:
- datetime_dim
- passenger_count_dim
- trip_distance_dim
- rate_code_dim
- pickup_location_dim
- dropoff_location_dim
- payment_type_dim

---

## ⚙️ ETL Pipeline Components

### 1️⃣ Data Loader Block
Fetches Uber dataset from Cloud Storage.

```python
requests.get(url)
pd.read_csv(...)
