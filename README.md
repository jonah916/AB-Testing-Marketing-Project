# A/B Testing Analysis – Control vs. Test Marketing Campaign
## Project Overview
This project simulates an A/B test analysis comparing the performance of two marketing campaigns:
* Control Campaign
* Test Campaign

The objective is to determine which campaign is more effective at driving user engagement and purchases, and to translate the findings into actionable business recommendations.
## Motivation
Inspired by my experience working with data related to customer growth, retention, and call campaigns supporting growth and retention initiatives, I wanted to use this project to:
* Build on my customer analytics experience by applying another common analytical lens
* Simulate a realistic A/B testing workflow
* Practice a common decision-making framework used in product analytics

## Dataset Description
A/B testing helps businesses identify more effective strategies for acquiring customers, marketing products, increasing reach, and improving conversions.

The [dataset](https://www.kaggle.com/datasets/amirmotefaker/ab-testing-dataset/data) contains daily performance metrics for two marketing campaigns: a **Control Campaign** and **Test Campaign**.

Given the data that's available, we will evaluate whether the Test Campaign improved three metrics: **Click-through Rate (CTR)**, **Add-to-Cart Rate**, and **Purchase Rate**. In additional to assessing statistical signfiicant, we will also consider practical effects and cost-effectiveness.

## Business Recommendation
**The business should adopt the Test Campaign to generate more purchases per impression.** The Test Campaign led to a Purchase Rate of 0.7% versus 0.48% for the Control Campaign, a lift of 47%. The primary mechanism was increasing the Click-through Rate (CTR) by almost 70%. Spend per Purchase was 14% higher in the Test Campaign, but this is likely justified because of the higher Purchase Rate.

However, before full rollout, additional considerations include:
* Comparing revenue, rather than number of purchases alone
* Evaluating total spend constraints for future campaigns
* Investigating opportunities to improve the Add-to-Cart Rate, which was not materially impacted by the experiment; consider UI improvements that encourage customers to add items to their cart

## Analytical Approach
For complete analysis, see [`AB Testing Project.ipynb`](https://github.com/jonah916/AB-Testing-Marketing-Project/blob/main/AB%20Testing%20Project.ipynb). The notebook follows a typical A/B testing workflow:
1. Data Loading & Cleaning
2. Handle Missing Values and Validate Data Quality
3. Exploratory Data Analysis (EDA)
4. Define Success Metrics
5. Hypothesis Testing: Formulate Null and Alternative Hypotheses
6. Statistical Analysis
7. Reporting and Visualization
8. Conclusions and Recommendations

## Results and Conclusions
### Experiment Results and Lift vs. Control
The test campaign resulted in a 70% lift in the CTR and a 47% lift in the Purchase Rate. There was not a significant lift in the Add-to-Cart Rate. 
<p align="center">  <img src="/images/experiment_results.png" width="400" /> <img src="/images/lift_vs_control.png" width="500" /> </p> <p align="center">

### Funnel Analysis: Where did the test campaign make the biggest difference?
There were more impressions in the control campaign by about 1 million, but the test campaign generated about as many purchases. Higher clicks were the main driver of the lift in purchases: despite having fewer impressions, the test campaign generated 25k more clicks.
<p align="center">  <img src="/images/impressions.png" width="400" /> <img src="/images/funnel.png" width="500" /> </p> <p align="center">

### Quality Check: Did the Purchase Rate vary significantly by day of the campaign? By day of the week?
Both the control and test campaigns saw lower purchase rates on the weekend. Purchase rates in the test campaign were much higher on Tuesdays (by almost 100% relative to the control campaign), driven in large part by an outlier on 8/19 that warrants closer inspection. Overall, purchase rates were consistently higher in the test campaign, outperforming the control campaign on 21 out of 29 days.
<p align="center">  <img src="/images/by_day.png" width="2000" /> </p> <p align="center">
<p align="center">  <img src="/images/by_DOW.png" width="500" /> </p> <p align="center">

### Practical Consideration: Cost Effectiveness Comparison
Spend per Purchase was about 14% higher in the test campaign, which is a reasonable increase to generate a 47% lift in Purchase Rate. However, the practical implications of this increase depend on the size of future ad campaigns (which will impact total spend) and the revenue accrued through those campaigns (which will impact total revenue).
<p align="center">  <img src="/images/spend_per_purchase.png" width="500" /> </p> <p align="center">

### Conclusions
The business should adopt the Test Campaign to generate more purchases per impression, but not before conducting a more thorough analysis of expected costs and revenue. The Test Campaign is effective at increasing CTR and Purchase Rate, although the business should consider other interventions to increase the Add-to-Cart Rate. In addition, the business should investigate the optimal timing to implement the Test Campaign, as there is signficant variation in lift by day of the week. Future analyses should feature user segmentation and incorporate profit and revenue metrics.
