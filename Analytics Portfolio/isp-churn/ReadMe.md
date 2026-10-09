Customer Churn Analysis

Business Problem
Telecom company losing 14.5% of customers annually. Need to understand churn patterns and identify at-risk customers.

Data
2,666 customer records with service usage (calls/minutes), plan details, customer service interactions, and churn status. Limited to single company; no demographic or geographic segmentation available.

Approach
Analyzed relationship between customer service call frequency and churn rate. Compared churn across service plan types (international, voice mail). Built Power BI dashboard to visualize patterns by segment.

Key Insights
Customers with 0 service calls churn at 14.2%; those with 5+ calls churn at 59%
High call volume signals unresolved problems, not engagement
International plan subscribers churn at 43.7% vs 11.3% without, International plan customers are 3.9x more likely to churn than non-international customers.
Voice mail plan adoption reduces churn: 8.9% with voice mail vs 16.7% without voice mail

Recommendation
Audit support ticket resolution rates and implement first-contact resolution metrics. Prioritize proactive outreach to customers with 4+ service calls in the last 90 days. Investigate international service quality and billing issues separately. Expected impact: reducing high-contact customer churn by 15-20% saves ~300-400 customers annually.

Tools Used
Power BI

What I'd Do With More Data
Demographic/geographic data would reveal if churn patterns differ by customer type or region. Contract terms and pricing history would show if price sensitivity drives calls. Ticket resolution times would validate the "unresolved problems" hypothesis

![Dashboard Preview](ISP%20Churn%20Dashboard.png)
