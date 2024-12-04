# ETL Simulation Project

This project demonstrates the process of building an ETL (Extract, Transform, Load) pipeline using Python. The pipeline works with the Titanic dataset to showcase the steps involved in extracting data, transforming it, and loading it for further use.

---

## Key Features

### Data Extraction
- Fetches the Titanic dataset from an external URL.
- Converts the raw data into a pandas DataFrame for further processing.

### Data Transformation
- Cleans the dataset by removing irrelevant columns.
- Handles missing values by imputing them with appropriate substitutes.
- Enriches the dataset by adding a derived feature for family size.

### Data Loading
- Saves the transformed dataset into a structured CSV file for storage or further analysis.

---

## Accomplishments

### Data Extraction
- **Accomplishment**: Retrieved raw data programmatically from an external URL.
- **Details**: Used HTTP requests to fetch data and convert it into a structured format.

### Data Cleaning
- **Accomplishment**: Removed unnecessary columns (`Cabin`, `Ticket`) to simplify the dataset.
- **Details**: Handled missing values in critical columns such as `Age` and `Embarked`.

### Feature Engineering
- **Accomplishment**: Created a new feature (`FamilySize`) combining `SibSp` and `Parch`.
- **Details**: Represented the total number of family members traveling together.

### Data Storage
- **Accomplishment**: Successfully stored the transformed data in a CSV file.
- **Details**: Saved clean and enriched data into a reusable and structured format.

---

## Summary of Accomplishments
- **Dynamic Data Retrieval**: Programmatically fetched and processed real-world datasets.
- **Data Cleaning**: Simplified and cleaned data for easier analysis.
- **Feature Engineering**: Enhanced the dataset with meaningful derived features.
- **Structured Storage**: Saved clean and enriched data in a structured format for future use.

This project serves as an example of implementing the complete ETL process in a scalable and reusable manner.
