# SVFC-TEST

**Disclaimer: This repository is only available for those who are granted permission as this is a test at the time being.**

## Context Overview
The SVFC marketing team has gathered customer data for March and April 2024. The manager has tasked me with analyzing insights from the customer segment that registered for loan products on iShinhan. Additionally, I will provide recommendations for the performance team for the upcoming month.

Tool used:
- Power Query: Data cleaning and processing
- Power BI: Visualize insights

### Raw Data Processing (Main points)
The interpretation of each raw column will be provided in the Dictionary tab of the submitted file. The processing steps will be explained in greater detail in the "Technical" section of this project.

Now, I will present the new columns generated to enhance our understanding of the insights:
- INDEX: An INDEX column has been created to serve as the primary key for loan applications after removing duplicate rows. This column can later be utilized to COUNT the applications effectively.
- DAY_OF_WEEK: This column indicates the day of the week corresponding to the CREATED_DATE, facilitating time-based analysis.
- WEEK_OF_MONTH: This column reflects the week of the month derived from the CREATED_DATE, useful for understanding monthly application trends.
- PHONE_MODEL: This column captures the specific phone model used by the customer when applying for the loan, providing valuable insights into customer technology.
- PHONE_TYPE: This column denotes the type of phone (e.g., iPhone, Samsung, OPPO) used by the applicant, which can be beneficial for optimizing the application experience.
- OS: This column specifies the operating system of the applicant's device, offering insights that can guide application optimization efforts.

Note: In the context of this project, I will not be using Code_type and Status columns.

## Technical

### Excel & Power Query
The raw data needs big cleaning, it was filled with typos, duplicate values, inconsistent formatting, missing values, etc.

#### 1. Remove Duplicate Rows: 
Eliminated one duplicate entry to ensure the uniqueness of records. There was only 1 duplicate row. The step was done using Excel built-in function of "Remmove Duplicate"

![image](https://github.com/user-attachments/assets/24e0c1cc-1a4e-49f8-8dc0-c7f29d326348)

#### 2. Data cleaning
Standardized and formatted various columns for clarity and consistency.

### Power BI


## Insights and Recommendation
Interactive Insight Dashboard

![image](https://github.com/user-attachments/assets/f6858c91-692c-494f-8703-bb8ddd0ff5e6)

Interactive Trend Dashboard

![image](https://github.com/user-attachments/assets/90005256-89e7-45e8-b70e-7269f437d37e)








