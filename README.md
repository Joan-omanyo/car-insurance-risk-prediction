# Car Insurance Risk Prediction


### Business Understanding

ABC Insurance Company - A leading auto insurance provider facing profitability challenges due to inaccurate risk assessment in their pricing model.

We use the `train.csv` dataset from Kaggle, loaded via pandas into the `car_insurance_claim_data` DataFrame. The dataset dimensions are 58,592 rows × 44 columns. Data quality analysis showed zero null values, requiring no imputation. Preprocessing steps included feature renaming and elimination of non-essential columns.

https://www.kaggle.com/datasets/ifteshanajnin/carinsuranceclaimprediction-classification/code

#### Business Problem

The company currently uses broad demographic categories for insurance pricing, leading to two critical issues:

1. Current Challenges:

a) Financial Losses: High-risk customers are undercharged, resulting in claim payouts that exceed their premium contributions.

b) Customer Attrition: Low-risk customers are overcharged and leave for competitors offering better rates.

c) Inefficient Resource Allocation: Marketing and retention efforts are not targeted effectively.

2. The Core Issue:

Only 6.4% of customers file claims, but these claims account for the majority of insurance payouts.

![Claim Distribution](outputs/plots/Claim%20Distribution.PNG)

The current "one-size-fits-all" pricing model fails to distinguish between truly high-risk and low-risk customers.

This leads to cross-subsidization where safe drivers effectively pay for risky drivers.

We develop a machine learning classification model that accurately predicts the likelihood of a customer filing an insurance claim, therefore enabling:

1. Risk-Based Pricing: Implement personalized premium calculations based on individual risk profiles.

2. Customer Segmentation: Identify and categorize customers into distinct risk tiers.

3. Profitability Optimization: Reduce losses from high-risk customers while retaining low-risk customers.

### Data Preparation & Modeling Approach
We transformed raw insurance data into a predictive format, handling categorical variables and addressing severe class imbalance (93.6% no claims vs 6.4% claims). Our methodology included stratified train-test splits and comprehensive model evaluation beyond simple accuracy metrics.

Key Findings & Business Impact:

#### The Accuracy Paradox

Baseline Model: 93.6% accuracy (always predicts "no claim") but identifies 0% of actual claims.

Predictive Models: Same 93.6% accuracy but can identify risky customers.

Insight: Traditional accuracy metrics mask true business value in imbalanced datasets.

#### Model Performance

Random Forest (Best): AUC = 0.652 - Meaningful risk ranking capability.

Logistic Regression: AUC = 0.590 - Limited predictive power.

Challenge: Severe 6.4% class imbalance remains the primary obstacle.

#### Critical Business Realization
The models' tendency to default to "no claim" predictions mirrors the current insurance industry problem: safe drivers subsidize risky ones due to inadequate risk differentiation. Our analysis demonstrates why true risk-based pricing is essential but challenging to implement.

#### Current Limitations

Risk segmentation identified 0 high-risk customers despite 6.4% actual claim rate.

Theoretical pricing strategies (30-50% surcharges) cannot yet be implemented.

Model shows promise but needs refinement for production use.

#### Path Forward
This project establishes a foundation for insurance risk prediction while highlighting the critical need for advanced techniques to handle severe class imbalance and enable genuine risk-based pricing strategies.

The project demonstrates that while machine learning can identify risk patterns, the insurance industry's inherent data challenges require sophisticated approaches to move beyond one-size-fits-all pricing.

### Visualization

![Risk Prediction](outputs/plots/Visualization.PNG.PNG)

Observation:

While accuracy scores appear identical across models, the risk segmentation and claims identification capabilities reveal the true business value. Our predictive models can actually identify risky customers and enable targeted interventions, unlike the baseline that provides no actionable insights despite its high accuracy score.

This analysis proves why simple accuracy metrics are insufficient for imbalanced business problems and highlights the importance of evaluating models based on their ability to provide actionable risk intelligence.
### Conclusion

The project demonstrates that while traditional accuracy metrics can be misleading, advanced predictive models provide actionable business intelligence. Implementing the Random Forest model enables transformation from reactive claims management to proactive risk optimization.

Next Step: Pilot implementation with 20% of portfolio to validate business impact before full deployment.



