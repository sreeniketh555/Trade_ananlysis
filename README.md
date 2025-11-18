# Trade_ananlysis

##Project Overview

The objective is to analyze import data from January 2017 to October 2025 for steel-based household and kitchen products. The analysis will simulate real-world business intelligence by relying entirely on dynamic Excel formulas, PivotTables, and text parsing to derive insights from the raw data.

##Data Cleaning and Preparation

The initial step involves creating a Cleaned Data Sheet by augmenting the raw data. Key computational fields will be added:
Grand Total INR is calculated as the sum of TOTAL VALUE_INR and DUTY PAID_INR.
The Year is extracted from the DATE column.
The HSN Code is mapped to a standard description (e.g., 73239990) to enable product categorization.
Main Category (e.g., "Steel," "Others") and detailed Sub-category (e.g., "Scrubber," "Basket") are created by applying IF and SEARCH functions to the HSN and GOODS DESCRIPTION.
Crucially, the complex GOODS DESCRIPTION column is parsed using text functions (MID, FIND, LEFT/RIGHT) to isolate critical unit economics data: Model Name/Number, Item Quantity, and the specific Unit Price_USD.

##Macro-Level Trade Analysis

The Year-wise Summary sheet focuses on macro trends. It aggregates Total Value_INR, Duty Paid_INR, and Grand Total_INR by year. A core insight derived here is the Year-over-Year (YoY) growth percentage for the Grand Total_INR, visualized using a line chart to show purchasing trends over time.
The HSN Code-wise Summary then breaks down the overall value by product type. It calculates each HSN code's percentage contribution to the overall Grand Total_INR. The top 25 contributing HSN codes will be identified and the rest grouped into an "Others" category, providing a clear picture of the company's most important product segments.

##Unit Economics and Cost Analysis

Detailed analysis is performed on the Model Detail sheet, leveraging the parsed data to understand true per-unit costs:
Product Performance: Quantities and average unit prices (in USD) are tracked year-wise for specific models.
Landed Cost: A Duty/Unit_INR metric is computed by dividing DUTY PAID_INR by the QUANTITY to find the per-unit duty component. This is added to the UNIT PRICE_INR to derive the final cost per unit including duty.
Duty Structure: Rows are flagged where the Duty Percentage (DUTY PAID_INR / TOTAL VALUE_INR) exceeds the overall average, highlighting potential exceptional duty structures.
