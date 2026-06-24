# Predictive-Customer-Value-Retention-Analytics
Overview

This project develops a predictive customer analytics framework using transactional retail data to identify high-value customers, forecast future customer lifetime value (CLV), and uncover retention opportunities.

The objective is to move beyond historical reporting and answer key business questions such as:

* Which customers are expected to generate the most future value?
* Which customer segments contribute most to future revenue?
* Which high-value customers are at risk of churning?
* Where should retention and loyalty efforts be prioritised?

The analysis follows an end-to-end customer analytics workflow:

* SQL for data cleaning and customer-level feature engineering
* Python for RFM segmentation and predictive CLV modelling
* Tableau for data visualisation dashboard

⸻

Dataset Used

Online Retail Dataset (UCI Machine Learning Repository)[https://archive.ics.uci.edu/dataset/352/online+retail]

This dataset contains transactional records from a UK-based online retailer between December 2010 and December 2011.

Key fields include:

* CustomerID
* InvoiceNo
* InvoiceDate
* Quantity
* UnitPrice
* Product Description
* Country

After cleaning:

* ~397,000 valid transactions retained
* 4,338 unique customers identified
* 2,790 repeat customers included in CLV modelling

⸻

Business Objectives

The project was designed to answer four key customer intelligence questions:

Customer Segmentation

Identify distinct customer groups based on purchasing behaviour and value.

Customer Lifetime Value Prediction

Forecast future customer value using probabilistic modelling techniques.

Retention Opportunity Identification

Detect high-value customers showing signs of disengagement.

Executive Decision Support

Translate complex customer analytics into actionable business insights through an interactive dashboard.

⸻

Methodology

Data Preparation (SQL)

Data cleaning and validation were performed in SQLite.

Key steps included:

* Removal of cancelled orders and returns
* Exclusion of missing customer identifiers
* Revenue calculation (Quantity × UnitPrice)
* Customer-level aggregation
* Creation of customer summary tables
* Data quality checks and validation

Customer-level features generated:

* Total Revenue
* Number of Orders
* Average Order Value
* Last Purchase Date

⸻

Customer Segmentation (Python)

RFM (Recency, Frequency, Monetary) analysis was used to classify customers according to purchasing behaviour.

Metrics calculated:

* Recency: Days since last purchase
* Frequency: Number of purchases
* Monetary Value: Total customer spend

Customers were segmented into:

* Champions
* Loyal High-Value
* At-Risk High-Value
* High Spend Occasional
* New / Potential Loyalists
* Lost / Low-Value
* Other

⸻

Predictive CLV Modelling (Python)

Customer Lifetime Value was estimated using the Lifetimes package.

Models used:

BG/NBD Model

Predicts future purchase frequency based on historical transaction behaviour.

Outputs:

* Expected future purchases over the next 180 days

Gamma-Gamma Model

Predicts future transaction value.

Outputs:

* Expected average spend per transaction

CLV Calculation

Predicted CLV was calculated as:

Predicted Purchases × Expected Average Spend

Resulting in a six-month projected customer lifetime value estimate.

⸻

Dashboard Development (Tableau)

An executive-facing Tableau dashboard was created to communicate customer insights.

Key dashboard components include:

KPI Cards

* Customers Included in CLV Model
* Total Predicted CLV
* Number of Champions
* Number of At-Risk High-Value Customers

Customer Segment Distribution

Visualises the relative size of each customer segment.

Predicted CLV by Segment

Shows which customer groups contribute most to future revenue.

Customer Value & Retention Analysis

Scatter plot combining:

* Recency
* Predicted CLV
* Predicted Purchase Frequency

Used to identify high-value customers requiring retention efforts.

Top 10 Customers by Predicted CLV

Highlights customers expected to generate the highest future value.

⸻

Key Findings

Segment Contribution to Future Value

* Champions contributed approximately 35% of total predicted customer value.
* Loyal High-Value customers contributed approximately 30%.
* High Spend Occasional customers contributed approximately 15%.

Together, these segments represented the majority of projected future revenue.

Retention Opportunities

The analysis identified a group of At-Risk High-Value customers with substantial future value but declining engagement.

These customers represent attractive targets for personalised retention campaigns.

Customer Value Concentration

A relatively small number of customers accounted for a disproportionate share of projected future value, highlighting the importance of customer-centric retention strategies.

⸻

Dashboard

<div class='tableauPlaceholder' id='viz1782265760678' style='position: relative'><noscript><a href='#'><img alt='Dashboard 1 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Pr&#47;PredictiveCustomerValueRetentionAnalytics&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='PredictiveCustomerValueRetentionAnalytics&#47;Dashboard1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Pr&#47;PredictiveCustomerValueRetentionAnalytics&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-GB' /><param name='filter' value='publish=yes' /></object></div>                


Repository Contents
```
customer-lifetime-value-retention-analytics/

├── SQL/

├── Python/

├── README.md
```
⸻

Tools & Technologies

* SQL (SQLite)
* Python
    * pandas
    * numpy
    * lifetimes (BG/NBD & Gamma-Gamma Models)
* Tableau
* Jupyter Notebook
