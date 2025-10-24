# Oil Well Location Optimization Project

## Project Overview

This project helps **OilyGiant mining company** find the best location for new oil wells by analyzing geological data from three regions and using advanced statistical methods to assess profitability and risk.

## Business Problem

OilyGiant needs to decide which region to develop for oil extraction while minimizing financial risk. The company has:
- Budget of $100 million for developing 200 wells
- Revenue of $4.5 thousand per barrel of oil
- Data from 500 potential well locations in each of 3 regions

## Dataset Description

**Data Sources:** Three regional datasets with geological survey data
- **Size:** 100,000 oil well samples per region
- **Features:** 
  - `f0`, `f1`, `f2`: Geological features (seismic data, soil composition, etc.)
  - `product`: Oil reserves in thousands of barrels (target variable)
  - `id`: Unique well identifier

## Methodology

### 1. Data Exploration & Preprocessing
- Analyzed distributions of oil reserves across regions
- Checked for missing values and duplicates
- Split data into training (75%) and validation (25%) sets

### 2. Machine Learning Model
- **Algorithm:** Linear Regression
- **Purpose:** Predict oil reserves based on geological features
- **Evaluation Metric:** Root Mean Square Error (RMSE)

### 3. Profitability Analysis
- Calculated break-even point: **111.11 thousand barrels per well**
- Developed profit calculation function for top 200 wells
- Compared predicted vs. actual average reserves

### 4. Risk Assessment with Bootstrapping
- **Method:** Bootstrap sampling (1,000 iterations, 500 samples each)
- **Metrics:** 
  - 95% confidence intervals for profit
  - Risk of losses (probability of negative profit)
  - Average expected profit

## Key Findings

| Region | Avg Reserves | RMSE | Expected Profit | Risk of Loss | 95% Confidence Interval |
|--------|-------------|------|----------------|--------------|------------------------|
| 0 | 92.5k barrels | 37.58 | $3.96M | 6.90% | [-$1.11M, $9.10M] |
| 1 | 68.8k barrels | 0.89 | $4.56M | 1.50% | [$0.34M, $8.52M] |
| 2 | 95.0k barrels | 40.03 | $4.04M | 7.60% | [-$1.63M, $9.50M] |

## Recommendation

**Region 1** is the optimal choice because:
- ✅ **Lowest risk:** Only 1.50% chance of losses (well below 2.5% threshold)
- ✅ **Highest expected profit:** $4.56 million average return
- ✅ **Most reliable model:** Lowest RMSE (0.89) indicates accurate predictions
- ✅ **Guaranteed profitability:** 95% confidence interval shows minimum profit of $338k



