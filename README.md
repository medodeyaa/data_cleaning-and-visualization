# Restaurant Sales Data Cleaning and Analysis

## Overview
This project focuses on cleaning, imputing, and analyzing a restaurant sales dataset. The provided Jupyter Notebook takes a raw dataset containing missing values, applies systematic data imputation techniques, and performs Exploratory Data Analysis (EDA) to uncover sales trends, popular items, and revenue metrics.

## Dataset Information
The project utilizes the `restaurant_sales_data.csv` dataset. It contains recorded transactions across the following columns:
* **Order ID**: Unique identifier for the order.
* **Customer ID**: Unique identifier for the customer.
* **Category**: The menu category of the item.
* **Item**: The specific name of the food or beverage.
* **Price**: The cost of the item.
* **Quantity**: The number of items purchased.
* **Order Total**: The total cost of the order.
* **Order Date**: The date the transaction occurred.
* **Payment Method**: The method used by the customer to pay.

## Dependencies
The analysis is built using Python and requires the following libraries:
* `pandas`
* `numpy`
* `matplotlib.pyplot`
* `seaborn`

## Data Cleaning Pipeline
The dataset contains missing values that are systematically addressed through the following steps:
1. **Menu Mapping for Missing Items and Prices:** A unique `menu` dataframe is generated from non-null rows to map the relationships between `Category`, `Item`, and `Price`. This reference table is subsequently used to fill missing items and prices in the main dataset.
2. **Payment Method Imputation:** Missing payment methods are filled using the most frequent payment method (mode).
3. **Quantity Imputation:** Missing `Quantity` values represent a small percentage of the data. These are first deduced using the formula `Order Total / Price`. Remaining gaps are safely filled with the median quantity to prevent the unnecessary loss of entire rows of data.
4. **Order Total Calculation:** Missing `Order Total` values are calculated using the standard formula `Price * Quantity`.
5. **Column Formatting:** Column names are stripped of whitespace and converted to lowercase. The `Price` column is cleaned of non-numeric characters using Regular Expressions (Regex) and cast to a float data type.

## Exploratory Data Analysis (EDA)
After cleaning, the notebook generates several insightful visualizations and statistical checks:
* **Best-Selling Products:** A horizontal bar plot highlighting the Top 10 items based on the total quantity sold.
* **Sales by Category:** A bar plot showing which menu categories generated the most total revenue.
* **Monthly Sales Trends:** A time-series line chart tracking the total sales revenue grouped by month and year.
* **Payment Methods Distribution:** A bar plot showing the total number of transactions processed per payment method.
* **Average Order Value (AOV):** An analysis of the average order total segmented by payment method.
* **Top 5 Revenue Items:** A horizontal bar plot breaking down the specific menu items that brought in the highest total revenue.
* **Monthly Order Volume:** A line chart illustrating the total number of orders placed each month.
* **Weekend vs Weekdays:** A pie chart comparing the percentage of total revenue generated on weekends versus weekdays.

## Execution Instructions
1. Ensure the required dependencies (`pandas`, `numpy`, `matplotlib`, and `seaborn`) are installed in your Python environment.
2. Update the file path in the `pd.read_csv()` function to point to your local copy of the `restaurant_sales_data.csv` file.
3. Run the cells sequentially to execute the data cleaning pipeline and render the plots.
