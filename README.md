# Flight Data Analysis Using DuckDB and Power BI

## Project Overview
This project focuses on building a **scalable and efficient data pipeline** to analyze a large flight dataset, leveraging **DuckDB** for data storage and processing, and **Power BI** for visualizations. The project adopts a modern data warehouse approach, organizing data into **Bronze**, **Silver**, and **Gold layers** to ensure smooth data flow, proper data cleaning, and structured insights extraction. 

The dataset, sourced from **Kaggle**, contains over **300,000 rows** of raw flight data, including details such as flight schedules, airline delays, routes, and more. The project involved substantial data cleaning, data transformation, and SQL querying through DuckDB to prepare a well-structured dataset for visualization and analysis in Power BI.

## Dataset
The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/mahoora00135/flights/code), providing information on flight schedules, delays, airlines, and routes. It was processed through multiple layers to ensure data quality and accuracy, culminating in key findings and insights.

### Python Notebook Overview
The **Python notebook (`Final Project.ipynb`)** manages the entire data processing pipeline, taking the dataset through multiple stages to clean, structure, and prepare it for analysis. Using **DuckDB** for in-memory data processing, the notebook processes the raw flight dataset in three primary layers:

1. **Bronze Layer (Raw Data Ingestion)**:
   - Raw dataset ingestion into **DuckDB**.
   - Captures the raw data, including time delays, airline names, flight numbers, and airport codes.

2. **Silver Layer (Data Cleaning & Transformation)**:
   - Applies data cleaning techniques:
     - Handling **9430 null values**.
     - Removing duplicates.
     - Filtering unnecessary information to ensure data quality.
   - Stores cleaned data in the `final_bronze` table.

3. **Gold Layer (Fact & Dimension Tables)**:
   - Creates **fact** and **dimension tables** for organized data:
     - **Fact tables** contain transactional data such as flight schedules and delays.
     - **Dimension tables** hold descriptive data on airlines, airports, and aircraft.
   - These structured tables are used for efficient analysis and visualization.

## Data Pipeline

### The data pipeline for this project processes the raw dataset through several layers, ensuring scalability and efficient data handling:

1. **Data Ingestion**:
   - Raw flight data from **Kaggle** is loaded into **DuckDB** as the data lake.

2. **Data Cleaning and Transformation**:
   - Using **pandas** and **DuckDB**, the raw dataset is cleaned by handling null values, removing duplicates, and filtering key columns.

3. **Data Structuring (Fact & Dimension Tables)**:
   - The cleaned data is organized into **fact and dimension tables**, which are stored in **DuckDB** for optimized querying.

4. **Data Analysis & Visualization**:
   - The structured data is loaded into **Power BI** to generate visual reports and dashboards, providing insights into airline performance and delays.

### The project follows a **three-layer architecture** to process and analyze the dataset:

1. **Bronze Layer**:
   - Raw data ingestion into **DuckDB** for creating a data lake.
   - This includes raw flight data like time details, delays, flight numbers, and routes.

2. **Silver Layer**:
   - Applied data cleaning using **Python** and **DuckDB**. This included handling **9430 null values**, removing duplicates, and creating a clean dataset stored as `final_bronze`.
   - Data transformations were applied to prepare the dataset for further analysis.

3. **Gold Layer**:
   - Structured the data into **fact** and **dimension tables** for cleaner access and analysis, covering airports, flight schedules, airlines, and aircraft.
   - Populated these tables using `INSERT` statements to extract the clean data from the `final_bronze` table.

## Tools & Technologies
- **DuckDB**: Used to create a scalable data lake and execute SQL queries.
- **Python (Jupyter Notebook)**: Used for data cleaning, handling null values, and data transformation.
- **Power BI**: Used to create detailed visualizations and reports from the data.
- **Kaggle Dataset**: Flight dataset providing detailed flight schedules, delays, and route information.

## Key Findings
- **Top Airlines by Distance**: United Airlines operates the longest distances, dominating international routes.
- **Market Dominance**: A few airlines control the majority of long-haul flights, providing growth opportunities for smaller carriers.
- **Environmental Impact**: Airlines with longer routes may have a larger environmental footprint, presenting opportunities for fuel efficiency improvements.

## Data Cleaning & Processing (Python Notebook)
The **Python Jupyter Notebook** (`Final Project.ipynb`) was used to:
- **Handle null values**: Removed **9430 null values** and created a clean dataset.
- **Remove duplicates**: Ensured no redundant records were left in the final dataset.
- **Create fact and dimension tables**: Structured the data into easily accessible formats for analysis.

## Data Visualization (Power BI)
The **Power BI** file (`Flights.pbix`) includes the following visualizations:
- **Top Airlines by Distance**
- **Flight Origins by NYC Airports**
- **Flight Counts by Airline**
- **Departure Delays by Airline**

These visuals provide actionable insights into airline performance, delays, and flight traffic distribution.

## Installation and Setup

1. Install **DuckDB**: 
   ```bash
   pip install duckdb
