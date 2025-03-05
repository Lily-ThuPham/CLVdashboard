
# Project Background
Established in 2017, our subscription-based financial advisory service offers newsletters, webinars, and investment recommendations. We also provide daytime support for customer inquiries related to products, signups, and cancellations. As a data analyst at the company, I focus on monitoring key metrics like customer lifetime value (CLV), recurring revenue, and churn rate to maximize long-term value and growth potential. This dashboard aims to provide accurate and actionable insights to help achieve these objectives.

Objectives and insights are provided on the following key areas:

- **Category 1:** Manage and monitor customer lifetime value to maximize company long-term value
- **Category 2:** Investigate customer behaviour 
- **Category 3:** Call/Support center activities to further 

The document for Python code to explore, clean and transform data can be found here [link].

Targed SQL queries regarding various business questions can be found here [link].

An interactive Power BI dashboard used to report and explore sales trends can be found here [link].



# Data Structure & Initial Checks

The original dataset contains four tables: **customer_info**, **product_info**, **customer_product**, and **customer_case**. To achieve the project's objectives, I generated a new table, **transactions_table**, using Python, to calculate metrics such as Monthly Recurring Revenue (MRR). The tables are described as follows:

- **customer_info**: Contains customer information such as gender and age, with each customer identified by a unique `customer_id`. This table includes over 508,000 rows representing unique customers.
- **product_info**: Provides information on subscription plans offered by the company, including pricing and payment cycles.
- **customer_product**: Contains `customer_id` and their chosen subscription plan, along with signup and cancellation dates. It is important to note that each row is unique for a `customer_id`.
- **customer_case**: Documents call center data, with each row representing a unique case (`case_id`). This table includes the customer who made the call, the contact channel (phone or email), and the reason for the call.
- **transactions_table** (enriched table): Each transaction is documented by a row for every payment made. This table includes transaction date, signup and cancellation dates, transaction amount, the associated plan/product, and its payment cycle.
- **Calendar** (Common date table): A common date table is created in Power BI Query to aid in time-series metric calculation. 

![Entity Relation Database diagram](images/diagram/ERD_diagram.png)



# Executive Summary

### Overview of Findings

Our subscription service demonstrates robust growth, evidenced by a ***40.5% year-over-year increase at the end of 2021***. Monthly recurring revenue shows highly-stable growth driven by well-managed monthly customer base. This signals strong market fit and effective acquisition strategies. Our ***3.33% churn rate***, which has surged by 46.8% compared to 2020, signals an urgent need to bolster our customer retention efforts. Identifying churn drivers is crucial for sustainable growth. Despite overall positive trends, ***the average customer lifespan of 18.3 months***, although improve by 15.8% YoY, indicates an opportunity to improve customer retention strategy, especially within our large base of monthly subscribers.

![Customer Lifetime Value Dashboard](images/charts/dashboard_CLV.png)



# Insights Deep Dive
### Category 1: Customer lifetime value insights (in 2021 as an instant)

* **1.** *The overall YTD MRR shows generally positive trend* through out the year, ***increasing from 12.21ml from January to 16.3ml December***. The “Existing” MRR is the largest contributor (up to 92.5% when consider total Net recurring revenue of 2021) to the total MRR and shows a consistent upward trend throughout the year. Churned MRR is calculated to be a rolling sum of churned customer since the beginning of the period, the effect of rolling MRR is obvious in February or November since it deminized the growth of Net MRR. Additionally, New MRR contributions decrease in the latter half (*starting in June with 1.7ml to December 0.8ml*) , suggesting a projection of decreasing recurrent revenue, recurrent profit and potential challenges in acquiring new customers and sustaining existing ones. 

![Monthly Recurring Revenue in 2021](images/charts/2021_MRR.png)

  
* **2.** Customer Lifetime Value Chart suggests that the current subscriber based is generating good value over time with the total of ***$8.8K for a whole year 2021***, ***YoY increase is 44.3%***, which is very significant. There are seemingly a downward trend from January to July-2021 and a upward trend begin from August to the end of the year mirroring a gradual rise in average customer lifetime.. However, the fluctuations are too minor to point out a seasonal change.  
* A large majority of customers are on monthly plans.  The 10-12 month lifespan segment has the highest concentration of annual subscribers (149K), significantly more than any other segment.  Conversely, annual subscribers are most prevalent in the under 6 months segment (105K - 96.5%), indicating longer retention for annual plans. This suggests that while customer retention for monthly plans may fluctuate, overall customer value and lifespan are steadily improving, particularly for annual subscribers.

![Customer Distribution by their Lifespan](images/charts/Customer_distribution_bylifespan.png)


* **3.** *The overall number of churned customers have a increased tendency during the year* (rising from 894 customers in January to 1498 in December). This escalating churn count is mirrored by a fluctuating, yet ultimately increasing churn rate, which began the year at 0.90% and peaked at 1.02% in December. Specifically, the period from September to December shows a substantial increase in both churned customers and the churn rate. Churned customers jumped from 1,189 in September to 1,426 in December, while the churn rate rose from 0.89% to 1.01% during the same period. As expected, *monthly subscribers constituted the vast majority of churned customers* each month, given the shorter subscription cycle. Annual subscribers have a tendency to churned less untill the end of the year, indicating a better retention in annual customers. 

![2021 Monthly Amount of churned Customer and Churned Rate](images/charts/2021_ChurnbyProduct.png)


### Category 2: Analysis of Customer Behavior and CLV Drivers

![Customer Segmentation Dashboard](images/charts/dashboard_customer.png)


* **1.**  The annual product type significantly contributes to both revenue (64.21%) and customer based (64.0%), indicating higher value and potentially longer lifespans compared to other products.

* **2. The 18-35 age group is a high-value, low-volume segment and the 46-65 age groups are high-volume, steady-growth segments.**
  - *The 56-65 age group has the highest number of active customers*, followed by the over 65 group, while the younger age groups (18-35 and 36-45) have significantly fewer customers. The churn rate is also highest for the youngest age group (18-35) at 3.56%, followed by the 36-45 age group at 3.5%. The older age groups have lower churn rates, (56-65 group at 3.29%).
  - Despite this, *the ***18-35 group*** has the highest CLV at* ***$10.4K***, followed by 36-45 at $9.6K. Older groups have CLV values of 46-55 at $8.9K, 56-65 at $8.6K, and over 65 at $8.8K. *Subscription duration is highest for the 18-35 group at* ***18.8 months***, while the 56-65 group, despite having the most active accounts, subscribes for an average of 18.1 months. This indicates that the 18-35 group are highly valuable customers and a prime target for retention effort.


* **3. Analyzing subscription choices: annual plans are overall preferred with lower churned rate.**
  - In 2021, the ratio between monthly and annual subscriptions remained stable. Older age groups (over 35) preferred annual plans (62% - 64.68%), while the 18-35 group had only 57.8% annual subscriptions. Conversely, monthly subscriptions were more popular among the younger group, with 42.2%. Despite fewer monthly subscribers overall, they had a significantly higher churn rate (12.5% vs 1.1% churned rate of annual subscribers)

![Customer activity by age and products in 2021](images/charts/2021_age_product.png)

  - The above reviews that the company's products or services are more appealing to older age groups. It could be due to factors like product relevance, marketing targeting, or brand perception. While the younger customers are less loyal or have different needs and preferences compared to older customers, this could be due to factors like changing lifestyles, budget constraints, or a preference for newer trends and technologies.

### Category 3: Customer Support Center Dashboard 

![Customer Service Report Dashboard](images/charts/dashboard_service.png)

* ** 1.** Despite a 40.3% growth in customer base by the end of 2021, **support cases surged by 66.5%**, averaging over 371 cases per day – a 67% increase. This disproportionate rise in support requests, alongside the previously mentioned churn trends, highlights *potential issues with product usability or service quality*.
  
* ** 2.** However, *the average case per customer remains less than 2 cases/customer* (**1.28 case/customer YoY 12.2%**). This suggests that while the volume of support cases is high, individual customers are not repeatedly encountering issues.
  
* **3. The most cases concentrated in supporting for monthly subscribers**, with a peak from July to October 2021, reaching over 10K cases. However, the churned customer trend, while fluctuating, doesn't directly correlate with the support case volume. 
  
* **4.** In 2021, **customers aged 56-65** who contacted support exhibited the highest churn rate, with 7K out of 50K active cases ultimately churning.  Specifically, **male monthly subscribers** in this age group displayed the highest contributions.


# Recommendations:

Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following:

* Incentivize Annual Subscriptions: Average customer lifespan is less than 2 years YTD despite 5 years of service providing. Offer discounts and benefits to convert monthly subscribers to annual plans, emphasizing value and cost savings.

* Target Younger Demographics: Younger demographic is the main driver of Customer lifetime values. Enhance digital marketing on platforms frequented by younger audiences and tailor content to each age group's financial interests.

* Improve Support for Older Demographics: Investigate the high churn rate of older customers (46-65) after support interactions and implement specialized training or resources to address their needs.

* Minimize churn rate by extensive churn analysis and competition benchmarking: The volume of churned customer and rate of churn has a tendency to increase by the end of the year, contributed vastly by monthly subscribers.

* Optimize Support & Product Usability and improve customer experience: Analyze support cases and customer feedback to identify areas for improvement in product usability and support processes, especially with monthly customers who are reported with most support requests. 

* Enhance Customer Retention: Implement proactive retention strategies, including loyalty programs and personalized engagement, to reduce churn and maximize CLV.

* Deepen Customer Understanding:  Analysis suggests the customer tendency to favor annual plans however they tend to churn after one year. Develop detailed customer profiles to understand their journey, preferences, and churn reasons.  Use this data to personalize communication and optimize offerings. 


# Assumptions and Caveats:

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* Assumption 1 - Transaction Timing: Subscription fees are assumed to be charged on the signup date and at the beginning of each new cycle (30 days for monthly, 365 days for annual) until cancellation.
  
* Assumption 2 - Unique Customer IDs: Each customer_id is assumed to represent a unique customer with only one signup and cancellation date, implying no re-subscriptions.
  
* Assumption 3 - Business Start Date: The analysis assumes the business commenced in 2017, based on the earliest data available in the dataset.
