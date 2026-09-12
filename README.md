# AI201X Projects

Course project artifacts for AI201X. The repository contains KNIME workflows,
model outputs, datasets, evaluation documents, and Kaggle submission files.

## Projects

### 1. Titanic survival prediction

The Titanic project compares several classification approaches in KNIME,
including K-nearest neighbors, logistic regression, random forest, and support
vector machines.

- `Team-Project1/Titanic_Survival_KNIME.knwf`: KNIME workflow
- `Team-Project1/KNIME-workflow.png`: workflow overview
- `Team-Project1/kaggle_submission.png`: Kaggle submission result
- `TITANIC_submission.csv`: prediction file for Kaggle (417 passengers)

### 2. House price regression

The house-price project evaluates regression models after missing-value
handling, one-hot encoding, feature creation, and data transformation. The
engineered features described in the report include house age, total area, and
total bathrooms.

| Model | RMSE | MAE | R-squared |
| --- | ---: | ---: | ---: |
| Linear Regression | 63,115 | 51,407 | 0.370 |
| Random Forest | **27,892** | **17,267** | **0.877** |
| Gradient Boosted Trees | 28,138 | 17,671 | 0.875 |
| XGBoost | 31,145 | 18,953 | 0.846 |

- `Team-Project2/KNIME Workflow for House Price Regressions.knwf`: KNIME workflow
- `Team-Project2/KNIME WORKFLOW.pdf`: project presentation and results
- `Team-Project2/impact of feature engineering.pdf`: before/after comparison
- `Team-Project2/submission.csv`: Kaggle prediction file (1,459 houses)

### 3. Telco churn and customer feedback

The final-project directory contains prepared telco-churn data, generated or
processed customer-feedback fields, and a serialized model artifact.

- `Final/dataset/telco_churn_with_all_feedback.csv`: source data enriched with
  prompt and feedback columns
- `Final/dataset/telco_prep.csv`: prepared feedback dataset
- `Final/dataset/telco_noisy_feedback_prep.csv`: prepared dataset with feedback
  availability and sentiment features
- `Final/dataset/model_with_feedback.pkl`: serialized model artifact

> [!CAUTION]
> Python pickle files can execute code when loaded. Only open
> `model_with_feedback.pkl` if you trust this repository and the file's origin.

## Opening the workflows

1. Install [KNIME Analytics Platform](https://www.knime.com/downloads).
2. In KNIME, select **File > Import KNIME Workflow**.
3. Choose one of the `.knwf` files in this repository.
4. Review file-reader paths and reconnect the expected source data if KNIME
   reports a missing local file.

The workflows were created with KNIME 5.x. A newer compatible KNIME release may
ask to install missing extensions when the workflow is opened.

## Repository notes

- Video and PowerPoint files are intentionally excluded from version control.
- Finder metadata and temporary Office lock files are also excluded.
- The included CSV files contain outputs or prepared data; the original Kaggle
  training/test datasets are not included unless explicitly listed above.
- Model metrics are transcribed from the included project reports and may differ
  if the workflows are rerun with different data splits or settings.

## Reproducibility

The KNIME workflows are the executable source for the Titanic and house-price
projects. Before running them, inspect each File Reader node and replace any
machine-specific path with the location of your local Kaggle dataset. Keep the
same train/test split and random seed recorded in the workflow when comparing
results with the metrics above.

The final telco-churn directory currently contains prepared data and a serialized
model, but not the original training script. Treat it as a results archive rather
than a fully reproducible experiment. Do not load the pickle from an untrusted
copy of the repository.
