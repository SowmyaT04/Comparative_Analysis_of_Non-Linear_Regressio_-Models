# Non-Linear Regression Analysis and Model Comparison

**Course Project – MTH686: Non-Linear Regression**
Indian Institute of Technology Kanpur

---

##  Table of Contents

- [Project Overview](#-project-overview)
- [Objectives](#-objectives)
- [Regression Models](#-regression-models)
- [Methodology](#-methodology)
- [Model Performance](#-model-performance)
- [Best Performing Model](#-best-performing-model)
- [Residual Variance Estimates](#-residual-variance-estimates)
- [Residual Normality](#-residual-normality)
- [Confidence Intervals](#-confidence-intervals)
- [Repository Structure](#-repository-structure)
- [Tools & Libraries](#️-tools--libraries)
- [Visualizations](#-visualizations)
- [Key Findings](#-key-findings)
- [Future Improvements](#-future-improvements)
- [References](#-references)

---

##  Project Overview

This project investigates the performance of multiple non-linear regression models by fitting them to a dataset containing **75 observations**. Three different functional forms were estimated using the **Least Squares Estimation (LSE)** approach and compared using statistical goodness-of-fit metrics.

The objective was to determine which model best explains the observed data while validating the underlying assumptions of regression through residual analysis, confidence intervals, and normality testing.

---

##  Objectives

- Estimate model parameters using Least Squares Estimation
- Compare three competing regression models
- Evaluate model performance using statistical criteria
- Estimate the residual variance
- Construct confidence intervals using the Fisher Information Matrix
- Validate model assumptions through residual diagnostics and normality tests
- Visualize fitted curves alongside observed data

---

##  Regression Models

### Model 1 – Double Exponential Model

$$
y(t) = \alpha_0 + \alpha_1 e^{\beta_1 t} + \alpha_2 e^{\beta_2 t} + \epsilon(t)
$$

### Model 2 – Rational Model

$$
y(t) = \frac{\alpha_0 + \alpha_1 t}{\beta_0 + \beta_1 t} + \epsilon(t)
$$

### Model 3 – Fourth-Degree Polynomial

$$
y(t) = \alpha_0 + \alpha_1 t + \alpha_2 t^2 + \alpha_3 t^3 + \alpha_4 t^4 + \epsilon(t)
$$

---

##  Methodology

The project follows the complete non-linear regression workflow:

1. Fit all three models
2. Estimate unknown parameters using Least Squares Estimation
3. Compare model performance using:
   - Residual Sum of Squares (RSS)
   - Coefficient of Determination (R²)
   - Akaike Information Criterion (AIC)
   - Bayesian Information Criterion (BIC)
4. Estimate residual variance
5. Compute 95% confidence intervals using the Fisher Information Matrix
6. Perform residual diagnostics
7. Test residual normality using the Shapiro-Wilk test
8. Compare fitted curves with observed data

---

## Model Performance

| Model | RSS | R² | AIC | BIC |
|-------|------:|------:|------:|------:|
| Double Exponential | 1.59 | 0.9991 | -279.14 | -267.55 |
| Rational | 0.65 | 0.9996 | **-348.68** | -339.41 |
| Polynomial | **0.47** | **0.9997** | -317.08 | **-359.49** |

---

##  Best Performing Model

Among the three models, the **Fourth-Degree Polynomial Model** provided the strongest overall fit, despite the Rational model recording a marginally lower AIC.

Key observations:

- Highest R² (0.9997) and lowest RSS (0.47)
- Lowest estimated residual variance (0.0067)
- Lowest BIC (-359.49), which more heavily penalizes model complexity than AIC — favoring the polynomial once parameter count is accounted for
- Residuals satisfied normality assumptions

---

## Residual Variance Estimates

| Model | Estimated σ² |
|--------|-------------:|
| Double Exponential | 0.0227 |
| Rational | 0.0091 |
| Polynomial | **0.0067** |

---

##  Residual Normality

Residual normality was evaluated using the **Shapiro-Wilk Test**.

| Model | W Statistic | p-value | Conclusion |
|--------|------------:|---------:|-----------|
| Double Exponential | 0.9834 | 0.4310 | Normally Distributed |
| Rational | 0.9774 | 0.1998 | Normally Distributed |
| Polynomial | **0.9912** | **0.8887** | Normally Distributed |

Since all p-values exceeded 0.05, the residuals for each model were consistent with the normality assumption.

---

##  Confidence Intervals

Approximate 95% confidence intervals for all model parameters were computed using the **Fisher Information Matrix**.

The polynomial model produced comparatively more stable parameter estimates than the non-linear exponential and rational models.

---

##  Tools & Libraries

- Python
- NumPy
- SciPy
- Pandas
- Matplotlib
- Statsmodels

---

##  Visualizations

The project includes:

- Observed vs Fitted Curves
- Residual Plots
- Model Comparison
- Diagnostic Plots

---

##  Key Findings

- Successfully estimated parameters for three competing regression models
- Compared models using multiple statistical performance metrics
- Estimated residual variance for each model
- Computed confidence intervals using the Fisher Information Matrix
- Verified regression assumptions through residual diagnostics
- Identified the fourth-degree polynomial as the most suitable model for the dataset

---

## 📖 References

- Course: **MTH686 – Non-Linear Regression Analysis**
- Indian Institute of Technology Kanpur
