# Home Sales Data Analysis with PySpark

## Overview

This project performs data analysis on a home sales dataset using PySpark and SparkSQL. The analysis includes calculating key metrics such as the average price of homes based on various criteria, optimizing performance through caching and partitioning, and comparing query run times. The steps include creating temporary views, partitioning the data, caching tables, and using SparkSQL to query the dataset.

## Project Structure

The key tasks in this project include:

1. **Loading Data into Spark DataFrame**: The home sales data is read from a CSV file (`home_sales_revised.csv`) into a PySpark DataFrame.
2. **Creating Temporary Tables**: A temporary table is created from the DataFrame to run SparkSQL queries.
3. **Running Queries**: Multiple queries are written using SparkSQL to answer the following:
   - The average price of a four-bedroom house sold for each year.
   - The average price of a three-bedroom, three-bathroom house for each year the home was built.
   - The average price of a home with three bedrooms, three bathrooms, two floors, and greater than or equal to 2,000 square feet for each year the home was built.
   - The average price of a home per "view" rating, where the average home price is greater than or equal to $350,000.
4. **Caching and Performance Optimization**: 
   - Caching the home sales temporary table to improve query performance.
   - Running and timing the same query before and after caching to compare run times.
   - Partitioning the data by the `date_built` field and writing it to parquet format.
   - Re-running the same query using the partitioned parquet data and comparing the run times.
5. **Uncaching the Temporary Table**: Finally, the home sales temporary table is uncached and verified.

## Dataset

The dataset contains information on home sales, including:
- `price`: Sale price of the home.
- `bedrooms`: Number of bedrooms.
- `bathrooms`: Number of bathrooms.
- `floors`: Number of floors in the house.
- `sqft_living`: Square footage of the house.
- `date_built`: Year the home was built.
- `view`: View rating of the home.


## Results

The run time for the uncached, cached, and partitioned queries are compared, demonstrating the performance improvements provided by caching and partitioning the data.
The time taken gradually decreased from uncached to cachesd and partitioned queries.

## Conclusion

This project uses SparkSQL to efficiently query and analyze home sales data. Caching and partitioning significantly improve performance, especially for large datasets. The use of temporary tables and parquet file formats further optimizes query execution times.

## Technologies Used

- PySpark
- SparkSQL
- Jupyter Notebook
- CSV and Parquet file formats
