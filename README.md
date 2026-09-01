# Titanic ML Baseline

An end-to-end binary classification project for the [Titanic: Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic) competition.

The project covers data auditing, preprocessing, cross-validation, feature engineering, error analysis, and Kaggle submission.

## Project Goal

Predict whether a passenger survived using demographic and travel information while keeping the experiment reproducible and avoiding validation leakage.

## Approach

- Audited missing values and target distribution.
- Used median imputation and scaling for numerical features.
- Used most-frequent imputation and one-hot encoding for categorical features.
- Trained a Logistic Regression model through a scikit-learn pipeline.
- Evaluated stability with stratified 5-fold cross-validation.
- Engineered `FamilySize` and `IsAlone`.
- Generated and validated a 418-row Kaggle submission.

## Results

| Evaluation | Result |
|---|---:|
| Majority-class holdout accuracy | 0.615 |
| Logistic Regression holdout accuracy | 0.804 |
| Baseline 5-fold CV | 0.797 ± 0.015 |
| Engineered 5-fold CV | 0.802 ± 0.015 |
| Survivor recall | 0.667 |
| Kaggle public accuracy | 0.76794 |
| Best Kaggle public accuracy | 0.77033 |

Family features improved mean cross-validation accuracy by `+0.006`.

The Kaggle public score is approximately `0.034` below the local CV mean. This difference does not by itself prove overfitting, but it shows why both local validation and competition results must be tracked.

Random Forest v2 improved the public score from 0.76794 to 0.77033
(+0.00239). The next milestone is one controlled regularization
experiment evaluated with the same cross-validation folds.

## Error Analysis

On the holdout set, the model produced:

- 23 false negatives: survivors predicted as not surviving.
- 12 false positives: non-survivors predicted as surviving.
- Survivor recall of 0.667.

Accuracy alone therefore does not describe all model weaknesses.

## Repository Structure

```text
data/       data instructions; competition CSV files are excluded from Git
notebooks/  exploratory analysis and model experiments
src/        reusable training code planned for the next milestone
reports/    reports and comparison artifacts
```

Main notebooks:

- [`01_eda.ipynb`](notebooks/01_eda.ipynb) — initial data audit.
- [`02_baseline_model.ipynb`](notebooks/02_baseline_model.ipynb) — validation, feature engineering, error analysis, and submission generation.

## Setup

A compatible Conda environment is provided:

```bash
git clone https://github.com/dermawanw/titanic-ml-baseline.git
cd titanic-ml-baseline
conda env create -f environment.yml
conda activate titanic-ml
jupyter lab
```

Download `train.csv` and `test.csv` from Kaggle, then place them in:

```text
data/raw/
```

Competition data and generated submissions are intentionally excluded from Git.

## Limitations and Next Step

This is a transparent baseline, not an optimized final model. It currently uses one linear classifier without systematic hyperparameter tuning.

The next milestone is to compare a tree-based model using the same cross-validation strategy and submit model v2 to Kaggle.

## License

Code is available under the [MIT License](LICENSE). The dataset remains subject to Kaggle's competition rules.