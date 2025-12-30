# Greenweez-Marketing-Performance-Analysis
This project analyzes paid marketing performance data from Greenweez across multiple advertising platforms. Using SQL in BigQuery, I combined raw ads and sales data, built staging tables, calculated key marketing KPIs, and analyzed revenue performance over time using window functions.
## Dataset Overview
- Paid advertising data from Google Ads (AdWords), Bing, Criteo, and Facebook
- Daily campaign-level metrics: ads_cost, click, impression
- Sales data with daily revenue and order information
- One row per campaign per day in ads tables
## Tools Used
- SQL (BigQuery)
- Excel (light data exploration and validation)
- Looker Studio (for dashboard visualization)
## Project Structure
- `raw_gz_*` tables: original raw data
- `stg_ads_all`: unified ads data across all platforms
- `stg_sales_daily`: daily aggregated sales data
- `ads_sales_daily`: ads data joined with revenue
- `channel_kpis`: aggregated KPIs by marketing channel
## Analysis Steps
1. Explored raw ads and sales data to verify granularity and uniqueness
2. Built a staging table combining all advertising platforms using `UNION ALL`
3. Aggregated daily sales revenue
4. Joined ads data with sales data using a left join
5. Calculated marketing KPIs after aggregation (ROAS, CPC, CTR)
6. Ranked channels by ROAS using window functions
7. Calculated cumulative revenue over time by channel
8. Analyzed monthly performance trends
## Key Metrics
- **ROAS (Return on Ad Spend)** = Revenue / Ads Cost
- **CPC (Cost per Click)** = Ads Cost / Clicks
- **CTR (Click-Through Rate)** = Clicks / Impressions
KPIs are calculated after aggregation to avoid averaging ratios.
## What This Project Demonstrates
- Building staging tables from raw data
- Combining multiple data sources with consistent schema
- Correct KPI calculation and defensive SQL practices
- Use of window functions for time-based analysis
- Translating business questions into SQL queries
## Visualizations
An interactive Looker Studio dashboard is built on top of the final analytical tables to visualize:
- Revenue and ad spend trends over time
- Channel-level performance comparison
- ROAS, CPC, and CTR evolution
- Cumulative revenue by channel

(Dashboard screenshots and link to be added.)

## Key Insights
Preliminary analysis shows:
- All paid channels generate revenue proportional to spend, indicating controlled budget allocation
- ROAS varies by channel, highlighting opportunities for budget reallocation
- Revenue accumulation over time is steady across channels, with no extreme volatility

Final insights will be refined through dashboard analysis.

## Limitations
- Revenue is joined at the daily level and not directly attributed to individual campaigns
- No user-level or conversion funnel data is available
- Results reflect historical performance and do not include predictive modeling

