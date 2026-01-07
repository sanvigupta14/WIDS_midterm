Problem Formulation 
Given a universe of stocks, identify companies that are likely to outperform the benchmark over the next t years, based on fundamental analysis and financial strength. 

One datapoint = “A company at year t” 
Feature space (what goes into the model) = FINANCIAL RATIOS
Time of prediction = At the end of the financial year, basically, “based on the financial ratios of the company today, will it outperform the benchmark over the next 3 years?” 
Outcome Horizon = 3 years forward return 
Model = Binary (1 outperformed the market, 0 did not outperform the market) 

Are data points dependent on each other (same sector) ? 
Will try to add this feature in an advanced model
Industry data needed 
Sector specific metrics 
Market cap

Transformations: Normalization + Winsorization 
Evaluation Strategy: Rolling time based validation

Week 1 & 2 progress 
Step 1 - The objective of this stage was to prepare a clean, structured dataset and extract variables that can be used to predict long-term equity performance. As a first step, column names were standardized by converting them to lowercase and replacing spaces and special characters with underscores. Missing values were analyzed by computing the percentage of null observations per variable.

Step 2 - Distinguished identifier variables (company name, ISIN, symbol), categorical variables (industry group), and numerical financial variables used for modeling. Box plots on the raw scale revealed that most financial variables, such as market capitalization, net sales, and profits, were highly right-skewed with heavy tails. 

Step 3 - Box plots were regenerated on a logarithmic scale. Log transformation compressed extreme values while preserving the monotonic relationships between variables. Using log-scaled visualizations allowed for better comparison across firms of vastly different sizes. 

Step 4 - Several important financial quantities were reconstructed directly from available line items. A structured set of financial ratios was created:

Profitability:
Gross margin, operating margin, net margin, and EBITDA margin

Risk and Capital Structure:
Interest coverage and EV-to-EBITDA

Valuation:
Price-to-earnings (P/E), firm P/E divided by industry P/E differences 

Size and Liquidity Controls:
Log-transformed market capitalization, trading activity

At this stage, the dataset is fully prepared for constructing the target variable (3-year forward outperformance) and implementing rolling, time-based model validation.
