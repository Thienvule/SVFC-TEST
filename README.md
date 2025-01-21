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

![image](https://github.com/user-attachments/assets/84b39dad-5798-4fd8-aa34-4196886be8f1)

#### 1. Remove Duplicate Rows: 
Eliminated one duplicate entry to ensure the uniqueness of records. There was only 1 duplicate row. The step was done using Excel built-in function of "Remmove Duplicate"

![image](https://github.com/user-attachments/assets/24e0c1cc-1a4e-49f8-8dc0-c7f29d326348)

#### 2. Change Data Types
The CREATED_DATE column contained poorly formatted time data, which might challenge the time series analysis later on. Changing the data type to "Date" effectively resolved the issue.

![image](https://github.com/user-attachments/assets/f2755310-77f0-4997-8066-4128dced4ade)
tbu
### Power BI
tbu

## Insights and Recommendation
Interactive Insight Dashboard

![image](https://github.com/user-attachments/assets/f6858c91-692c-494f-8703-bb8ddd0ff5e6)

Note: If the user wishes to explore further, they can always use the filter to do so.

![image](https://github.com/user-attachments/assets/4d9551f0-f6b8-4777-a9c6-121dd0d7d98e)

### High-level Observations

![image](https://github.com/user-attachments/assets/d85f6328-3b47-4335-a656-fe2fc8cbf774)

- Applications and Loan Amounts (Summary Metrics)
  - 109 Applications: A relatively small sample of applications is displayed, indicating this might be for a limited timeframe of March and the first week of April.
  - 2.62 Billion Loan Amount: This reflects a significant loan volume, indicating high-value loans are being processed despite the relatively low number of applications. However, more data of other months is needed for a clearer comparison analysis.
  - Approximately 57% of our customers are male, while only around 36% are female.

### Detailed Insights
#### Income Group

![image](https://github.com/user-attachments/assets/40d537d5-9c32-4811-b0ee-4368e17617be)


- The "Not Specified" (0 gross income from the raw file) group represents the majority of loan applications, with **1,302M** loan amounts.
  - **Insight**: Missing income data is a critical issue here, as this group dominates the dataset. Without clear segmentation by income group, tailored services or marketing strategies may be challenging.
  - **Action**: Consider investigating why income is not being captured or ensuring customers are required to input this data.
- For known income groups:
  - 10-19M earns the most loan amounts (950M), though applications are fewer.
  - Higher-income groups (20M+) account for fewer applications but significantly larger loan amounts on average. This suggests that wealthier customers tend to request larger individual loans (specifically 1 application with a 100M loan amount).
- Gender filtered:
  - Male: Has the same trend as the overall trend. Yet, once again emphasizing the lack of gross income data.
  - Female: female applicants in the income bracket of 10-19M have taken out significantly larger loans (470M) compared to the Not Specified group, highlighting the potential for targeted marketing strategies.

![image](https://github.com/user-attachments/assets/d945f83f-cf6d-4252-9729-a93eec09973b)

#### Current Location

![image](https://github.com/user-attachments/assets/0c365359-a9ad-42b3-93c2-f4ff5cda92e5)

Hồ Chí Minh (HCM) and Đồng Nai are the top locations for both applications and loan volume, with amounts of 481M and 382M, respectively. Notably, while Đồng Nai had a relatively lower number of applications, its loan amount still ranked second.
- Insight:
  - This suggests that targeted marketing efforts may be necessary to enhance application volume in Đồng Nai region.
  - Major urban centers like HCM/Hà Nội dominate, which aligns with expectations given higher population density and better financial access in cities.
  - Smaller cities like Bà Rịa/Hải Phòng/ showed lower applications (~60M loan amounts), yet it's still a potential considering the lower population density.
- Action:
  - Expand marketing outreach or digital campaigns in smaller provinces while strengthening the focus on areas like HCM and Đồng Nai where the bulk of demand currently exists.
  - Explore the specifics in Đồng Nai to identify the types of phones applicants are using, the sources from which they are applying, and their intended loan purposes. This information can be utilized to optimize our application, services and tailor financial products more effectively.
  
  ![image](https://github.com/user-attachments/assets/3c700606-c51c-4cf9-ae7d-7305d9cceb49)

#### Phone Type

![image](https://github.com/user-attachments/assets/2e92f0ae-ace8-444d-b024-ad36a82ebe5f)

iPhone dominates both in the number of applications (highest) and loan amounts (1,821M).
- Insight:
  - This suggests that applicants using iPhones may belong to a higher-income demographic or are more likely to successfully interact with the application platform.
  - Other significant contributions: Samsung and lower-tier brands like Xiaomi and OPPO contribute fewer applications overall and smaller loan amounts.
- Action: Ensure app performance is optimized for iOS devices, while improving accessibility and experience on Android devices to encourage broader adoption. This optimization could start from the UX/UI on different iOS platforms, starting with Google (filtered).

![image](https://github.com/user-attachments/assets/0eb9a343-987a-46e4-8be7-96065b99859b)


#### Source
Google, TikTok, and Facebook generate the highest applications and loan amounts, with Google (674M loan amount) being the top contributor.
- Insight:
  - Google might deliver high-value lead generation despite potentially higher costs compared to platforms like TikTok and Facebook.
  - EDM (Email) and Organic rank lower, indicating lesser engagement through these traditional or passive channels.
- Action:
  - Invest more resources into high-performing channels like Google and TikTok, while reassessing the ROI for EDM.
  - Enhance and further invest in the SEO strategy, as this organic channel has demonstrated its ability to passively generate applications.



Interactive Trend Dashboard

![image](https://github.com/user-attachments/assets/90005256-89e7-45e8-b70e-7269f437d37e)








