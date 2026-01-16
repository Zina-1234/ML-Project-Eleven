Predicting Parkinson's Disease Severity Using Voice Data
Team Eleven - 011 | Ironhack Data Analytics | January 2026

Project Description
This project predicts Parkinson's disease severity from voice recordings using machine learning. We trained models on voice features to predict the total_UPDRS score, which measures disease severity (0-176 scale).
Goal: Enable remote, non-invasive monitoring of Parkinson's patients through voice analysis.

Data Source
Dataset: Oxford Parkinson's Telemonitoring Dataset
Source: UCI Machine Learning Repository
Dataset Overview:

5,875 voice recordings
42 patients with Parkinson's disease
16 voice features
6-month monitoring period

Target Variable: total_UPDRS (disease severity score, 0-176)
Reference: Little, M.A., et al. (2007). Exploiting Nonlinear Recurrence and Fractal Scaling Properties for Voice Disorder Detection. BioMed Eng OnLine 6, 23.

Features Used
We used 16 voice measurements grouped into categories:
Jitter (frequency variation): Jitter(%), Jitter(Abs), RAP, PPQ5, DDP
Shimmer (amplitude variation): Shimmer, Shimmer(dB), APQ3, APQ5, APQ11, DDA
Noise ratios: NHR, HNR
Complexity measures: RPDE, DFA, PPE

Machine Learning Techniques
1. Linear Regression (Baseline)
Simple model to establish baseline performance.
Results:

MAE: 2.42
R² Score: 0.90

2. Random Forest (Advanced)
Ensemble model to capture non-linear patterns.
Results:

MAE: 0.13
R² Score: 0.999

3. Cross-Validation
5-Fold Cross-Validation to ensure model reliability.
Results:

Mean R²: 0.909
Standard Deviation: 0.005


Key Findings
- Random Forest significantly outperformed Linear Regression, achieving near-perfect predictions (R² = 0.999)
- Voice features are highly predictive of Parkinson's disease severity
- Non-linear patterns exist in the relationship between voice and disease severity
- Model is reliable, as shown by consistent cross-validation scores
- Voice data should complement, not replace, comprehensive medical diagnosis
