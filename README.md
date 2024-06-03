# Spark Home Sales Analysis

## Overview
The purpose of this analysis is to utilize Apache Spark for processing and analyzing home sales data. The analysis involves tasks such as loading data from an AWS S3 bucket, performing SQL queries to extract insights, partitioning data, caching data, and comparing runtimes. This assignment demonstrates how to handle big data efficiently using Spark's capabilities.

## Analysis
### Purpose of the Analysis
The goal of this analysis is to explore and analyze home sales data using Apache Spark. By performing various SQL queries and optimizations, we aim to extract valuable insights and improve query performance.

### Data Description
The dataset contains information on home sales, including details such as sale price, number of bedrooms and bathrooms, square footage, and the date the home was built. Key variables include:

* ***Date:*** The date when the home was sold.
* ***Price:*** The sale price of the home.
* ***Bedrooms:*** The number of bedrooms in the home.
* ***Bathrooms:*** The number of bathrooms in the home.
* ***Sqft_living:*** The square footage of the living space.
* ***Floors:*** The number of floors in the home.
* ***View:*** A rating of the home's view.
* ***Date_built:*** The year the home was built.

### Variable Information
* ***Date:*** The sale date of the home.
* ***Price:*** The sale price of the home.
* ***Bedrooms:*** The number of bedrooms in the home.
* ***Bathrooms:*** The number of bathrooms in the home.
* ***Sqft_living:*** The living space square footage.
* ***Floors:*** The number of floors.
* ***View:*** A view rating.
* ***Date_built:*** The year the home was built.

## Stages of the Analysis
1. Setup Spark Environment:
* Installed Java and Spark.
* Set environment variables for Java and Spark.
* Initialized Spark and created a Spark session.

2. Load Data:
* Read the home sales data from an AWS S3 bucket into a DataFrame.
* Created a temporary view of the DataFrame.

3. Perform SQL Queries:
* ***request_1:*** Calculated the average price for a four-bedroom house sold per year.
* ***request_2:*** Calculated the average price of a home for each year it was built, for homes with 3 bedrooms and 3 bathrooms.
* ***request_3:*** Calculated the average price of a home for each year it was built, for homes with 3 bedrooms, 3 bathrooms, 2 floors, and at least 2,000 square feet.

4. Caching and Runtime Comparison:
* Cached the temporary table and performed a query to calculate the average price of a home per "view" rating, for homes with an average price of at least $350,000.
* Measured and compared the runtime of the query with and without caching.

5. Partitioning Data:
* Partitioned the home sales data by the date_built field and wrote it to Parquet format.

6. Create Temporary Table from Parquet Data:
* Read the partitioned Parquet data and created a temporary table.
* Performed the same query as in Step 4 on the Parquet data and measured the runtime.

7. Uncache Table:
* Uncached the home_sales temporary table and verified that it was no longer cached.

### Methods Used
* ***SQL Queries:*** To extract and analyze data.
* ***Caching:*** To improve query performance by storing data in memory.
* ***Partitioning:*** To organize data for efficient querying.
* ***Parquet Format:*** To store data in a columnar format that is optimized for query performance.
