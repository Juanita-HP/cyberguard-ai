# CyberGuard AI — Technical Requirements

## 3.1 Functional Requirements:
### Project Objective

Develop a beginner-friendly Machine Learning pipeline that analyzes historical network traffic data and classifies records as either Benign or Malicious using Binary Classification.

### Classification Scope

- **Version 1.0:** Binary Classification (Benign vs. Malicious).
- **Version 2.0:** Multiclass Classification (future enhancement to identify specific attack categories).

Version 1.0 will focus exclusively on Binary Classification to establish a solid, reproducible Machine Learning baseline.

### Functional Requirements

- **FR-01 — Data Import:** The system shall import historical network traffic data from a supported dataset.
- **FR-02 — Data Inspection:** The system shall inspect dataset structure, features, and labels.
- **FR-03 — Data Preprocessing:** The system shall clean and prepare data for analysis and Machine Learning.
- **FR-04 — Exploratory Data Analysis:** The system shall perform EDA to identify patterns and characteristics of network traffic.
- **FR-05 — Data Visualization:** The system shall generate visualizations to communicate traffic distributions and analytical findings.

- **FR-06 — Feature Preparation:** The system shall prepare input features and binary target labels for Machine Learning.
- **FR-07 — Model Training:** The system shall train a binary classification model using historical network traffic data.
- **FR-08 — Prediction:** The system shall predict whether network traffic records are Benign or Malicious.
- **FR-09 — Model Evaluation:** The system shall evaluate classification performance using Precision, Recall, F1-score, and a Confusion Matrix.
- **FR-10 — Results Documentation:** The system shall document model performance, analytical findings, and limitations.

- ### Project Boundaries

CyberGuard AI Version 1.0 is an educational, offline Data Science and Machine Learning project.

**Out of Scope:**
- Real-time network traffic monitoring.
- Production-level Intrusion Detection Systems (IDS).
- Automated cybersecurity incident response.
- Live network traffic collection.
- Multiclass attack classification (reserved for Version 2.0).

## 3.2 Non-Functional Requirements

Non-Functional Requirements (NFRs) define the quality standards, technical characteristics, and operational constraints of CyberGuard AI Version 1.0.

### Reproducibility

- **NFR-01 — Reproducibility:** The project shall provide documented dependencies, consistent random seeds, and clear execution instructions to enable reproducible results.

### Performance

- **NFR-02 — Execution Performance:** The data processing and Machine Learning workflow should run on a standard personal computer without requiring dedicated GPU hardware or cloud infrastructure.
- **NFR-03 — Resource Efficiency:** The project should use memory and computational resources efficiently, considering the size of the selected dataset.

### Maintainability

- **NFR-04 — Code Readability:** Python code shall use meaningful variable names, clear organization, and explanatory comments where necessary.
- **NFR-05 — Modularity:** Data preprocessing, model training, and evaluation should be organized into logically separated steps to facilitate future improvements.

### Usability

- **NFR-06 — Documentation:** The repository shall include a README with the project objective, setup instructions, dependencies, and execution steps.
- **NFR-07 — Interpretability:** Results shall be presented using understandable metrics, tables, and visualizations suitable for technical review.

### Reliability

- **NFR-08 — Data Validation:** The workflow shall check for missing values, duplicate records, and invalid data types before model training.
- **NFR-09 — Error Handling:** The workflow should identify and clearly report common data-loading and preprocessing errors.

### Security and Privacy

- **NFR-10 — Data Privacy:** The project shall use publicly available or appropriately authorized datasets and shall not expose personal, confidential, or proprietary network information.
- **NFR-11 — Secure Development:** The repository shall not contain passwords, API keys, or other sensitive credentials.

### Compatibility

- **NFR-12 — Development Environment:** The project shall use Python and widely supported Data Science libraries, including pandas, NumPy, scikit-learn, and visualization tools.
- **NFR-13 — Execution Compatibility:** The project shall be executable through Jupyter Notebook or a compatible Python development environment such as VS Code.

### Version Control

- **NFR-14 — Version Control:** Project files, documentation, and source code shall be maintained in GitHub with descriptive Commit messages.

### Project Scope

- **NFR-15 — Educational Scope:** CyberGuard AI Version 1.0 is intended for offline research, learning, and portfolio demonstration, not production cybersecurity operations.

### Verification Criteria

The Non-Functional Requirements will be reviewed during development and final project validation. Compliance will be assessed through successful environment setup, reproducible execution, code review, documentation review, and examination of the project's outputs.

## 3.3 Inputs and Outputs

### Overview

CyberGuard AI Version 1.0 is an offline Machine Learning project that processes historical network traffic records and predicts whether each record is Benign or Malicious.

### Inputs

**IN-01 — Historical Network Traffic Dataset**
- Source: A publicly available or appropriately authorized cybersecurity dataset.
- Format: CSV or another format supported by Python and pandas.
- Content: Historical network traffic records with relevant attributes and classification labels.
- Dataset selection: To be finalized during the data acquisition phase.

**IN-02 — Input Features**
- Numerical and/or categorical attributes describing network traffic.
- Exact feature names and data types will depend on the selected dataset.
- Features will be inspected, cleaned, and transformed as needed.
- The target label and any columns that cause data leakage must be excluded from model inputs.

**IN-03 — Target Labels**
- Binary classification target with two classes: Benign and Malicious.
- Original dataset labels will be mapped to these classes where appropriate.
- Label mapping rules will be documented before model training.

**IN-04 — Model Configuration**
- Model algorithm: RandomForestClassifier as the initial baseline.
- Training configuration: Reproducible random seed and documented hyperparameters.
- Dataset split: Separate training and testing subsets.
- Preprocessing decisions will be based on the training data to prevent data leakage.

### Processing Workflow

1. Load the selected dataset.
2. Inspect its structure, features, labels, and data quality.
3. Clean and preprocess the data.
4. Perform Exploratory Data Analysis (EDA).
5. Prepare features and binary target labels.
6. Split the dataset into training and testing subsets.
7. Train a baseline Machine Learning model.
8. Generate predictions on the test subset.
9. Evaluate performance and interpret the results.
10. Document findings, limitations, and recommendations.

### Outputs

**OUT-01 — Cleaned Dataset**
- A validated and prepared dataset suitable for analysis and model development.
- Any saved intermediate files will be documented.

**OUT-02 — Exploratory Data Analysis**
- Descriptive statistics and summaries of network traffic.
- Analysis of class distributions, missing values, and relevant features.

**OUT-03 — Data Visualizations**
- Charts illustrating traffic characteristics and class distributions.
- Visualizations supporting interpretation of analytical findings.

**OUT-04 — Trained Baseline Model**
- A trained RandomForestClassifier capable of predicting Benign or Malicious labels.
- Model configuration and training methodology documented.

**OUT-05 — Classification Predictions**
- Predicted binary labels for previously unseen test records.
- Prediction probabilities where supported and appropriate.

**OUT-06 — Model Evaluation**
- Confusion Matrix.
- Precision, Recall, and F1-score.
- ROC-AUC where appropriate.
- Interpretation of errors, including False Positives and False Negatives.

**OUT-07 — Reproducible Jupyter Notebook**
- Python code covering data preparation, EDA, model training, and evaluation.
- Clear Markdown explanations of the methodology and results.

**OUT-08 — Project Documentation**
- GitHub README with project overview and execution instructions.
- Technical Requirements documentation.
- Summary of findings, limitations, and potential improvements.

**OUT-09 — Portfolio Presentation**
- A short presentation explaining the business scenario, methodology, results, and lessons learned.
- All scenarios and organizational references must be clearly identified as fictional or simulated.

### Input and Output Constraints

- The project will operate on historical data, not live network traffic.
- No real-time alerts or automated incident response will be generated.
- Exact dataset columns, file sizes, and model performance targets will be finalized after dataset selection.
- Outputs are intended for educational analysis and portfolio demonstration, not operational security decisions.

## 3.4 Classification Question and Success Metrics

### Classification Question

Can a supervised Machine Learning model accurately distinguish between Benign and Malicious network traffic using historical network traffic features?

### Machine Learning Problem Definition

- **Problem Type:** Supervised Learning.
- **Task:** Binary Classification.
- **Input (X):** Network traffic features extracted from the selected historical dataset.
- **Target (y):** Binary label indicating Benign (0) or Malicious (1).
- **Baseline Algorithm:** RandomForestClassifier.
- **Unit of Prediction:** One network traffic record.
- **Operating Environment:** Offline, educational analysis.

### Model Evaluation Strategy

The dataset will be divided into training and testing subsets using a reproducible random seed. Stratified splitting will be used where appropriate to preserve class proportions.

Preprocessing operations that learn from data must be fitted using training data only to avoid Data Leakage.

The test subset will remain separate from model training and hyperparameter tuning.

### Evaluation Metrics

**MET-01 — Precision**
- Measures the proportion of predicted Malicious records that are actually Malicious.
- Helps assess the frequency of False Positives.

**MET-02 — Recall**
- Measures the proportion of actual Malicious records correctly detected.
- Helps assess the frequency of False Negatives.
- Recall for the Malicious class will be a primary evaluation priority.

**MET-03 — F1-score**
- Combines Precision and Recall into a single metric.
- Useful when the dataset has imbalanced classes.

**MET-04 — Confusion Matrix**
- Displays True Positives, True Negatives, False Positives, and False Negatives.
- Supports interpretation of classification errors.

**MET-05 — ROC-AUC**
- Evaluates the model's ability to distinguish between the two classes across classification thresholds.
- Will be reported when appropriate and supported by the model outputs.

### Baseline Comparison

The RandomForestClassifier will be compared against a simple baseline, such as a DummyClassifier, to determine whether it provides meaningful predictive improvement.

### Success Criteria

CyberGuard AI Version 1.0 will be considered technically successful when:

- **SC-01:** The dataset can be loaded, inspected, and prepared successfully.
- **SC-02:** A reproducible train/test split is implemented without Data Leakage.
- **SC-03:** The RandomForestClassifier can be trained and generate predictions on unseen test records.
- **SC-04:** Precision, Recall, F1-score, and Confusion Matrix are calculated and interpreted.
- **SC-05:** The model's performance is compared with a simple baseline.
- **SC-06:** Classification errors and limitations are discussed, with particular attention to False Negatives.
- **SC-07:** The Jupyter Notebook can be executed using documented dependencies and instructions.
- **SC-08:** Findings are clearly communicated through GitHub documentation and a portfolio presentation.

### Performance Targets

Numeric performance thresholds will be defined after selecting and inspecting the dataset and establishing a baseline.

Targets must be justified using dataset characteristics, class distribution, and baseline performance. No specific accuracy or detection rate is guaranteed in advance.

### Important Limitations

- Strong test-set metrics do not guarantee performance on real-world network traffic.
- Dataset imbalance and Data Leakage can produce misleading evaluation results.
- The model is not validated for production intrusion detection.
- Predictions are intended for research and portfolio demonstration only.
