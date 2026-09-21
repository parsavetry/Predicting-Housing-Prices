# Predicting Housing Prices — Kaggle Competition

A statistical modeling project focused on predicting residential housing prices using regression analysis in R. The project placed Top 60 in the Kaggle competition.

## Project Overview

The goal of this competition was to predict house sale prices from property characteristics. I developed and evaluated multiple linear regression models, using exploratory analysis, statistical diagnostics, variable transformations, and model selection to improve predictive performance.

The final approach used a log-transformed response variable and transformed predictors to address nonlinearity, skewness, and heteroscedasticity.

## Results

- 🏆 Top 60 Kaggle placement

- Adjusted R²: 0.757 for the final full model

- Used statistical diagnostics to identify violations of linear regression assumptions

- Improved model fit through log transformations and variable selection

## Methodology

### 1. Exploratory Data Analysis

I initially examined the distributions and relationships between SalePrice and potential predictors, including:

- LotArea

- OverallQual

- TotalBsmtSF

- GrLivArea

- TotRmsAbvGrd

- GarageArea

- OverallCond

Categorical variables such as Neighborhood and LotConfig were also evaluated using ANOVA. Both showed statistically significant relationships with SalePrice.

### 2. Initial Regression Model

An initial multiple linear regression model was fit using the original variables.

The model achieved an R² of 0.298, but diagnostic plots revealed several violations of regression assumptions:

- Nonlinearity

- Non-constant variance

- Strong skewness

- Large residuals and influential observations

These diagnostics motivated transforming the response and predictor variables.

### 3. Variable Transformation

A Box-Cox analysis was used to investigate appropriate transformations. I ultimately applied logarithmic transformations to SalePrice and several continuous predictors.

The transformed model substantially improved fit:

Adjusted R²: 0.740

The diagnostic plots also showed improvements in linearity, normality, and variance stability.

### 4. Model Selection

I used added-variable plots, variance inflation factors (VIF), and exhaustive subset selection to evaluate the contribution of individual predictors.

The final full model achieved:

| Metric | Value |
|---|---:|
| Adjusted R² | 0.757 |
| R² | 0.757 |
| AIC | 11,684.11 |
| BIC | 11,745.79 |

The full model provided the highest adjusted R² and lowest AIC among the candidate models.

### 5. Final Prediction Model

The final Kaggle predictions were generated using a log-linear regression model with:

- log(LotArea)

- OverallQual

- log(TotalBsmtSF + 1)

- log(GrLivArea)

- log(TotRmsAbvGrd)

- log(GarageArea + 1)

Predictions were converted back to the original dollar scale using the exponential transformation before being submitted to Kaggle.

## Tools & Techniques

Language: R

Libraries:

- dplyr

- car

- leaps

Statistical Methods:

- Exploratory data analysis

- Multiple linear regression

- ANOVA

- Box-Cox transformations

- Log transformations

- Regression diagnostics

- Added-variable plots

- Variance inflation factor (VIF) analysis

- Exhaustive subset selection

- AIC / BIC model comparison

- Predictive modeling

## Key Takeaways

This project demonstrated how statistical diagnostics can guide the modeling process rather than relying solely on predictive performance. The initial model showed substantial violations of regression assumptions, leading to transformations and subsequent model refinement. The resulting model achieved a Top 60 Kaggle placement while providing an interpretable statistical framework for housing price prediction.
