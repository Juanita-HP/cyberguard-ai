# CyberGuard AI — Data Cleaning & Preprocessing Report

## 1. Objective

Prepare UNSW-NB15 network traffic data for supervised
Binary Classification of Benign (0) and Malicious (1) traffic.

## 2. Dataset

- Original Training Records: 175,341
- Original Test Records: 82,332
- Original Columns: 45
- Input Features: 42
- Target: `label`

## 3. Data Quality Assessment

- Missing Values: 0
- Duplicate Occurrences (excluding id): 67,601
- Conflicting Feature Groups: 229
- Records in Conflicting Groups: 940
- Infinite Numerical Values: 0
- Negative Numerical Values: 0
- Constant Numerical Features: 0

## 4. Train/Test Overlap

- Test Records with Matching Training Features: 8,541
- Test Overlap: 10.37%
- Matching Labels: 8,017
- Opposite Labels: 296
- Ambiguous Training Labels: 228

These are exact feature-value matches, not necessarily
identical real-world network connections.

The official Test Dataset was not modified.

## 5. Data Cleaning Decisions

- Excluded `id` because it is an identifier.
- Excluded `attack_cat` to avoid potential Target Leakage.
- Retained `label` as the Binary Classification target.
- Retained Duplicate Records pending further evidence.
- Retained Conflicting Labels pending ground-truth review.
- Retained `service = "-"` as a categorical value.
- Retained rare categorical values.
- Did not remove Outliers automatically.
- Did not alter the original CSV files.

## 6. Train/Validation Split

- Method: GroupShuffleSplit
- Random State: 42
- Training Records: 140,145
- Validation Records: 35,196
- Shared Feature Groups: 0

Identical combinations of Input Features are kept
within the same development split.

## 7. Preprocessing

- Numerical Features: 39
- Categorical Features: proto, service, state
- Categorical Encoding: OneHotEncoder
- Unknown Categories: Ignored during transformation
- Numeric Transformation: Passthrough
- Encoded Feature Count: 192

The Preprocessor was fitted only on Training Data.
Validation Data was transformed using the fitted
Preprocessor without fitting again.

## 8. Final Outputs

- X_train_processed: (140145, 192)
- X_val_processed: (35196, 192)
- y_train: (140145,)
- y_val: (35196,)

## 9. Limitations and Evaluation Plan

Duplicate and conflicting records have not been
automatically removed because the available data
does not establish which observations are erroneous.

The official Test Dataset has a known feature overlap
with Training. Final Model Evaluation must explicitly
report this limitation.

Validation is used for model selection.
The official Test Dataset must not be used for
hyperparameter tuning or preprocessing decisions.

## 10. Next Phase

Model Training and Evaluation:
- DummyClassifier baseline
- RandomForestClassifier
- Precision, Recall and F1-score
- Confusion Matrix
- ROC-AUC
- Generalization and error analysis
