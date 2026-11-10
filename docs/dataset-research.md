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
