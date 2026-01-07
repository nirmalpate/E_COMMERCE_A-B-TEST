# E_COMMERCE_A-B-TEST
Post-Observed A/B Test for E-Commerce Revenue
Overview

This project demonstrates a post-observed A/B test scenario for an e-commerce business, evaluating the impact of a treatment (e.g., improved recommendations) on revenue per user and conversion rate.

The dataset is simulated and used for:

Sample size calculation

Experiment analysis

Post-observed revenue evaluation

The A/B test includes:

Success metric: Revenue per user (T-test)

Guardrail metric: Conversion rate (Chi-square test)

Minimum Detectable Effect (MDE): 30% revenue increase

Dataset

The simulated dataset includes the following columns:

Column	Description
user_id	Unique user identifier
group	Experiment group: Control or Treatment
base_price	Price per item
items_bought	Number of items purchased
total_revenue	Revenue per user before conversion
converted	Binary: 1 if user converted, 0 otherwise
post_revenue	Revenue after conversion (observed)
Requirements

Python >= 3.8

Libraries:

pandas
numpy
scipy


Install dependencies via pip:

pip install pandas numpy scipy

How to Run

Clone this repository:

git clone https://github.com/yourusername/ab-test-revenue.git
cd ab-test-revenue


Run the A/B test script:

python post_observed_ab_test.py


The script will output:

Required sample size per group

T-test results for revenue (success metric)

Chi-square test results for conversion (guardrail metric)

Baseline revenue and MDE

First 20 rows of the post-observed dataset

Sample Output
Required sample size per group: 132

Revenue per User Test (Success Metric)
T-Statistic: -1.012, p-value: 0.3124
Fail to reject null hypothesis: no significant increase in revenue per user.

Conversion Rate Test (Guardrail Metric)
Chi-Square Statistic: 0.732, p-value: 0.3921
Fail to reject null hypothesis: no significant difference in conversion rate between groups.

Baseline Revenue per user: €117.45
MDE (30% of baseline): €35.23

Post-Observed A/B Test Data (first 5 rows):
   user_id      group  base_price  items_bought  total_revenue  converted  post_revenue
0        1    Control   107.4456             1      107.4456          0          0.0
1        2  Treatment    45.2318             2      117.6037          1        117.6
2        3  Treatment    80.1234             1      104.16            0          0.0
3        4    Control    55.9871             3      167.9613          1       167.96
4        5  Treatment    75.4562             2      196.1720          1       196.17

Key Notes

MDE = 30% is used to determine the minimum detectable difference in revenue per user.

Revenue for Treatment group is increased by 30% in the simulation to reflect treatment effect.

post_revenue accounts for actual conversions (converted column).

This approach can be adapted for any e-commerce scenario, changing base_price, items_bought, or conversion probabilities.
