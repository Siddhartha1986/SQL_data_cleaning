
# Nashville Housing Data Cleaning Project

## Project Overview
This project involves cleaning and organizing a dataset of housing data from Nashville. The primary focus is on standardizing date formats, populating missing address data, splitting addresses into individual components, and transforming categorical data for better usability and analysis. Special thanks to **Alex the Data Analyst** for organizing, the free Data Analyst Bootcamp.

## Dataset
The dataset, referred to as `NashvilleHousing`, is contained within the `PortfolioProject` database. It includes information about housing properties in Nashville, such as addresses, sale prices, and legal references.

## Objectives
The main objectives of this data cleaning project include:
- Standardizing date formats for consistency.
- Populating missing property addresses.
- Breaking down full addresses into separate columns for address, city, and state.
- Converting abbreviations in categorical data to full words for clarity.
- Removing duplicate records to ensure data integrity.
- Deleting unused columns to streamline the dataset.

## Cleaning Process
The data cleaning process involves several SQL queries:

1. **Standardizing Date Formats:**
   - Creating a new column `SaleDateConverted` with standardized date format.

2. **Populating Missing Property Addresses:**
   - Identifying records with null `PropertyAddress`.
   - Updating these records by joining on `ParcelID`.

3. **Splitting Full Addresses:**
   - Using `SUBSTRING` and `CHARINDEX` to split `PropertyAddress` into `PropertySplitAddress` and `PropertySplitCity`.
   - Employing `PARSENAME` and `REPLACE` to split `OwnerAddress` into `OwnerSplitAddress`, `OwnerSplitCity`, and `OwnerSplitState`.

4. **Transforming 'Sold As Vacant' Field:**
   - Changing values from 'Y' and 'N' to 'Yes' and 'No'.

5. **Removing Duplicate Records:**
   - Using a Common Table Expression (CTE) with `ROW_NUMBER` to identify and delete duplicates.

6. **Dropping Unused Columns:**
   - Removing columns like `PropertyAddress`, `SaleDate`, and `OwnerAddress` after their data has been restructured.

## Tools and Technologies
- SQL Server: For executing SQL queries and managing the database.

## How to Use
- Import the `PortfolioProject` database into your SQL Server instance.
- Execute the provided SQL scripts to clean and restructure the `NashvilleHousing` table.
- Analyze the cleaned data for real estate trends, market analysis, or further data processing.

## Future Enhancements
- Integrate data validation steps to prevent data quality issues in future data entries.
- Automate the data cleaning process for new data imports.
- Expand the dataset to include additional relevant features for comprehensive analysis.

