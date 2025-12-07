# Project Summary (Short Overview)
This project compares Facebook and Instagram ad performance using blended descriptive, diagnostic, and predictive analytics.
The dataset contains clicks, conversions, CPC, CTR, CVR, and impressions from February to October.
Power BI was used for descriptive insights, while Python was used for statistical diagnostis and regression modeling. 
The goal was to identify which platform performs better and predict expected conversions from future clicks. 

# Business Problem 
The business ran ads on both Facebook and Instagram but does not know which platform gave better efficiency. 
This project answers:
1. Which platform converts better?
2. Which platform has lower CPC?
3. Does higher clicks lead to higher conversions?
4. Can we predict conversions using clicks?

# Dataset Description
Include:
* FB_IG_AD_Data
* 273 rows
* 19 columns
* Key columns: Date, Month, FB_Campaign, FB_Ad_Clicks, FB_Ad_CVR, IG_Campaign, IG_Ad_Clicks, IG_Ad_CVR.

# Tools Used 
* Power BI for Descriptive analytics and dashboard.
* Python (Pandas, Statsmodels, Matplotlib).
* Excel for data storage in desktop.

# Descriptive Analysis
1. Instagram Cicks vs Conversion rate Over Time
Instagram's clicks starerted low in February, rose slightly in March, and continued a wave-like pattern (up-down-up-down) across the months.
Despite fluctuations, overall click volume showed gradual improvement toward the later months.
In contrast, Instagram's conversion rate (CVR) was steadily increasing, reaching its hghest point in July, before declining again.
This indicates that while user engagement fluctuated, Instagram briefly achieved stronger conversion efficiency mid-year.

Scorecard Insight:
* Avg CTR: 0.08
* Avg CVR: 0.03
* Avg CPC: 139.07
Instagram required significantly higher cost to acquire clicks.

2. Facebook Clicks vs Converion Rate Over Time
Facebook's click pattern remained mostly flat and stable throughout the year, with a strong spike in October, indicating an increase in reach or campaign intensity.
Facebook's conversion rate peaked in May, making it the strongest conversion month for the platform.
Even after the peak, Facebook maintained a higher CVR compared to Instagram in every month.
Scorecard Insight:
* Avg CTR: 0.08
* Avg CTR: 0.04
* Avg CPC: 93.92
Facebook delivered conversions more cost-efficiently.

3. Facebook vs Instagram CPC Over Time
The CPC comparison clearly shows that:
Instagram's CPC is cosnsitently higher than Facebook's every month.
This confirms that Instagram is the more expensive platform for generating clicks.
Facebook maintains a lower and more predictable CPC pattern, making it more cost-effective option for ad delivery across the period.

4. Facebook vs Instagram CVR Over Time
Facebook's CVR remains consistently higher than Instagram throughtout all months.
Facebook shows a strong peak in May, while Instagram peaks later in July but still stays below Facebook.
Overall, Facebook consistently outperforms Instagram in conversions efficiency.

# Diagnostic Analysis 
* Objective: Understand why Facebook and Instagram ads performed differently.

1. Variability and Outliers
* Facebook CVR: mean 0.04, high CV (0.75), right-skewed, extreme high campaigns.
* Instagram CVR: mean 0.02, CV 1.0, heavily right-skewed, more low-conversion days.
* CTR shows similar high variability: histograms hide extreme outliers.

2. Daysof Week Insghts
* Best days: Thursday (both platforms), Monday (Facebook).
* Worst/volatile: Tuesday (Facebook), Monday/Friday/Saturday (Instagram).
* Ads perform more consistently on stable days: some days extreme outliers.

3. Percentile Analysis
Category  Facebook  Instagram
Low         98        130
Medium      94         87
High        81         56

* Instagram has more low-performing days: Facebook achieves more high conversions.

4. CTR vs CVR
* Facebook: Positive correlation (0.73): higher CTR lead to higher CVR.
* Instagram: Weak correlation (0.61): CTR does not predict CVR reliably.

# Predictive Analysis 
* Objective: Predict which platform (Facebook or Instagram) will yield more conversions if current ad strategies continue.
1. Hypothesis
* Null (H0): No significant difference in conversions between Facebook and Instagram.
* Alternative (H1): Facebook conversions are significantly higher than Instagram.
2. Normality Check
* Normality Check
- Facebook p-value = 0.934: it is approximately normal.
- Instagram p-value = 0.927: approximately normal
- Conclusion: Data is suitable for parametric test.

3. Variance Check
* Levene's test: p-value < 0.05: unequal variances.
* Conclusion: Use Welch's t-test instead of standard t-test.

4. Welch t-test
* t-statistic = 6.7969
* p-value ~ 3 * 10 -11
* Interpretation: Statistically significant difference between platforms: the result is not due to chance.

5. Conclusion
* Facebook CVR > Instagram CVR
* Facebook is more effective at converting clicks into actions (conversions).
* The performance gap is statistically reliable.
* Predictive implicaition: If current campaigns continue unchanged, Facebook will consistently generate higher conversions than Instagram.

# Predictive Analysis: Facebook Ad Conversions (Regression Analysis)
* Objective: Predict Facebook ad conversions based on the number of clicks.
Method:
- Simple linear regression using
  Statsmodels: Conversions ~ Clicks
- Model metrics:
  Adjusted R2 = 0.762: strong predictive power.
  Intercept = -8.9277
  Slope = 0.8182: for every additional click, conversions increase by ~0.18.
  F-statistic p-value < 0.01: statistically significant

* Regression Equation:
  Predicted Conversions = -0.89277 + 0.8182 * Clicks
* Interpretation:
- The positive slope indicates that higher clicks lead to more conversions.
- The model explains ~0.76% of hte variation in Facebook conversions.
- Statistically significant and practically meaningful: it can be used to predict expected conversions for future campaigns.

* Visualization:
- Predicted conversions were plotted alongside actual data for 300 - 700 clicks, showing both observed and forecasted trends.
- The chart confirms the model reliably predicts conversion trends beyond the observed data range.

# Assumption-Based Facebook ROI Analysis & Recommendations
1. ROI & Profitabilty (Facebook Ads)
- Total clicks: 67,044
- Conversions (products sold): 604
- Revenue per sale: $5,000
- Calculated revenue: $3,020,000
- Profit: $2,520,000
- ROI: 504%: for every $1 spent, $5.04 profit earned.

* Interpretation:
- The Facebook campaign is highly profitable, generating over 5X return on ad spend.
- Even with conservative conversions assumptions, Facebook delivers strong financial outcomes.

# Business Recommendations
1. Reallocate budget toward Facebook
- Move 15-30% of Instagram ad budget to Facebook to leverage higher CVR and ROI.
- Monitor total conversions and CPA after reallocation.
2. Optimize Instagram spending
- Focus on high-potential audineces with strong engagement.
- Update ad creatives: Instagram favors flashy visuals, images and videos.
3. Conversion Rate Optimization (CRO) & A/B Testing
- Test ad elements across both platforms: CTA placement, button color and headline wording.
- Run cross-platform A/B tests to identify highest-converting combinations.
4. Customer Behavior Analysis
- Conduct post-click funnel analysis using Google Analytics.
- Integrate CRM insights to optimize audience targeting and retention.
5. Content Strategy
- Prioritize short-form content and reusuable carousel ads
- Leverage best-performing ad formats across platforms.

  
  
- 





