# Click-Through Rate (CTR) Prediction Analysis

**Data Science Capstone Project**

## Executive Summary

This project analyzes online advertising data to predict click-through rates (CTR) and identify key factors influencing user engagement with digital advertisements. Using a dataset of 50,000 advertising records, we performed comprehensive exploratory data analysis (EDA) and developed baseline machine learning models to understand user behavior patterns and predict ad click probability.

## Research Question

**What factors most significantly influence the likelihood of a user clicking on an online advertisement, and how accurately can we predict click-through rates using machine learning?**

## Data Sources

- **Dataset**: Online advertising click-through data
- **Size**: 50,000 records with 24 features
- **Target Variable**: Binary click indicator (0 = no click, 1 = click)
- **Key Features**:
  - Temporal: Hour, day of week, time periods
  - Device: Device type, connection type, device model
  - Ad Context: Banner position, site category, app category
  - Anonymous: Categorical features C1, C14-C21

## Methodology

### 1. Exploratory Data Analysis (EDA)
- Data quality assessment and cleaning
- Temporal pattern analysis
- Categorical feature exploration
- Correlation analysis and outlier detection
- Interactive visualizations using Plotly

### 2. Feature Engineering
- Temporal feature extraction (hour, day of week, time periods)
- High-cardinality feature handling
- Label encoding for categorical variables
- Weekend/weekday indicator creation

### 3. Machine Learning Modeling
- **Primary Model**: Random Forest Classifier
- **Comparison Model**: Logistic Regression
- **Evaluation Metric**: ROC-AUC (chosen for class imbalance handling)
- **Data Split**: 80% training, 20% testing with stratification

## Results

### Key EDA Findings

#### Dataset Characteristics
- **Click-Through Rate**: 16.93% (8,467 clicks out of 50,000 impressions)
- **Class Imbalance**: 4.9:1 ratio (no-click to click)
- **Data Quality**: Clean dataset with no missing values or duplicates

#### Temporal Patterns
- Clear hour-of-day effects on click rates
- Day-of-week variations in user engagement
- Time-period categorization shows distinct performance patterns
- Weekend vs weekday behavior differences

#### Device and Context Insights
- Banner position significantly impacts click probability
- Device type influences user engagement patterns
- Site and app categories show varying performance
- Connection type affects user behavior

#### Feature Correlations
- Anonymous categorical features (C1, C14-C21) show varying predictive power
- Temporal features provide meaningful signals
- Device characteristics correlate with click behavior

### Model Performance

| Model | ROC-AUC Score | Accuracy | Precision | Recall | F1-Score |
|-------|---------------|----------|-----------|--------|----------|
| **Random Forest** | **0.6960** | 0.6551 | 0.2728 | 0.6226 | 0.3793 |
| **Logistic Regression** | **0.6323** | 0.5867 | 0.2234 | 0.5818 | 0.3228 |

Best Model: **Random Forest** with 0.6960 ROC-AUC score

### Feature Importance Insights
- **Most predictive features** (Top 5):
  1. C21 (13.88% importance)
  2. C14 (12.72% importance) 
  3. C20 (8.95% importance)
  4. C17 (8.91% importance)
  5. app_category (7.54% importance)

## Next Steps

### Immediate Improvements
1. **Hyperparameter Tuning**: Optimize model parameters using GridSearch/RandomSearch
2. **Advanced Models**: Implement XGBoost, LightGBM, or Neural Networks
3. **Feature Selection**: Apply statistical and ML-based feature selection techniques
4. **Class Imbalance**: Experiment with SMOTE, class weights, or ensemble method

## Project Structure

- **[main.ipynb](./main.ipynb)**: Complete analysis notebook with EDA and modeling
- **[data/50krecords.csv](./data/50krecords.csv)**: Source dataset
- **[README.md](./README.md)**: The project documentation
- **[requirements.txt](./requirements.txt)**: Python package dependencies