# 📦 ADF_COPY_ACTIVITY

## 📘 Azure Data Factory - Copy Activity with Medallion Architecture

### 🧾 Overview

This project demonstrates how to use **Azure Data Factory (ADF)** to ingest data from GitHub repositories into **Azure Data Lake Storage (ADLS)**, following the **Medallion Architecture** (Bronze → Silver → Gold). The data is incrementally loaded and refined across layers for analytical and reporting purposes.

---

## 🏗️ Project Architecture

### 🔄 Data Flow

1. **Source**  
   - Public data from GitHub repositories (e.g., JSON files).

2. **Destination**  
   - Data is initially ingested into the **Bronze Layer** (landing zone) in ADLS.

3. **ADF Pipeline Components**
   - **Linked Services**: Connects ADF to GitHub and ADLS.
   - **ForEach Activity**: Dynamically loops through multiple datasets.
   - **Copy Activity**: Moves data from GitHub to ADLS (Bronze layer).

---

## 🔧 Components

### 1. 🔗 Linked Services
- **GitHub Linked Service**  
  - Authenticated connection to fetch data from public GitHub repositories.
  
- **ADLS Linked Service**  
  - Secure connection to Azure Data Lake Storage for landing the data.

### 2. 📁 Datasets
- **Source Dataset**  
  - Points to GitHub JSON files.
  
- **Sink Dataset**  
  - Configured to write data to appropriate locations in ADLS.

### 3. 🛠️ Pipeline Configuration
- **ForEach Activity**  
  - Iterates over a list of repositories or datasets for dynamic data loading.
  
- **Copy Activity**  
  - Executes the actual data movement from GitHub to ADLS within the loop.
  
- **Incremental Loading**  
  - Configured where applicable to avoid reprocessing and improve performance.

### 4. 🏛️ Medallion Architecture Implementation
- **Bronze Layer (Raw Data)**  
  - Ingested data directly from GitHub; minimally processed.

- **Silver Layer (Refined Data)**  
  - Cleaned and structured data for analytical readiness.

- **Gold Layer (Curated Data)**  
  - Business-ready data used for reporting and dashboarding (e.g., Power BI).

---

## 🌟 Key Features

✅ Dynamic ingestion of multiple datasets via `ForEach` activity  
✅ Secure and reusable connections using Linked Services  
✅ Incremental load for optimized performance  
✅ Follows **Medallion Architecture** best practices for scalable and clean data transformation

---

## ✅ Prerequisites

- 🔧 Azure Data Factory instance  
- 🗄️ Azure Data Lake Storage (ADLS) account  
- 🌐 Access to desired GitHub repositories  
- 🔐 Azure Key Vault (for securely managing credentials and secrets)

---

## 📬 Contact

For questions or collaboration, feel free to reach out at:  
📧 *[Your Contact Email]*
