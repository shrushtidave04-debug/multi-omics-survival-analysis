# Multi-Omics Survival Analysis: A Comparative Study

## Overview

This project compares different statistical and machine learning models
for survival analysis using multi-omics data from kidney cancer patients.

The main objective is to identify which model provides the best performance
for predicting patient survival and to examine whether combining multi-omics
data improves performance compared with clinical data alone.

## Dataset

The dataset was obtained from the TCGA-KIRC (Kidney Renal Clear Cell
Carcinoma) dataset.

The analysis includes:

- Clinical data
- mRNA gene expression
- Copy Number Variation (CNV)
- Mutation data
- miRNA data

The datasets were integrated using a common patient/sample ID.

## Data Preprocessing

The preprocessing steps included:

- Encoding categorical clinical variables
- Converting tumor stage into numerical levels
- Handling missing values
- Removing invalid survival-time observations
- Merging datasets using common sample IDs

## Feature Grouping

The variables were organized into meaningful groups:

- Clinical
- mRNA
- CNV
- Mutation
- miRNA

This grouping was used to account for the natural structure of multi-omics
data during model building.

## Models Compared

The following models were evaluated:

- Kaplan-Meier
- Cox Proportional Hazards Model
- Lasso Cox
- CoxBoost
- Random Forest
- Block Forest

## Model Evaluation

Models were compared using the **Concordance Index (C-index)**.

Five-fold cross-validation was used to obtain more reliable and stable
performance estimates.

## Results

| Model | Mean C-index |
|-------|--------------|
| Block Forest | 0.825 |
| Clinical Cox | 0.809 |
| Lasso Cox | 0.780 |
| Random Forest | 0.696 |
| Kaplan-Meier / CoxBoost | 0.500 |

Block Forest achieved the highest mean C-index of **0.825**, making it the
best-performing model in this analysis.

## Conclusion

The results showed that models which consider the group structure of
multi-omics data performed better than simpler approaches.

However, the improvement from using multi-omics data over clinical data
alone was relatively small. This highlights the importance of comparing
model performance as well as considering the additional complexity of
multi-omics data.

## Technologies

- R
- Survival Analysis
- Statistical Modelling
- Machine Learning
- Cross-Validation
- Data Preprocessing
- Data Visualization
