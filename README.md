# Big Data Management: Data-Driven Architecture Project using Spark
This repository contains the implementation of two critical backbones of a data-driven architecture: the Data Management Backbone and the Data Analysis Backbone. The project involves setting up a structured data lake with defined zones and performing either descriptive or predictive analysis. 

## Project Overview 
This project focuses on creating a data-driven architecture using Apache Spark. It involves setting up a data lake with structured zones on the local file system, processing raw data, and performing analysis.

## Environment SetUp 
The following guide will aid in setting up PySpark on Mac (for help with Windows setup, please head to: https://www.machinelearningplus.com/pyspark/install-pyspark-on-windows/). 

**PySpark Mac** 
1. Open terminal
2. Execute following command (make sure to have Homebrew installed)
   ```brew install openjdk``` 
3. For successful installation check run the following comands:
   ```
   java -version
   whereis java
   ```
4. Setting up Java_Home environment in shell profile (e.g., ~/bashrc or ~/.zshrc) by running:
   ```
   export JAVA_HOME=/usr/libexec/java_home
   ```
   ```
   source ~/.bashrc
   ```
5. Installing Apache Spark
   ```
   brew install apache-spark
   ```
for path info 
  ```
  brew info apache-spark
  ```
6. Setting Environment Variables (replace ***version*** with the installed Spark version) 
   ```
   export SPARK_HOME=/usr/local/Cella/apache-spark/<version>/libexec
   export PYSPARK_PYTHON=python3
   export PYSPARK_DRIVER_PYTHON=python3
   ```
7. ```
   source ~/.bashrc
   ```
8. Install PySpark Python Package
   ```
   pip install pyspark
   pyspark --version
   ```
 

## Data Management Backbone 
**Landing Zone**
- Stores raw data ingested into the data lake in a structured or semi-structured format. This includes data directly extracted from source systems with minimal transformation.
- *Implementation:* This would be implemented in a Distributed File System in a real-world scenarion but for the project goal it will be done in my local file system.

**Formatted Zone**
Stores data in a standardized format according to a canonical data model. Data is potentially enriched and in a consumption-ready form.
-*Implementation:* Implemented using Parquet files for efficient storage and schema enforcement on the local file system. 

**Exploitation Zone**
Contains processed and refined data optimized for analysis, such as features and KPIs.
-*Implementation:** Implemented using Parquet and CSV files for efficient storage on the local file system. 

## Data Analysis Backbone 
**Descriptive Analysis and Dashboarding** 
-*Descriptive Analysis:* Performed exploratory data analysis (EDA) on the data in the Exploitation Zone to summarize and understand the data. 
-*Dashboarding:* Created interactive dashboards using tools like Tableau, Power BI, or Jupyter Notebooks with matplotlib/seaborn. 

## How to navigate the repository
```bash 
├── Documents
│   ├── BigData_Spark_notebook.ipynb
│   ├── BigData_Spark_report.pdf
├── LandingZone
│   ├── cultural-sites
│   ├── income
│   └── price_opendata
├── FormattedZone
│   ├── CulturalSites
│   ├── Income
│   └── PriceOpenData
├── ExploitationZone
│   ├── CulturalSites
│   ├── Income
│   ├── Price_Income
│   └── PriceOpenData
└── README.md
```
