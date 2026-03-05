# Multicollinearity in Regression — Linear vs. Ridge Regression

This project was part of the Statistical Inference Class at the FCUP Porto.

An analysis of how multicollinearity affects linear regression models 
and how Ridge Regression can address it. Applied to a diabetes 
progression dataset containing correlated explanatory variables, the 
study demonstrates the practical consequences of multicollinearity on 
coefficient stability and model interpretability, and evaluates Ridge 
Regression as a remediation strategy.

## Background

Multicollinearity — the near-linear association between two or more 
explanatory variables — causes a range of problems in regression 
models:
- Unstable and unreliable parameter estimates
- High variance of coefficients
- Reduced informational value of individual coefficients
- Poor model predictions

Since regression models are frequently favoured for their 
transparency, addressing multicollinearity is essential for producing 
interpretable and reliable results.

## Project structure

### 1 — Multicollinearity diagnostics
Detection and quantification of multicollinearity using:

| Diagnostic | Purpose |
|------------|---------|
| Pearson correlation matrix | Pairwise linear associations between predictors |
| Variance Inflation Factor (VIF) | Degree to which each predictor is explained by others |
| Tolerance | Inverse of VIF; flags redundant predictors |
| Eigenvalues | Identification of near-singular dimensions |
| Condition index | Overall severity of multicollinearity |

### 2 — OLS Linear Regression
- Ordinary Least Squares regression applied to the diabetes 
  progression dataset
- Moderate explanatory power observed, but high standard errors 
  on correlated coefficients confirm the destabilising effect of 
  multicollinearity
- Coefficient interpretation is unreliable under these conditions

### 3 — Ridge Regression
- Ridge Regression applied with regularisation parameter k 
  determined via Generalised Cross-Validation (GCV)
- Correlated variables — particularly blood serum measurements — 
  show reduced and stabilised coefficients
- Overall predictive performance (R² and MSE) does not change 
  significantly, but coefficient estimates become reliable and 
  interpretable
- Demonstrates that Ridge Regression effectively trades a small 
  amount of bias for a substantial reduction in variance

## Key findings

- Strong multicollinearity confirmed in the dataset across all 
  diagnostics
- OLS regression produces unstable coefficients despite moderate R²
- Ridge Regression stabilises coefficient estimates without 
  sacrificing predictive power
- Ridge Regression is an effective and interpretable solution to 
  multicollinearity in regression models

## Dataset

The publicly available diabetes progression dataset is used 
(originally from Efron et al., 2004), containing 10 physiological 
baseline measurements as predictors and a quantitative measure of 
diabetes progression one year after baseline as the target variable.

## Repository structure

| File | Contents |
|------|----------|
| `Statistical Inference Final Report.pdf` | Paper with the full analysis: diagnostics, OLS, Ridge Regression |
| `Diabetes_Regression_Analysis.ipynb` | Notebook with the computations (analysis and explanation are provided in the paper) |
| `diabetes.tab.txt` | Data |
