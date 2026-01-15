# ML-Project-Eleven: Predicting Parkinson’s Disease Severity Using Voice Data

## Project overview:
This project builds a **regression model** to predict Parkinson’s disease severity from voice-based acoustic features.

## The problem:
Parkinson disease progression needs continuous monitoring.
Traditionnal clinical assessments are infrequent and resource-intensive.

## Objective:
Predict UPDRS (Unified Parkinson's Disease Rating Scale) severity score (0-176) from vocal measurements using machine learning.

## Why voice analysis?
- Non invasive monitoring
- Can be done remotely
- Early detection of symptom changes

## Impact
Early diagnosis, non-invasive, non-invasive and accessible

-----

## Dataset

**Source** 
[Oxford Parkinson's Telemonitoring Dataset](https://archive.ics.uci.edu/ml/datasets/Parkinsons+Telemonitoring)

### Dataset Characteristics
- **5,875 voice recordings**
- **42 patients** with Parkinson's disease
- **~200 recordings per patient** (longitudinal data)
- **6-month trial** period

### Target Variable
- total_UPDRS: Overall disease severity score (range: 0-176)
  - 0 = Perfectly healthy
  - 176 = Total disability

### Features
- **Voice measurements** (16 acoustic features):
  - Jitter (frequency perturbation)
  - Shimmer (amplitude perturbation)
  - Harmonic measures (NHR, HNR)
  - Nonlinear dynamics (RPDE, DFA, PPE)

### Sex Distribution:
- Male: 68.2%
- Female: 31.8%

-----

## Methodology

### Data Preparation
- Loaded and inspected the dataset
- Checked for missing values (none found)
- Removed identifiers (subject#)
- Performed exploratory data analysis (EDA)
- Created correlation heatmaps to understand feature relationships

### Handling Data Leakage
To avoid data leakage caused by multiple recordings per patient, the dataset was split at the subject level using GroupShuffleSplit

### Feature Engineering and Selection
- Used all 16 voice features
- Applied **correlation analysis** to understand feature relationships
- Standardized features using StandardScaler

### Model Building

#### 1. Model Used: Linear Regression
Baseline model to establish initial performance benchmarks, indicating that voice features contain predictive information about disease severity.
- Simple and interpretable
- Good starting point
- Fast training
- Establishes baseline

 #### 2. Random forest regression
- Ensemble method: combines multiple decision trees
- Handles non-linear relationships better than linear models
- Feature importance: can identify which voice features matter most
- No assumptions about data distribution

### Model validation: Cross-validation 
To ensure robust performance evaluation.

- More reliable than single train-test split
- Uses all data for both training and validation
- Reduces variance in performance estimates
- Detects overfitting by comparing train vs. validation scores

### Evaluation Metrics
- **MAE (Mean Absolute Error):** Average prediction error in UPDRS points
- **R² Score:** Proportion of variance explained by the model

-----

## Results

### Model performance

#### Training set performance:
- **MAE:** ###
- **MSE:** ###
- **RMSE:** ###
- **R²:** ###


#### Test set performance:
- **MAE:** ###
- **R²:** ###

### Key findings:
Catter plot showing correlation between actual and predicted severity scores. 

**MAE interpretation:**
On average, predictions are within 8.27 points of actual UPDRS.
Given the 0-176 scale, this represents ~4.7% error - a reasonable baseline performance.

**R² interpretation:**

Model explains 7.9% of variance in severity.
Low R² indicates high disease complexity - many factors beyond voice affect severity

