# Will the Customer Accept the Coupon? — Starter EDA

This repository explores factors driving **coupon acceptance** while driving.

## Data
- Source: UCI ML repository (Mechanical Turk driving scenarios)
- File: `coupons.csv`

## Label
- Detected acceptance label column: `Y`

## Quick stats
- Rows: **12684**
- Columns: **26**
- Overall acceptance rate: **0.568** (fraction of 1s) if label was detected.

## Questions explored
1. Which **coupon types** are most likely to be accepted among all coupon types? 
2. How do **contextual factors** (destination, passenger, time, weather, expiration) shift acceptance?
3. How do **habits** (bar/coffee/restaurant frequencies) relate to acceptance for different types of coupons?

## Key findings
1.Bar Coupons
- **Frequent bar-goers** (more than 3×/month) are **2.5× more likely** to accept bar coupons than infrequent visitors, highlighting strong behavioral alignment.  
- **Social and contextual factors** matter — drivers with **friends or partners (no kids)** and aged **26–40** are most likely to redeem.  
- **Middle-income and unmarried-partner drivers** show lower acceptance, suggesting lifestyle context outweighs income.

2. Coffee House Coupons
- **Frequent coffee drinkers** (>3×/month) are **1.5× more likely** to accept coffee coupons, with acceptance peaking **in the morning** and **en route to work**.  
- **Female drivers** and those with **no urgent destination** show higher engagement, emphasizing convenience and timing.  
- **Lower and higher income segments** are more responsive than middle-income drivers, suggesting value sensitivity and habitual consumption both drive behavior.

3. All Coupons (Cross-Type)
- **Carry Out & Takeaway** coupons have the **highest acceptance rate**, while **Bar** and **Restaurant** coupons perform worst.  
- Drivers prefer **low-effort, convenience-based offers** over those requiring detours or extended stops.  


## Recommendations & Next steps
- Comparing all Coupon types:
Drivers are most responsive to **convenient, quick-stop coupons** like Carry Out offers.  
Coupons requiring **longer detours or higher effort** (e.g., dining in) see lower engagement.  
Future strategies should emphasize **low-friction, convenience-based coupon types** 
- For Bar Coupons: 
Drivers who **frequent bars**, **travel with adult companions**, and are in the **26–40 age range** are the most receptive to bar coupons.  
Acceptance is driven more by **social context and lifestyle patterns** than by income level.  
Future targeting should emphasize **behavioral and situational signals** over broad demographic traits.
- For Coffee House Coupons:
Drivers who **frequent coffeehouses**, **travel during morning or early afternoon hours**, and have **no urgent destinations** are most receptive to coffee coupons.  
Acceptance likelihood increases for **female drivers** and those at the **lower or higher ends of the income spectrum**.  
Future targeting should emphasize **habit frequency, time of day, and trip context** over generic demographic factors.

