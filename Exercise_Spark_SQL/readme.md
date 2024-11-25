# Customer Sales Analysis: A PySpark Project

## Project Overview

This project demonstrates the use of PySpark for performing SQL-like operations and DataFrame transformations on a dataset representing customer sales. The dataset includes sales dates, store IDs, product details, quantities sold, prices, and calculated metrics. By leveraging PySpark's capabilities, we perform advanced analytics such as aggregations, calculated columns, and window functions.

## Key Features and Accomplishments

1. **Setup and Initialization**:
   - Configured PySpark and initialized a Spark session for data processing.

2. **Data Preparation**:
   - Created a structured schema for the sales dataset.
   - Built a PySpark DataFrame containing sales data.

3. **Data Exploration and Analysis**:
   - Displayed the dataset to verify structure and data.
   - Added calculated columns, including:
     - Total sales per transaction (quantity * price).
   - Aggregated total sales for each store.
   - Calculated average sales for each product.
   - Sorted sales data by date for chronological analysis.
   - Applied window functions to calculate cumulative sales by store.

4. **Insights Derived**:
   - Total and average sales metrics provide valuable insights for store and product performance.
   - Cumulative sales trends highlight sales growth over time.

## Technologies Used

- **PySpark**: A powerful framework for big data processing and analytics.
- **Jupyter Notebook**: For an interactive and iterative development environment.
