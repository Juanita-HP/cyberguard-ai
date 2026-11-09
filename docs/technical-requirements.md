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
