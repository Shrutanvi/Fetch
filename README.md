# Fetch

Offer Similarity Search Documentation
Introduction
This Python script performs offer similarity search based on user queries using TF-IDF vectorization and cosine similarity. It utilizes three dataframes - df_brand, df_cat, and df_off - which are merged to create a comprehensive dataset. The code then follows data cleaning steps and builds a model to search for offers and related information.

Dependencies
pandas
numpy
scikit-learn
Exploratory Data Analysis
The script begins with exploratory data analysis (EDA) on the input datasets:

df_brand
Loaded from 'brand_category.csv'
Displayed first five rows and shape
Checked for missing values
Explored unique values and counts for 'BRAND' and 'BRAND_BELONGS_TO_CATEGORY'
df_cat
Loaded from 'categories.csv'
Displayed first five rows and shape
Checked for missing values
Explored unique values for 'PRODUCT_CATEGORY' and 'IS_CHILD_CATEGORY_TO'
df_off
Loaded from 'offer_retailer.csv'
Displayed first five rows and shape
Checked for missing values
Explored unique values for 'OFFER', 'RETAILER', and 'BRAND'
Merging Data
Merged df_brand and df_off on 'BRAND'
Further merged with df_cat on 'BRAND_BELONGS_TO_CATEGORY'
Displayed merged dataframes and their shapes
Data Cleaning
The script proceeds with data cleaning steps on the merged dataframe (df_merged):

Dropped columns 'CATEGORY_ID' and 'RECEIPTS'
Dropped rows with missing values in the 'OFFER' column
Cleaned special characters from the 'OFFER' column
Filled remaining missing values with 'None'
Displayed cleaned dataframe and its shape
Model Creation
The script creates two models:

Model 1: Searching for Offers
Vectorized 'OFFER' column using TF-IDF
Accepted a user query for a product category (e.g., "Bakery")
Calculated cosine similarity between the user query and offer vectors
Displayed relevant offers, retailers, brands, and similarity scores
Model 2: Searching Across Columns
The script provides flexibility to search across multiple columns:

Vectorized 'OFFER' column using TF-IDF
For a user query (e.g., "Diaper", "Huggies", "Target"):
Calculated cosine similarity across specified columns
Aggregated similarity scores
Displayed relevant offers and overall similarity scores
