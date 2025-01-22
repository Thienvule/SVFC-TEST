# SVFC-TEST

**Disclaimer: This repository is only available for those who are granted permission as this is a test at the time being.**

## Context Overview
The SVFC marketing team has gathered customer data for March and April 2024. The manager has tasked me with analyzing insights from the customer segment that registered for loan products on iShinhan. Additionally, I will provide recommendations for the performance team for the upcoming month.

The current timeline: The second week of April 2024.

Tool used:
- Power Query: Data cleaning and processing
- Power BI: Visualize insights

## Technical

### Excel & Power Query
The interpretation of each raw column will be provided in the Dictionary tab of the submitted file. 

![image](https://github.com/user-attachments/assets/44a102bd-4aa7-4066-9b9a-4509f978e8e0)


The raw data needs big cleaning, it was filled with typos, duplicate values, inconsistent formatting, missing values, etc.

![image](https://github.com/user-attachments/assets/84b39dad-5798-4fd8-aa34-4196886be8f1)

All of the Query steps have been assign a name for users to double-check:

![image](https://github.com/user-attachments/assets/e787d8b2-b550-41dc-b8ec-ff27f6c76357)

Note: In the context of this project, I will not be using Code_type and Status columns. Alright, let's get started.

#### 1. Remove Duplicate Rows: 
Eliminated one duplicate entry to ensure the uniqueness of records. There was only 1 duplicate row. The step was done using Excel built-in function of "Remmove Duplicate"

![image](https://github.com/user-attachments/assets/24e0c1cc-1a4e-49f8-8dc0-c7f29d326348)

#### 2. Change Data Types
The CREATED_DATE column contained poorly formatted time data, which might challenge the time series analysis later on. Changing the data type to "Date" effectively resolved the issue.

![image](https://github.com/user-attachments/assets/f2755310-77f0-4997-8066-4128dced4ade)

#### 3. Align Column Names:
Standardize column names to be in English and capitalize them for uniformity.

![image](https://github.com/user-attachments/assets/839a49a7-5e78-4cb0-9018-8fa8ea0371af)

#### 4. Remove Redundant Information:
Eliminate unnecessary details from the Industry Sub (e.g., removing "Manuf.") to streamline the data.

![image](https://github.com/user-attachments/assets/f8cc3308-9f90-49ff-9faf-186decc5f7e2)


#### 5. Handling Missing Values and Typos:

![image](https://github.com/user-attachments/assets/331fb949-778a-40e5-a2b3-8f1c3d64785e)

- For Loan Purpose, Phone Type, Gender assign (using a built-in feature Replace Values) a placeholder value of "Unknown" for missing entries.
- Retain entries with a gross income of 0 while noting the need for further investigation.
- For the Type column, fill in missing values with the most frequently occurring categorical value to maintain data integrity.
- For WARD_NAME, there were data entry inconsistencies such as XÃ vs X. ỏ PHƯỜNG vs P. This was solved by replacing all XÃ/PHƯỜNG BY X. and P.

#### Create New Columns
Add new columns to enhance analysis:
- INDEX: An INDEX column has been created to serve as the primary key for loan applications after removing duplicate rows. This column can later be utilized to COUNT the applications effectively.
- DAY_OF_WEEK: This column indicates the day of the week corresponding to the CREATED_DATE, facilitating time-based analysis.

  ![image](https://github.com/user-attachments/assets/cd85831a-56b3-423e-beda-d31738f00885)

- WEEK_OF_MONTH: This column reflects the week of the month derived from the CREATED_DATE, useful for understanding monthly application trends.

  ![image](https://github.com/user-attachments/assets/f55dfa13-db68-450b-9566-5601a2166beb)

- Loan Application Index: A unique identifier for each loan application. This was done using Index Column in Power Query.
- Phone Model: Information about the specific model of the applicant's phone, serving as a support column to create "Phone Type" column later on. This is done by taking what is after the first delimiter "-" and before the second "-"

  ![image](https://github.com/user-attachments/assets/24c74833-77c7-452c-9c44-a56a23379c73)
  ![image](https://github.com/user-attachments/assets/b8ea5e69-82a0-47f5-a864-5116551d4788)

- Phone Type: Classification of the type of phone used for the application. This was done by taking what is before the first " " (space) 

  ![image](https://github.com/user-attachments/assets/570681d2-a1c9-4314-bada-4828d1a9d2fc)

- Operating System (OS): The operating system of the applicant's device. This was done using Conditional Column

![image](https://github.com/user-attachments/assets/f221ec16-c4a4-4371-857b-000ffe449aaa)



### Power BI
1. Create new columns
-    Age Group: The dataset includes a wide range of ages, making analysis challenging and less effective. Therefore, categorizing these ages is a beneficial approach.

![image](https://github.com/user-attachments/assets/969dac4e-1cb9-4f6c-a869-03cb582321a6)

- Income Group: Likewise, income will be classified into four specific categories: 'Not Specified' (for records with zero gross income), '<10M', '10-19M', and '20M+'.

![image](https://github.com/user-attachments/assets/31efaf62-5466-4e1c-84bb-59b4afaef0f0)

## Insights and Recommendation
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

##### Loan Purpose

![image](https://github.com/user-attachments/assets/30a89ebc-c46c-45b7-95e6-be6b5463c4cb)

- "Unknown" dominates applications and loan amounts (2312M loan amount) again due to missing or unclear data on loan purposes.
- Other identified purposes include:
- Home purchases contribute 170M loan amounts — the top specified reason.
- Maintenance services like “Mua phương tiện” and Sửa chữa nhà contribute smaller loan volumes (120M; 20M respectively).
- Insight: Missing information regarding loan purposes poses a significant analytical limitation.
- Action:
  - Ensure that customers input accurate loan purposes during application submissions to better the tailor messages.
  - Promote popular loan services like home purchases through enhanced marketing campaigns.

##### Industry

![image](https://github.com/user-attachments/assets/d1b3e8f6-4fea-4f95-b414-0917a8536cfb)

- The "Unknown" category constitutes a large percentage of applications and the largest loan volume (1,302M loan amount), followed by:
- Office work (516M) and Financial Acts (246M).
- Insight: Missing industry data represents another significant data gap. However, office workers and finance professionals are key segments contributing to loan demand.
- Action:
  - Mandate the collection of industry data within the application process.
  - Develop specific loan products tailored to these key segments (e.g., office workers, financial professionals).

##### Reject Reasons

![image](https://github.com/user-attachments/assets/4c985e65-b4a0-4cd9-a6d1-660a42fdaa17)

- Top reasons for loan rejection include:
  - Ver-Uncontactable with 10 instances.
  - Other reasons include TUD-No show, cannot contact, restricted profile, lack of documents.
- Insight: Most rejections are due to unsuccessful contact reflecting process bottlenecks or lack of qualification. Besides, 5 of the most value loan as mentioned before were rejected because of this reason.
- Action:
  - Advocate for better communication during application submission to reduce errors.
  - Provide an educational guide or FAQs to help applicants meet eligibility criteria.


#### Key Recommendations
1. Data Gaps:
- Missing data in Income Group, Loan Purpose, and Industry significantly limits deeper analysis.
- Action: Review the data collection process to ensure all relevant fields are filled during application submissions.
2. Performance by Marketing Channel (This can be done using the Trend Dashboard):
- Invest more in high-performing channels like Google and TikTok.
- Explore reasons for low performance in Organic channels to improve engagement.

3. Focus on High-Performing Segments:
- Prioritize urban regions like Hồ Chí Minh and Đồng Nai, where demand and loan amounts are highest.
- Customers using iPhones represent a premium segment worth targeting with higher loan tiers or specialized financial products.

4. Optimize for Phone Types: Improve user experience for Android devices since these customers show some engagement but contribute less compared to iPhone users. Of course, we need to continue to maintain iOS user experience.

5. Rejections: Review and address process inefficiencies to reduce application rejections and boost conversion rates.

### Interactive Trend Dashboard

![image](https://github.com/user-attachments/assets/ba526a60-0433-43f7-9e2b-c77cf8987741)

#### Application and Loan Amount by Week of Month

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


#### Application and Loan Amount by Day of the Week

![image](https://github.com/user-attachments/assets/c1d1c4ed-1b7a-4555-888c-c9426c599d21)

- Observations:
  - Wednesday through Saturday (Days 3–6) show the highest activity:
  - Thursday and Friday drive the most applications (~40 applications), with corresponding loan amounts of 783M and 728M, respectively.
  - Activity drops significantly on Sundays and early weekdays (Day 0, Day 1).
- Insights:
  - Mid- to late-week days (Wednesday through Saturday) are critical for loan applications and volumes, likely due to increased consumer interaction and decision-making on these days.
  - Early weekdays and Sundays are quiet periods, suggesting a need for better outreach or incentives to boost activity during these off-peak times.
- Action:
  - Concentrate marketing campaigns and promotional efforts during high-activity days (Wednesday-Friday) for maximum impact.
  - Develop engagement strategies (e.g., exclusive offers, reminders) for Monday and Sunday to level the distribution of applications.

#### Application and Loan Amount by Day of Week and Source

![image](https://github.com/user-attachments/assets/b92ae12e-2df7-46e8-985d-9c2c4740268d)

- Observations:
  - Across all sources, TikTok and Google maintain consistently high application and loan amount contributions, particularly on high-performing days (Wednesday–Saturday).
  - TikTok/Google significantly leads on days of the week with spikes, whereas Facebook, Organic, and EDM sources exhibit relatively flat performance throughout the week.
- Insights:
  - TikTok/Google drives traffic and high loan amounts on key days, showing its potential for targeted, time-specific campaigns aimed at capturing week-day momentum.
  - Facebook applications also peaks on Thursday, followed by a significant drop.
  - EDM underperformance suggests either ineffective targeting or lower user engagement with this channel during the week.
- Action:
  - Leverage TikTok/Facebook (on Thursday)/Google with daily-specific campaigns (e.g., peak offer periods mid-week).
  - Perform a deep dive into non-performing channels like EDM, focusing on engagement strategies and user behavior analysis.

#### Key Recommendations
1. Source Performance:
- TikTok and Google are the standout performers across all metrics (applications and loan amounts).
- Actions:
  - Focus on scaling TikTok campaigns for high-tech demographics and larger loan amounts.
  - Double down on high-performing Google campaigns while refining targeting for mid-tier income brackets.

2. Timing and Week Trends:
- Applications and loan amounts pick up mid-week and peak in Week 5 or Wednesday-Saturday.
- Actions:
  - Align campaigns and promotions with mid-week days and Week 5 intensity.
  - Explore campaigns for off-peak periods (early weekdays and Sundays) to level out distributions.

3. Underperforming Channels:
- Facebook, EDM, and Organic sources show low engagement and minimal contribution to applications and loan amounts.
- Actions: Assess the ROI of these channels and test alternative strategies, such as new content formats, audience segmentation, or cross-channel marketing efforts.

4.Consumer Activity:
- The increase in activity in later weeks and towards the middle/end of the week suggests loan decision-making aligns with pay cycles, financial obligations, or successful outreach campaigns.
- Actions: Map campaigns and communications to customer paydays or known financial cycle triggers to maximize impact.





















