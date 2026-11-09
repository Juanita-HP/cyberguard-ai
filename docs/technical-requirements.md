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
