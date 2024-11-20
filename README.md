Dataset
This project demonstrates the process of cleaning and standardizing a dataset containing information about layoffs across various companies, sourced from Kaggle. The dataset is prepared for exploratory data analysis (EDA) and further insights extraction using SQL.

Dataset
Source: Kaggle - Layoffs 2022 Dataset

The dataset contains the following key columns:

company: Name of the company.
location: Location of the layoffs.
industry: Industry sector of the company.
total_laid_off: Number of employees laid off.
percentage_laid_off: Percentage of the workforce affected.
date: Date of the layoff.
stage: Funding or growth stage of the company.
country: Country where the layoffs occurred.
funds_raised_millions: Total funds raised by the company (in millions).
Objective
This project focuses on:

Data Cleaning: Removing duplicates, standardizing values, and correcting inconsistencies.
Data Preparation: Transforming the data into a structured and analyzable format.
Handling Null Values: Appropriately managing missing or invalid data.
Standardization: Ensuring consistent formatting across key fields.
Steps Performed
1. Staging Table Creation
A staging table (layoffs_staging) was created to preserve the original dataset and serve as the workspace for cleaning.
2. Duplicate Removal
Identified duplicate rows using ROW_NUMBER() with a PARTITION BY clause.
Deleted unnecessary duplicates while retaining unique rows.
3. Standardization
Fixed inconsistencies in industry (e.g., unifying "Crypto Currency" and "CryptoCurrency" as "Crypto").
Removed trailing periods and unnecessary whitespaces in the country column.
Converted the date column from TEXT to DATE format.
4. Null Handling
Converted empty strings to NULL for easier processing.
Populated missing industry values using non-null entries for the same company.
5. Data Cleanup
Removed rows with critical missing values (e.g., both total_laid_off and percentage_laid_off null).
Dropped auxiliary columns, such as row_num, after deduplication.
SQL Queries
The repository contains detailed SQL scripts demonstrating the above steps, including:

Duplicate Detection and Deletion
Standardization Updates
Date Formatting
Null Value Handling
