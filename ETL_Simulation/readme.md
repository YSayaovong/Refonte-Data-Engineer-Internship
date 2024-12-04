# ETL Simulation Project: Complete Code

import pandas as pd
import requests
from io import StringIO

# Step 1: Extract
def extract():
    """
    Extracts the Titanic dataset from a remote URL and loads it into a DataFrame.
    """
    # URL of the Titanic dataset
    url = 'https://raw.githubusercontent.com/datasciencedojo/datasets/master/titanic.csv'

    # Use requests to get the raw data
    response = requests.get(url)

    # Convert the data to a pandas-readable format
    if response.status_code == 200:
        data = StringIO(response.text)
        df = pd.read_csv(data)
        print("Dataset extracted successfully.")
        return df
    else:
        raise Exception(f"Failed to fetch data. HTTP Status Code: {response.status_code}")

# Step 2: Transform
def transform(df):
    """
    Cleans and transforms the extracted DataFrame to prepare it for analysis.
    """
    # Drop columns that are irrelevant
    df = df.drop(columns=["Cabin", "Ticket"])

    # Handle missing values
    df["Age"].fillna(df["Age"].median(), inplace=True)
    df["Embarked"].fillna("Unknown", inplace=True)

    # Create a derived column for family size
    df["FamilySize"] = df["SibSp"] + df["Parch"] + 1

    print("Dataset transformed successfully.")
    return df

# Step 3: Load
def load(df, file_name="transformed_titanic.csv"):
    """
    Saves the transformed DataFrame to a CSV file.
    """
    df.to_csv(file_name, index=False)
    print(f"Dataset loaded successfully into {file_name}")

# Complete ETL Pipeline Execution
try:
    # Extract the data
    titanic_df = extract()

    # Transform the data
    transformed_df = transform(titanic_df)

    # Load the data
    load(transformed_df)

except Exception as e:
    print(f"An error occurred during the ETL process: {e}")
