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

Technologies Used
Programming Language: Python
Libraries: pandas, requests, io
Dataset Source: Titanic dataset from DataScienceDojo on GitHub.
Summary
This project demonstrates the complete lifecycle of an ETL pipeline:

Extract: Fetched raw data from a remote source.
Transform: Cleaned and enriched the data for usability.
Load: Stored the processed data for future analysis or visualization.
