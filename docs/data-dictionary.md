
# CyberGuard AI — Data Dictionary

## 4.9 Data Dictionary

### 1. Overview

This document describes the 45 variables available in
the prepared UNSW-NB15 training and testing datasets.

Feature descriptions are adapted from the official
UNSW-NB15 feature dictionary.

### 2. Dataset Information

- Dataset: UNSW-NB15
- Training records: 175,341
- Testing records: 82,332
- Total records: 257,673
- Total columns: 45
- Candidate input features: 42
- Excluded columns: 2
- Target variable: 1

### 3. Complete Data Dictionary

| Variable | Data Type | Description | Role |
|---|---|---|---|
| id | Integer | Unique record identifier | Excluded |
| dur | Float | Total connection duration | Feature |
| proto | Nominal | Network transaction protocol | Feature |
| service | Nominal | Network application service | Feature |
| state | Nominal | Connection state associated with the protocol | Feature |
| spkts | Integer | Source-to-destination packet count | Feature |
| dpkts | Integer | Destination-to-source packet count | Feature |
| sbytes | Integer | Bytes transmitted from source to destination | Feature |
| dbytes | Integer | Bytes transmitted from destination to source | Feature |
| rate | Float | Traffic rate; exact calculation requires verification | Feature |
| sttl | Integer | Source-to-destination time-to-live value | Feature |
| dttl | Integer | Destination-to-source time-to-live value | Feature |
| sload | Float | Source bits per second | Feature |
| dload | Float | Destination bits per second | Feature |
| sloss | Integer | Source packets retransmitted or dropped | Feature |
| dloss | Integer | Destination packets retransmitted or dropped | Feature |
| sinpkt | Float | Source interpacket arrival time in milliseconds | Feature |
| dinpkt | Float | Destination interpacket arrival time in milliseconds | Feature |
| sjit | Float | Source jitter in milliseconds | Feature |
| djit | Float | Destination jitter in milliseconds | Feature |
| swin | Integer | Source TCP advertised window value | Feature |
| stcpb | Integer | Source TCP base sequence number | Feature |
| dtcpb | Integer | Destination TCP base sequence number | Feature |
| dwin | Integer | Destination TCP advertised window value | Feature |
| tcprtt | Float | TCP connection setup round-trip time | Feature |
| synack | Float | Time between SYN and SYN-ACK packets | Feature |
| ackdat | Float | Time between SYN-ACK and ACK packets | Feature |
| smean | Integer | Mean source packet size | Feature |
| dmean | Integer | Mean destination packet size | Feature |
| trans_depth | Integer | HTTP request-response pipeline depth | Feature |
| response_body_len | Integer | Uncompressed HTTP response content size | Feature |
| ct_srv_src | Integer | Recent connections sharing source address and service | Feature |
| ct_state_ttl | Integer | Connection count by state and TTL range | Feature |
| ct_dst_ltm | Integer | Recent connections sharing destination address | Feature |
| ct_src_dport_ltm | Integer | Recent connections sharing source address and destination port | Feature |
| ct_dst_sport_ltm | Integer | Recent connections sharing destination address and source port | Feature |
| ct_dst_src_ltm | Integer | Recent connections sharing source and destination addresses | Feature |
| is_ftp_login | Binary | Indicates FTP authentication using username and password | Feature |
| ct_ftp_cmd | Integer | Number of flows containing FTP commands | Feature |
| ct_flw_http_mthd | Integer | Number of flows containing HTTP methods | Feature |
| ct_src_ltm | Integer | Recent connections sharing source address | Feature |
| ct_srv_dst | Integer | Recent connections sharing destination address and service | Feature |
| is_sm_ips_ports | Binary | Indicates matching source and destination IP addresses and ports | Feature |
| attack_cat | Nominal | Attack category | Excluded |
| label | Binary | Normal or malicious traffic classification | Target |

### 4. Feature Categories

#### 4.1 Basic Traffic Features

Variables describing connection duration, protocol,
service, state, packet counts, and transmitted bytes.

#### 4.2 Network Performance Features

Variables describing traffic rate, throughput,
packet loss, jitter, and interpacket arrival times.

#### 4.3 TCP Connection Features

Variables describing TCP windows, sequence numbers,
and connection establishment times.

#### 4.4 Application-Level Features

Variables describing HTTP and FTP activity.

#### 4.5 Connection History Features

Variables describing recent connections that share
network addresses, ports, services, or connection states.

### 5. Target Variable

The target variable is `label`.

| Value | Class | Description |
|---|---|---|
| 0 | Benign | Normal network traffic |
| 1 | Malicious | Attack-related network traffic |

CyberGuard AI uses supervised machine learning
to perform binary classification.

### 6. Excluded Variables

#### id

The record identifier will be excluded from model
training because it is not a meaningful network
traffic characteristic and may introduce artifacts.

#### attack_cat

The attack category will be excluded from model
training because it contains information directly
related to the target variable.

Including this variable could introduce target leakage.

### 7. Original-to-Prepared Feature Mapping

| Original Name | Prepared Name |
|---|---|
| Sload | sload |
| Dload | dload |
| Spkts | spkts |
| Dpkts | dpkts |
| Sjit | sjit |
| Djit | djit |
| Sintpkt | sinpkt |
| Dintpkt | dinpkt |
| smeansz | smean |
| dmeansz | dmean |
| res_bdy_len | response_body_len |
| ct_src_ ltm | ct_src_ltm |
| Label | label |

### 8. Dataset Schema Differences

The original feature dictionary contains 49 variables.

The prepared datasets contain 45 columns.

Original variables not present in the prepared datasets:

- srcip
- sport
- dstip
- dsport
- Stime
- Ltime

Additional prepared dataset variables:

- id
- rate

The original feature dictionary does not explicitly
define these two additional variables.

### 9. Data Preprocessing Considerations

- Validate actual pandas data types.
- Investigate invalid values and placeholders.
- Validate binary variable values.
- Investigate duplicate records.
- Investigate potential training and testing overlap.
- Encode categorical input features.
- Exclude identifier and target-leaking variables.
- Preserve the original dataset files.
- Fit preprocessing transformations using training data only.

### 10. Documentation Notes

Data types in this document represent semantic types
rather than verified pandas storage types.

The definitions of id and rate are provisional
interpretations because these variables are not
included in the original feature dictionary.

The 42 input features are candidates and may be
reduced following further data quality analysis
and feature selection.

### 11. References

Official UNSW-NB15 Dataset:

https://research.unsw.edu.au/projects/unsw-nb15-dataset

Official Feature Dictionary:

UNSW-NB15_features.csv

Dataset Inspection Notebook:

notebooks/01_dataset_inspection.ipynb
