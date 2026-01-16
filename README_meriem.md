# ML-Project-Eleven: Predicting Parkinson’s Disease Severity Using Voice Data

## Project overview:
This project builds a **regression model** to predict Parkinson’s disease severity from voice-based acoustic features.

### The problem:
Parkinson disease progression needs continuous monitoring.
Traditionnal clinical assessments are infrequent and resource-intensive.

### Objective:
Predict UPDRS (Unified Parkinson's Disease Rating Scale) severity score (0-176) from vocal measurements using machine learning.

### Why voice analysis?
- Non invasive monitoring
- Can be done remotely
- Early detection of symptom changes

### Impact
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
- **MAE:** 2.42
- **MSE:** 10.69
- **RMSE:** 3.27
- **R²:** 0.90

**Results:**
Our model predicts that a patient with minimal voice pathology would have a relatively low total UPDRS score of approximately 8.78.

### Hyperparameter Tuning and Model Optimization

#### Linear Regression 
The regression intercept indicates a baseline Total UPDRS score in the mild symptom range, suggesting that minimal voice impairment is associated with low overall Parkinson’s severity.


#### Cross-Validation (Model K Fold)

**Results:**

R2 scores for each fold:
0.91381079
0.90167049
0.91176976
0.91351376
0.90381669

**Mean R2:** 0.909
**Standard deviation:** 0.005

**Interpretation:**
The model performs consistently well across different subsets of patients.


#### Random Forest 

**Results:**
MAE ≈ 0.13
R² ≈ 0.999

**Interpretation:**
Our model performed extremely well.
We achieved:
Very low error
R² score close to 1

The error is clinically negligible and the model almost perfectly reproduces the real Total UPDRS values.

-----

## Conclusion

### Key findings

**Chalenges:**
- Complex, multifactorial disease → voice explains only part
- Small number of patients (42) → limited variability.

**Learnings:**
- Simple models are a good baseline
- Ensemble models can improve performance.

Voice data can help predict Parkinson’s severity but is not sufficient alone.
Random Forest improved predictions over Linear Regression, confirming non-linear patterns exist in the data.


### Real-World Application and Impact

#### Practical Applications

- Accessible pre-screening tool
- Telemedicine / remote diagnosis
- Disease progression monitoring

#### Potential Impact

- Early detection enables better treatment
- Cost reduction in healthcare
- Increased accessibility for patients

#### Ethical Considerations & Limitations

Limited dataset size (197 samples)
Requires clinical validation
Complements, not replaces, medical diagnosis

### Future Work and Improvements

#### Areas for Expansion

- Collect larger, more diverse dataset
- Experiment with Deep Learning models (Neural Networks)
- Integrate additional biomarkers (gait analysis, handwriting)

#### Potential Improvements

- Mobile application for regular screening
- Longitudinal patient tracking system
- Multi-modal diagnostic approach




