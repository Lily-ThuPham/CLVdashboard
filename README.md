
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

[Entity Relationship Diagram here]



# Executive Summary

### Overview of Findings

Explain the overarching findings, trends, and themes in 2-3 sentences here. This section should address the question: "If a stakeholder were to take away 3 main insights from your project, what are the most important things they should know?" You can put yourself in the shoes of a specific stakeholder - for example, a marketing manager or finance director - to think creatively about this section.

[Visualization, including a graph of overall trends or snapshot of a dashboard]



# Insights Deep Dive
### Category 1:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 1]


### Category 2:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 2]


### Category 3:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 3]


### Category 4:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 4]



# Recommendations:

Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following: 

* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  


# Assumptions and Caveats:

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* Assumption 1 (ex: missing country records were for customers based in the US, and were re-coded to be US citizens)
  
* Assumption 1 (ex: data for December 2021 was missing - this was imputed using a combination of historical trends and December 2020 data)
  
* Assumption 1 (ex: because 3% of the refund date column contained non-sensical dates, these were excluded from the analysis)
