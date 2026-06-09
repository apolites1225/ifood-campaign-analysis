# iFood — Marketing Campaign Performance Analysis

![Dashboard Demo](dashboard_demo.gif)

## Executive Summary

This project analyzes marketing campaign performance across 2,021 iFood customers, using Excel to identify which customer segments respond best to campaigns, what drives total spend, and how future campaigns should be targeted for maximum ROI.

Three material findings emerged:

- Campaign 6 achieved a 15.4% acceptance rate — more than double the next best campaign (7.7%) and nearly 12x Campaign 2 (1.3%).
- Campaign acceptors spend significantly more: $932 average vs. $564 for all customers — a 65% difference, indicating campaigns are reaching high-value segments.
- Income is the strongest spend driver: the $75K+ group averaged $1,373 in total spend, 25x the sub-$25K group — and showed the highest campaign responsiveness.

---

## Business Questions

1. Which of the 6 campaigns performed best, and why?
2. What customer profile is most likely to accept a campaign offer?
3. What demographic and behavioral factors drive total customer spend?
4. How should future campaigns be targeted to maximize acceptance and revenue impact?
5. Which campaigns should be scaled, and which should be retired?

---

## Data Sources

| Dataset | Description |
|---|---|
| Customer records | 2,021 rows after deduplication; 38 columns |
| Demographics | Age, income, marital status, education, household composition |
| Spend | Total spend + breakdown across 6 product categories (wines, fruits, meat, fish, sweets, gold) |
| Channels | Web, catalog, and in-store purchase counts; web visits per month |
| Campaigns | Binary acceptance flags for Campaigns 1–6 |
| Engagement | Days since last purchase (recency), customer tenure, complaint flag |

---

## Tools & Skills Used

- **Excel (Power Query):** Data transformation, cleaning, and deduplication
- **Excel (Power Pivot):** Data modeling with unpivoted campaign structure
- **DAX:** AVERAGEX and DISTINCTCOUNT measures for per-customer averages across unpivoted data
- **VBA:** Automated filter reset button
- **PivotTables & Slicers:** Cross-filtering across income, age, household, and education dimensions
- **Conditional Formatting:** Performance outlier highlighting

---

## Key Findings

**Campaign Performance**

Campaign 6 was the clear winner with a 15.4% acceptance rate — more than double Campaign 4 (7.7%) and nearly 12x Campaign 2 (1.3%). The overall average across all campaigns was 7.6%.

![Acceptance Rate by Campaign](AcceptanceRateChart.png)

**Acceptor Spend Profile**

Customers who accepted any campaign averaged $932 in total spend vs. $564 for all customers — a 65% premium. This confirms campaigns are reaching and activating high-value segments rather than low-value ones.

**Income as the Primary Spend Driver**

The $75K+ income group (16% of customers) averaged $1,373 in total spend — nearly double the $50K–$75K group ($783) and 25x the sub-$25K group ($54). This segment also accepted Campaign 5 at 37.6%, the highest rate of any income/campaign combination.

**Children at Home Suppresses Spend**

Customers with no children averaged $1,056 vs. $433 for one-child and $223 for two-child households — a 4.7x difference between child-free and two-child customers.


![Average Spend by Household Composition](Average_Spend_Household_Comp.png)


**Product Mix Concentration**

Wine (54.4% of avg spend, $306) and meat (29.5%, $166) together account for 83.9% of all customer spending, representing the primary levers for revenue-focused targeting.

**Age: An Underutilized Segment**

The 66+ age group showed the highest average spend ($699) and strong campaign acceptance (30%), but is likely underrepresented in campaign targeting.

---

## Key Business Recommendations

| Priority | Recommendation |
|---|---|
| 🎯 Target high-LTV segments | Focus premium campaigns on $75K+ income, child-free customers — highest spend and campaign responsiveness |
| 📦 Lead with wine and meat | These two categories drive 84% of wallet share; use them as primary campaign hooks |
| 📈 Scale Campaign 6 for volume | 15.4% acceptance rate — replicate its structure across the broader customer base |
| 💎 Use Campaign 5 for $75K+ targeting | 37.6% acceptance among the highest-LTV segment; optimal for high-margin acquisition |
| 👴 Activate the 66+ segment | Highest avg spend ($699) and 30% campaign acceptance — significantly underutilized |
| ❌ Retire Campaign 2's approach | 1.3% acceptance is not economically viable; reallocate budget to Campaigns 5 and 6 |

---

## Data Cleaning, Assumptions & Limitations

- Dataset contains 2,021 customer records after deduplication; original source includes duplicate entries removed via Power Query.
- Campaign acceptance is binary (0/1); analysis does not account for multiple campaign acceptances per customer beyond the provided flags.
- Spend figures represent total historical spend across all categories and do not reflect campaign-period spend specifically.
- Income brackets are self-reported and may not reflect current financial status.
- Analysis does not include cost-per-campaign or margin data — all ROI directional conclusions are based on spend differentials, not net profitability.

---

## Project Structure

```
ifood-campaign-analysis/
├── ifood_campaign_analysis.xlsm   # Full interactive Excel workbook (enable macros)
├── dashboard_demo.gif             # Animated dashboard walkthrough
├── dashboard_preview_3.png        # Dashboard screenshot
├── AcceptanceRateChart.png        # Campaign acceptance rate chart
├── Average_Spend_Household_Comp.png  # Spend by household composition chart
└── README.md
```

### How to Use the Workbook

1. Download `ifood_campaign_analysis.xlsm`
2. Enable macros if prompted
3. Navigate to the **Dashboard** tab
4. Use slicers to filter by Income Group, Age Group, Children at Home, or Education
5. Click **Reset Filters** to return to full dataset view
