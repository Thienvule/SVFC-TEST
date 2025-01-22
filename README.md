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

## Technical (tbu)

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

## Insights and Recommendation (On-going)
### Interactive Insight Dashboard

![image](https://github.com/user-attachments/assets/f6858c91-692c-494f-8703-bb8ddd0ff5e6)

Note: If the user wishes to explore further, they can always use the filter to do so.

![image](https://github.com/user-attachments/assets/4d9551f0-f6b8-4777-a9c6-121dd0d7d98e)

#### High-level Observations

![image](https://github.com/user-attachments/assets/d85f6328-3b47-4335-a656-fe2fc8cbf774)

- Applications and Loan Amounts (Summary Metrics)
  - 109 Applications: A relatively small sample of applications is displayed, indicating this might be for a limited timeframe of March and the first week of April.
  - 2.62 Billion Loan Amount: This reflects a significant loan volume, indicating high-value loans are being processed despite the relatively low number of applications. However, more data of other months is needed for a clearer comparison analysis.
  - Approximately 57% of our customers are male, while only around 36% are female.

#### Detailed Insights
##### Income Group

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

##### Current Location

![image](https://github.com/user-attachments/assets/0c365359-a9ad-42b3-93c2-f4ff5cda92e5)

Hồ Chí Minh (HCM) and Đồng Nai are the top locations for both applications and loan volume, with amounts of 481M and 382M, respectively. Notably, while Đồng Nai had a relatively lower number of applications, its loan amount still ranked second.
- Insight:
  - This suggests that targeted marketing efforts may be necessary to enhance application volume in Đồng Nai region.
  - Major urban centers like HCM/Hà Nội dominate, which aligns with expectations given higher population density and better financial access in cities.
  - Smaller cities like Bà Rịa/Hải Phòng/ showed lower applications (~60M loan amounts), yet it's still a potential considering the lower population density.
  - Gender filtered:
    - The number of male applicants was twice that of female applicants. However, the total loan amount requested by female applicants (1.06 billion VND) was very close to the total amount requested by male applicants (1.31 billion VND).
    - In Hà Nam, although the number of loan applications was significantly lower than that in major cities like Ho Chi Minh City (HCMC), the total loan amount was considerably higher—300 million VND in Hà Nam compared to only 161 million VND in HCMC. This discrepancy suggests the need for further investigation and consideration of Hà Nam in our analysis.

![image](https://github.com/user-attachments/assets/caf560c2-b740-47f7-96f2-26267b96469a)


- Action:
  - Expand marketing outreach or digital campaigns in smaller provinces while strengthening the focus on areas like HCM and Đồng Nai where the bulk of demand currently exists.
  - Explore the specifics in Đồng Nai to identify the types of phones applicants are using, the sources from which they are applying, and their intended loan purposes. This information can be utilized to optimize our application, services and tailor financial products more effectively.
  ![image](https://github.com/user-attachments/assets/3c700606-c51c-4cf9-ae7d-7305d9cceb49)
  - Applicants in Đồng Nai typically seek loans to purchase household appliances. We can leverage this insight to tailor our marketing messages and share this information with our partner, Siêu thị điện máy nội thất Chợ Lớn in Đồng Nai.
  ![image](https://github.com/user-attachments/assets/c4cd9c8c-98f5-4f31-958c-338c6816ed76)
  - Upon further analysis of Hà Nam's insights, we noted that there were five applications with a high loan amount, but all applicants were uncontactable and subsequently rejected. We can share this information with our sales team to encourage them to reach out to these applicants again and retarget them through our marketing platforms with tailored messages specifically designed for office workers.
  

##### Phone Type

![image](https://github.com/user-attachments/assets/2e92f0ae-ace8-444d-b024-ad36a82ebe5f)

iPhone dominates both in the number of applications (highest) and loan amounts (1,821M).
- Insight:
  - This suggests that applicants using iPhones may belong to a higher-income demographic or are more likely to successfully interact with the application platform.
  - Other significant contributions: Samsung and lower-tier brands like Xiaomi and OPPO contribute fewer applications overall and smaller loan amounts.
- Action: Ensure app performance is optimized for iOS devices, while improving accessibility and experience on Android devices to encourage broader adoption. This optimization could start from the UX/UI on different iOS platforms, starting with Google (filtered).

![image](https://github.com/user-attachments/assets/0eb9a343-987a-46e4-8be7-96065b99859b)


##### Source
![image](https://github.com/user-attachments/assets/344e9c35-4163-4d7d-818f-a4f37a7442a3)

Google, TikTok, and Facebook generate the highest applications and loan amounts, with Google (674M loan amount) being the top contributor.
- Insight:
  - Google might deliver high-value lead generation despite potentially higher costs compared to platforms like TikTok and Facebook.
  - EDM (Email) and Organic rank lower, indicating lesser engagement through these traditional or passive channels.
  - Android users generally prefer TikTok and Facebook, whereas Google Search Engine Marketing (SEM) is more effective for engaging iOS users.
- Action:
  - Invest more resources into high-performing channels like Google and TikTok, while reassessing the ROI for EDM.
  - Enhance and further invest in the SEO strategy, as this organic channel has demonstrated its ability to passively generate applications.
    
  ![image](https://github.com/user-attachments/assets/8943b743-e571-4057-b3c3-52b433f4002f)
  ![image](https://github.com/user-attachments/assets/fa70d511-c290-415a-97d0-17940d4b3381)




### Interactive Trend Dashboard

![image](https://github.com/user-attachments/assets/ba526a60-0433-43f7-9e2b-c77cf8987741)



#### Week Number

![image](https://github.com/user-attachments/assets/7eb454ca-6267-488d-a08f-9311847ada3c)

- Observation
  - Applications and loan amounts increase significantly as the week progresses, peaking in Week 5 with 80 applications and a total loan amount of 1,647M.
  - Week 2 and Week 3 exhibit minimal activity, with relatively low applications (less than 5) and loan amounts (just 10M in Week 3).

- Insights: Most loan applications seem to cluster toward the end of the timeframe, particularly Week 5, indicating that customer behavior may accelerate as the month progresses. This could be due to payday cycles, financial obligations, or marketing/promotional campaigns concentrated in that period.
- Action:
  - Investigate Week 5's success by analyzing marketing efforts or user behaviors during this period and replicate effective strategies in lower-performing weeks.
  - Consider spreading campaigns or reminders earlier in the month (Weeks 2-3) to balance loan activity.

#### Application by Week of Month and Source

![image](https://github.com/user-attachments/assets/0f7aec2a-1477-4d1b-8c58-e626a9b0051d)

- Observations:
  - Google and TikTok are the leading traffic sources, especially in Week 5, with Google slightly outperforming TikTok in terms of growth trajectory.
  - Facebook, EDM, and Organic sources exhibit smaller contributions overall, with slower growth trends across all weeks.
- Insights:
  - Google and TikTok dominate as key platforms for generating applications, indicating strong engagement on these channels.
  - Facebook, EDM, and Organic sources may not be yielding optimal results, despite potentially being long-standing or low-cost channels.
- Action:
  - Allocate more budget and resources toward Google and TikTok while conducting tests (e.g. A/B testing) on Facebook and EDM to refine content and audience targeting.
  - Reevaluate and potentially overhaul EDM strategies or look into why this channel's growth lags despite being cost-effective.
  - Continue our SEO operation.

#### Loan Amount by Week of Month and Source

![image](https://github.com/user-attachments/assets/7afc4f99-0e62-41db-b4d4-fda6c1c10bb4)

- Observations:
  - Google contributes the highest loan amounts by Week 5, outperforming TikTok with roughly 500M loan amounts from Google alone.
  - TikTok remains steady across weeks, serving as a consistent second performer, despite a quick trough in March.
  - Facebook, Organic, and EDM show flat or marginal growth, limited to lower loan volumes compared to the above channels.
- Insights:
  - Google not only demonstrates high engagement but also attracts larger loan amounts, suggesting that users with existing loan needs are actively searching for loan options.
  - The disparity in loan volume suggests that optimizing the overall experience (from app use to loan usability) on platforms like Facebook and EDM or even our Organic site could boost performance.
- Action:
  - Strengthen Google campaigns with targeted ads highlighting loan products relating to the loan purposes (prioritizing vehicle loans as Google users' loan reason was to buy vehicles) for high-value customers from this channel. Digging deeper, we can use the filter section to focus on this vehicle loan need and see that these customers tend to approach us on the 4th week and on Wednesday (as demonstrated below)
    
    ![image](https://github.com/user-attachments/assets/703b0ba1-3036-4a02-9c2b-938261e82ae1)

  - This move, once again, could only be successful when we bettered our data collection process as we lack data on the "Not Specified" loan purpose.
  - Investigate why TikTok's application collapsed on the 3rd week to better our optimization.







