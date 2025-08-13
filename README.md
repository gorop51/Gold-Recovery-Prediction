# ⛏️ Gold Recovery Prediction

## 📌 Project Overview

Machine learning model predicting gold recovery coefficient from ore processing data for mining operations optimization.

## 🎯 Objective

Develop a model that accurately predicts gold recovery rates with:
- sMAPE < 10% on test set
- Better performance than baseline model
- Separate predictions for rougher and final processing stages

## 📊 Dataset Description

Three datasets provided:
- **train.csv** - training data with target variables
- **test.csv** - test data without targets
- **full.csv** - complete dataset

**Key Features Structure**: `[stage].[parameter_type].[parameter_name]`
- **Stages**: rougher, primary_cleaner, secondary_cleaner, final
- **Parameters**: gold/silver/lead concentrations, feed size, reagent usage, air/fluid levels

## 🔍 Methodology

### Data Preparation
- Verified recovery efficiency calculations (very low MAE)
- Handled missing values by grouping by date and calculating medians
- Removed features absent in test set
- Standardized features due to different scales

### Modeling Approach
- Implemented custom sMAPE metric
- Tested multiple models with cross-validation:
  - RidgeCV with various alpha values
  - Random Forest Regressor with hyperparameter tuning

## 📈 Results

**Best Model**: Random Forest Regressor with optimized parameters

**Performance Metrics**:
- Rougher stage sMAPE: 6.62%
- Final stage sMAPE: 10.88%
- **Overall sMAPE**: 9.35% (vs. 10.29% for baseline)

The model successfully outperforms the baseline by 0.94%, confirming its adequacy for predicting gold recovery rates.

## 💡 Business Impact

- Predicts recovery rates before full processing
- Identifies unprofitable production runs in advance
- Optimizes reagent usage and processing parameters
- Improves resource efficiency in gold mining operations

ML model predicting gold recovery coefficient with 9.35% sMAPE (vs. 10.29% baseline). Analyzes flotation process parameters and metal concentrations to forecast recovery rates for both rougher (6.62% sMAPE) and final (10.88% sMAPE) processing stages. Enables mining companies to identify unprofitable production runs in advance and optimize resource allocation, improving operational efficiency in gold extraction processes.
