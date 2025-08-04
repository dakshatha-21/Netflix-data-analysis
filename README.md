# Netflix-data-analysis
This project focuses on cleaning and analyzing Netflix data  using Python and Pandas.

## Contents

Raw netflix data.xlsx :contain raw data 
Code.ipynb : Jupyter notebooks/scripts used for data cleaning and exploration
netflix_cleaned.xlsx : contains the cleaned data

## Tasks Completed

 1.**Data Loading & Setup**
 Loaded raw dataset (Raw netflix data.xlsx)
 Displayed data overview using .head(), .info(), .shape(), .describe()

2. **Data Cleaning**
 Handled missing values in key columns like director, cast, country, and rating

 Standardized show_id by removing prefix 's' using:
 
**df['show_id'] = df['show_id'].str.replace('^s', '', regex=True)**

Converted date_added to datetime format using:

**df['date_added'] = pd.to_datetime(df['date_added'])**

Split duration into a new numeric column duration_min:

**df['duration_min'] = df['duration'].str.extract(r'(\d+)').astype('Int64', errors='ignore')**
 
 Standardized column names (e.g., lowercase, snake_case format)

 Exported cleaned data to netflix_cleaned.xlsx

 3. **Data Inspection & Preprocessing**

 Identified null counts and data types

 Detected and prepared to handle outliers in duration_min

 Used .value_counts() to explore unique values in type, country, rating, etc.

Used regex operations for cleaning (e.g., show_id, duration)
  
*Used .apply() and .lambda functions for column-wise transformations*

 Applied .astype() with errors='coerce' or errors='ignore' for safe conversions

 Cleaned column names consistently for better downstream analysis

