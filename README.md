# Customer Lifetime Value (CLV) & Revenue Segmentation  
**Telecom Analytics Project**

---

## Project Overview
This project focuses on **Customer Lifetime Value (CLV) estimation and revenue segmentation** using telecom customer data.  
The objective is to identify **which customers contribute the most revenue**, **which are at risk of churn**, and **where retention efforts should be prioritized**.

The project extends traditional churn analysis by combining **customer value** and **churn risk**, delivering insights that directly support **ROI-driven retention strategies**.

---

## Business Problem
In the telecom industry:
- Customer acquisition is expensive
- Retention budgets are limited
- Not all churn has the same financial impact

**Key Question:**  
> *Which customers should the business focus on retaining to maximize revenue impact?*

---

## Dataset
The analysis uses the same telecom customer dataset as the churn project, ensuring analytical continuity.  
Key features include:
- Monthly Charge
- Tenure (in months)
- Contract Type
- Payment Method
- Internet Service
- Customer Status (Churned / Retained)

---

## Methodology

### CLV Estimation
Customer Lifetime Value is estimated using an interpretable, business-aligned approach:

Expected Customer Lifetime (months) ≈ 1 / churn_rate
CLV ≈ Monthly Charge × Expected Lifetime

Key Insights
1. CLV Distribution

CLV is right-skewed

A small group of customers contributes a disproportionately large share of total revenue

<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/7ef78ccd-ebf0-4232-afb5-c0dace22d53f" />

2. Revenue Concentration (Pareto Effect)

Approximately 20% of customers account for the majority of estimated revenue

Confirms the importance of value-based customer prioritization

<img width="790" height="490" alt="image" src="https://github.com/user-attachments/assets/35b4a852-6de2-4f6f-a234-312ad3d88d61" />

3. CLV-Based Customer Segmentation

Customers are segmented into:

Low CLV

Medium CLV

High CLV

Insight:

High-CLV customers represent a smaller portion of the customer base but generate the largest revenue share

<img width="689" height="390" alt="image" src="https://github.com/user-attachments/assets/441f89d9-dae2-4fdd-8bb5-c80e482ed421" />

4. Value vs Risk Analysis

Customer value is combined with churn behavior to form value-risk segments:

Segment	Description
High CLV / Low Risk	Most valuable and stable customers
High CLV / High Risk	Highest retention priority
Low CLV / High Risk	Low ROI churn
Low CLV / Low Risk	Stable but low value

<img width="790" height="590" alt="image" src="https://github.com/user-attachments/assets/accf612c-3d34-4e6d-aea1-fa6eca2bc6b8" />

5. High-Value Customers at Risk

A subset of customers falls into the High CLV / High Risk category:

These customers generate significant revenue

Their churn would result in disproportionate revenue loss

<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>customers</th>
      <th>avg_clv</th>
      <th>total_clv</th>
      <th>churn_rate</th>
    </tr>
    <tr>
      <th>value_risk_segment</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>High CLV / Low Risk</th>
      <td>1542</td>
      <td>368.834492</td>
      <td>568742.787373</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>Medium CLV / Low Risk</th>
      <td>1608</td>
      <td>254.962594</td>
      <td>409979.850669</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>High CLV / High Risk</th>
      <td>811</td>
      <td>360.428235</td>
      <td>292307.298368</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Low CLV / Low Risk</th>
      <td>1934</td>
      <td>100.545310</td>
      <td>194454.629856</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>Medium CLV / High Risk</th>
      <td>672</td>
      <td>267.046410</td>
      <td>179455.187801</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>Low CLV / High Risk</th>
      <td>356</td>
      <td>127.446667</td>
      <td>45371.013537</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>nan / High Risk</th>
      <td>0</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>nan / Low Risk</th>
      <td>0</td>
      <td>NaN</td>
      <td>0.000000</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>
Conclusions

Customer revenue in telecom is highly concentrated

Churn should not be treated uniformly across all customers

High-value customers can still exhibit significant churn risk

Combining CLV with churn insights enables smarter, ROI-focused retention strategies

This analysis bridges the gap between churn prediction and business decision-making.

Actionable Business Recommendations
1. Prioritize High-Value, High-Risk Customers

Deploy targeted retention campaigns (discounts, service upgrades)

Assign proactive customer support outreach

2. Protect High-Value, Low-Risk Customers

Maintain service quality and loyalty incentives

Avoid unnecessary pricing changes

3. Optimize Retention Spend

Reduce aggressive retention efforts for low-CLV customers

Reallocate resources toward segments with higher revenue impact

4. Integrate Predictive Risk Scoring

Replace observed churn labels with churn probability scores

Continuously monitor risk in real time using dashboards
