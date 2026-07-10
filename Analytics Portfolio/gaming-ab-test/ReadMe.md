Gaming Player A/B Test Analysis

Business Problem
Mobile game company ran A/B test on promotional offer sets. Test group (B) received one offer variant, control group (A) received another. 
Objective: Identify which offer set maximizes revenue per player.

Data
400,770 player records across registration, authentication events, and A/B test assignments with revenue. No behavioral data (playtime, level progression, friend networks), limiting depth of engagement analysis.

Approach
Compared test group size, revenue distribution, and revenue-per-user across both versions. Built Power BI dashboard showing user counts, total revenue, and per-user spending by test group.

Key Insights
Test Group A: 202,103 users, $5.1M revenue, $25.41 per user
Test Group B: 202,667 users, $5.4M revenue, $26.75 per user
No statistically significant difference in spending between versions
Revenue difference ($285K) driven by both higher user count in B and higher spending per user

Recommendation
Group B outperforms on revenue per user by 5.3%, generating ~$285K additional annual revenue at current scale. While the uplift is modest, it's consistent and meaningful. Recommend A/B test for statistical significance to confirm this difference isn't due to random variation. If confirmed real, rollout B as default.

Tools Used
Power BI

What I'd Do With More Data
User engagement metrics (session length, daily active rate, feature adoption) would show if version affects engagement differently than spending. Retention curves would reveal long-term player value beyond first revenue. Cohort analysis by signup date would show if test effect varies over time.