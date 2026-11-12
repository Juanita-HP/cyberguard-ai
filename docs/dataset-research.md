### CIC-IDS2017 Documentation Review

- **Source:** Canadian Institute for Cybersecurity, University of New Brunswick.
- **Collection period:** July 3–7, 2017.
- **Data type:** Historical labeled network traffic.
- **Features:** More than 80 network flow features extracted using CICFlowMeter.
- **Labels:** Benign and multiple attack categories.
- **Format:** CSV files for Machine Learning; PCAP files also available.
- **Binary Classification compatibility:** Yes, by mapping benign traffic to 0 and attack categories to 1.
- **Limitations:** Historical experimental environment, substantial data volume, preprocessing and label mapping required.
- **Decision:** Retain as a comparison candidate; UNSW-NB15 remains the provisional primary dataset.
- **Official source:** https://www.unb.ca/cic/datasets/ids-2017.html

## 4.3 Dataset Comparison Matrix

### Objective

Compare three cybersecurity datasets to identify the most suitable option for CyberGuard AI Version 1.0, an offline Binary Classification project.

### Candidate Comparison

| Criterion | UNSW-NB15 | CIC-IDS2017 | CSE-CIC-IDS2018 |
|---|---|---|---|
| Source | UNSW Canberra | University of New Brunswick | CSE and University of New Brunswick |
| Historical network traffic | Yes | Yes | Yes |
| Network features | 49 documented attributes, including labels | More than 80 flow features | More than 80 flow features |
| Binary target | Available directly | Requires attack-label mapping | Requires attack-label mapping |
| CSV availability | Yes | Yes | Yes |
| Prepared train/test files | Yes | Not provided as the same standard partition | Not provided as the same standard partition |
| Dataset scale | 2,540,044 records overall; smaller prepared subsets available | Multi-million-record dataset | Large-scale dataset |
| Beginner suitability | High | Moderate | Lower |
| Data quality | Requires inspection | Requires inspection | Requires inspection |
| Licensing | Verify portfolio/publication conditions | Verify usage and citation requirements | Citation and usage terms published |
| Primary limitation | Older, synthetic/experimental traffic and possible distribution differences | Larger files, preprocessing and label mapping | Larger scale, more complex acquisition and preprocessing |

### Preliminary Selection

**Preferred Dataset:** UNSW-NB15

**Reasons:**
1. Provides a binary target label suitable for Supervised Learning.
2. Includes documented network traffic features.
3. Offers prepared training and testing CSV files.
4. Provides a manageable starting point for Python, pandas, EDA, and RandomForestClassifier.
5. Aligns with the educational scope of CyberGuard AI Version 1.0.

### Planned Dataset Files

- UNSW_NB15_training-set.csv — 175,341 records.
- UNSW_NB15_testing-set.csv — 82,332 records.
- UNSW-NB15_features.csv — Feature descriptions.

### Remaining Validation

Before confirming the final dataset selection:
- Inspect actual column names, types, and labels.
- Check missing values, duplicates, and potential Data Leakage.
- Review class distribution and dataset limitations.
- Verify licensing and permitted public portfolio use.
- Confirm the files can be processed with available hardware.

### Decision Status

**Provisional selection — pending technical and licensing validation.**

### Official Sources

- UNSW-NB15: https://research.unsw.edu.au/projects/unsw-nb15-dataset
- CIC-IDS2017: https://www.unb.ca/cic/datasets/ids-2017.html
- CSE-CIC-IDS2018: https://www.unb.ca/cic/datasets/ids-2018.html


## 4.5 Dataset Size, Formats, Quality and Limitations

### Overview

A preliminary dataset inspection was conducted using Python
and pandas in a Jupyter Notebook to evaluate the structure,
quality, and limitations of the UNSW-NB15 dataset.

### Dataset Size and Format

| Metric | Training Set | Testing Set |
|---|---:|---:|
| Number of records | 175,341 | 82,332 |
| Number of columns | 45 | 45 |
| File format | CSV | CSV |
| Missing values | 0 | 0 |
| Duplicate records | 67,601 | 26,387 |
| Duplicate percentage | 38.55% | 32.05% |
| Benign records | 56,000 | 37,000 |
| Malicious records | 119,341 | 45,332 |

Total number of records: 257,673.

### Data Quality Assessment

- No missing values were detected by pandas in either dataset.
- Duplicate records were identified after excluding the ID column.
- Duplicate records require further investigation before removal.
- Numerical and categorical variables are present.
- The dataset includes a binary target variable named `label`.
- No modifications were made to the original datasets.

### Class Distribution

Training Dataset:

- Benign (0): 31.94%
- Malicious (1): 68.06%

Testing Dataset:

- Benign (0): 44.94%
- Malicious (1): 55.06%

The training dataset presents a class imbalance that must
be considered during model training and evaluation.

### Dataset Limitations

- The dataset contains a substantial number of repeated records.
- Potential overlap between training and testing records
  requires further investigation.
- Class distributions differ between the training and testing sets.
- The dataset was generated in a controlled research environment
  and may not fully represent real-world financial network traffic.
- Historical attack patterns may not represent emerging threats.
- Categorical variables require appropriate preprocessing.
- The absence of missing values does not guarantee the absence
  of invalid or inconsistent values.

### Inspection Tools

- Python
- pandas
- Jupyter Notebook
- Visual Studio Code

### Inspection Notebook

`notebooks/01_dataset_inspection.ipynb`

### Conclusion

The UNSW-NB15 dataset is suitable for preliminary binary
classification research. However, duplicate records,
potential data leakage, class imbalance, and data
representativeness must be addressed during subsequent
project phases.


## 4.6 Licensing and Permitted Use

### Dataset Ownership

- Dataset: UNSW-NB15
- Institution: University of New South Wales
- Authors: Nour Moustafa and Jill Slay

### Terms of Use

The dataset is available for academic research without
a usage fee. Commercial applications require an
agreement with the authors.

Copyright remains with the original authors.
Users must cite the five publications identified
on the official dataset website.

### Project Compliance

CyberGuard AI is an independent, non-commercial,
educational research project.

The project will:

- Use the dataset for educational research.
- Provide appropriate academic attribution.
- Keep the original dataset files stored locally.
- Exclude raw datasets from GitHub.
- Direct users to the official download source.
- Avoid commercial deployment.
- Seek clarification if additional permissions
  are required for public portfolio publication.

### Publication Strategy

The GitHub repository will contain original source code,
technical documentation, and research methodology.

Raw dataset redistribution will be avoided.
Public research outputs will be shared subject to
the applicable dataset usage conditions.

### Official Source

https://research.unsw.edu.au/projects/unsw-nb15-dataset

Accessed: November 11, 2026.

### Required References

The five publications specified by UNSW will be
included in the project's academic references.


## 4.7 Dataset Selection and Justification

### Selected Dataset

UNSW-NB15 was selected as the primary dataset
for CyberGuard AI Version 1.0.

### Selection Rationale

The dataset was selected based on the following criteria:

- Alignment with the cybersecurity problem statement.
- Availability of a binary target variable.
- Compatibility with supervised machine learning.
- Availability of predefined training and testing sets.
- Manageable dataset size for local development.
- Availability of feature documentation.
- Compatibility with Python and pandas.
- Suitability for educational cybersecurity research.

### Technical Compatibility

- Problem type: Binary Classification
- Learning approach: Supervised Learning
- Target variable: label
- Benign class: 0
- Malicious class: 1
- Training records: 175,341
- Testing records: 82,332
- Total records: 257,673
- Columns per dataset: 45
- File format: CSV

### Identified Risks

- Duplicate records.
- Potential training and testing overlap.
- Class imbalance.
- Historical attack patterns.
- Limited real-world representativeness.

These risks will be investigated during data cleaning,
preprocessing, and model evaluation.

### Final Decision

UNSW-NB15 is selected as the official dataset
for CyberGuard AI Version 1.0.

The selection is based on technical compatibility,
research objectives, computational feasibility,
and educational value.

The project will remain an offline research simulation
and will not be presented as a production-ready
cybersecurity system.

