# ETL Simulation Project

---

## Project Overview
This project demonstrates an ETL (Extract, Transform, Load) pipeline using Python, working with the Titanic dataset. The focus is on the key steps of extracting data from an external source, transforming it for usability, and loading it for analysis.

---

## Accomplishments

### **Extract**
- **Accomplishment**: Successfully fetched the Titanic dataset from a remote URL.
- **Implementation**:
  ```python
  import pandas as pd
  import requests
  from io import StringIO

  def extract():
      # URL of the Titanic dataset
      url = 'https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv'

      # Use requests to get the raw data
      response = requests.get(url)

      # Convert the data to a pandas-readable format
      if response.status_code == 200:
          data = StringIO(response.text)
          df = pd.read_csv(data)
          return df
      else:
          raise Exception(f"Failed to fetch data. HTTP Status Code: {response.status_code}")

  # Extract the data
  titanic_df = extract()
  print("Dataset extracted successfully.")

Transform
Accomplishment: Applied preliminary transformations to prepare the dataset for analysis.
Implementation:
python
Copy code
def transform(df):
    # Drop columns that are irrelevant
    df = df.drop(columns=["Cabin", "Ticket"])

    # Handle missing values
    df["Age"].fillna(df["Age"].median(), inplace=True)
    df["Embarked"].fillna("Unknown", inplace=True)

    # Create a derived column for family size
    df["FamilySize"] = df["SibSp"] + df["Parch"] + 1

    return df

# Transform the data
transformed_df = transform(titanic_df)
print("Dataset transformed successfully.")
print(transformed_df.head())
Load
Accomplishment: Loaded the cleaned dataset into a structured format for further use.
Implementation:
python
Copy code
def load(df, file_name="transformed_titanic.csv"):
    # Save the DataFrame to a CSV file
    df.to_csv(file_name, index=False)
    print(f"Dataset loaded successfully into {file_name}")

# Load the transformed data
load(transformed_df)
Technologies Used
Programming Language: Python
Libraries: pandas, requests, io
Dataset Source: Titanic dataset from DataScienceDojo on GitHub.
Summary
This project demonstrates the complete lifecycle of an ETL pipeline:

Extract: Fetched raw data from a remote source.
Transform: Cleaned and enriched the data for usability.
Load: Stored the processed data for future analysis or visualization
