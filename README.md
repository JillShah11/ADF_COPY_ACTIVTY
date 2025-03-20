# ADF_COPY_ACTIVTY

README: Azure Data Factory (ADF) - Copy Activity with Medallion Architecture

Overview

**This project leverages Azure Data Factory (ADF) to implement a Copy Activity that ingests data from GitHub repositories into Azure Data Lake Storage (ADLS). The solution follows the Medallion Architecture (Bronze, Silver, Gold layers) for data refinement and transformation.**

Project Architecture

Data Flow Overview

Source: Data extracted from various GitHub repositories.

Destination: Data is ingested into Azure Data Lake Storage (ADLS) in the Bronze (Landing Layer).

ADF Pipeline: ADF orchestrates the data movement using:

Linked Services to connect ADF to GitHub and ADLS.

ForEach Activity to loop through multiple datasets dynamically.

Copy Activity to load data from GitHub to the Bronze layer in ADLS.

Components

1. Linked Services

GitHub Linked Service: Configured with appropriate authentication to pull data from public repositories.

ADLS Linked Service: Utilized to connect to Azure Data Lake for data storage.

2. Datasets

Source datasets reference GitHub JSON files.

Sink datasets are configured to write data to ADLS.

3. Pipeline Configuration

For Each activity iterates through a list of datasets to dynamically copy multiple files from GitHub.

Copy Activity within the ForEach loop moves data from GitHub to the Bronze layer in ADLS.

The pipeline is configured for incremental loading where possible.

4. Medallion Architecture Implementation

Bronze Layer (Landing Zone): Raw data copied directly from GitHub.

Silver Layer: Cleaned and structured data for refined analysis.

Gold Layer: Curated data prepared for business consumption and Power BI reporting.
**
Key Features**

✅ Dynamic dataset ingestion using ForEach activity.✅ Secure authentication using Linked Services.✅ Incremental data load to optimize performance.✅ Follows best practices in Medallion Architecture for data quality refinement.

**Prerequisites**

Azure Data Factory Instance.

Azure Data Lake Storage (ADLS) configured for data storage.

Access to the desired GitHub repositories.

Azure Key Vault for securely managing credentials.
