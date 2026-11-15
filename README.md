# WealthPilot

**AI-Powered Investment Decision Support | AlphaForge AI — Datathon 2026**

## Project Overview

WealthPilot is an AI-powered educational investment simulation platform designed to help users understand their financial profiles, evaluate investment risks, and explore personalized investment scenarios.

By integrating public financial data, rule-based investor classification, and explainable AI Agents, WealthPilot delivers transparent, goal-based financial insights while highlighting assumptions, uncertainties, and limitations.

## Key Features

- **Investor Classification:** Evaluates Risk Capacity and Risk Tolerance to assign one of five risk profiles, applying goal-specific investment horizon constraints.
- **Financial Analysis:** Calculates Historical Returns, CAGR, Volatility, Sharpe/Sortino Ratios, Maximum Drawdown, and Portfolio Exposure.
- **Portfolio Simulation:** Compares hypothetical allocations using historical data, rebalancing, and transaction costs.
- **Macroeconomic Analysis:** Examines Inflation, Interest Rates, and economic indicators to contextualize financial risk.
- **Financial News Analysis:** Evaluates headline relevance, source credibility, sentiment, and Descriptive versus Predictive content.
- **Explainable AI Agents:** An Advisor and Devil's Advocate generate and challenge explanations, while a deterministic Verifier checks numerical claims against calculation receipts.

## Technical Architecture

**React 18 + Vite (Frontend) → FastAPI (Backend) → Python Financial Engines → Public Financial Data**

| Component | Technologies |
|---|---|
| Frontend | React 18, Vite, Chart.js |
| Backend | Python, FastAPI |
| Data Analysis | pandas, NumPy, Matplotlib, Jupyter Notebook |
| AI Agents | Claude, calculation tools, deterministic verification |
| Cloud Integration | Amazon Bedrock, AWS Lambda, S3, DynamoDB |
| Project Management | GitHub Projects, Scrumban |

*AWS integration code is included; live deployment and end-to-end execution require final verification.*

## Data Sources

| Source | Purpose |
|---|---|
| Yahoo Finance | Historical prices, ETFs, cryptocurrencies, and financial news |
| Bank of Canada | Canadian Inflation, Interest Rates, Bond Yields, and USD/CAD exchange rates |
| FRED | U.S. macroeconomic indicators |
| Organizer Asset Universe | Metadata for 31 selected financial assets |

The starter Market Dataset covers **November 12, 2021 – November 12, 2026**. Additional macroeconomic history and news are collected separately.

## Installation & Local Setup

### Requirements

- Python 3.10+
- Node.js 18+
- Git
- Internet access to obtain public datasets

### 1. Clone the Repository

```bash
git clone https://github.com/Juanita-HP/WealthPilot.git
cd WealthPilot
```

### 2. Install Python Dependencies

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 3. Prepare the Datasets

Place the organizers' CSV files in `data/starter/` or regenerate the public starter data:

```bash
python scripts/build_dataset.py
```

For extended macroeconomic analysis:

```bash
python scripts/fetch_macro_history.py
```

### 4. Run the Application

```bash
cd web
npm install
npm run build
cd ..
python -m wealthpilot.api
```

Open **http://127.0.0.1:8000** in your browser.

AI Agent execution requires the relevant LLM provider configuration and credentials.

## Testing

The repository includes automated tests covering financial calculations, investor profiling, portfolio constraints, data processing, and agent verification.

Run:

```bash
pytest
```

Final test results and live AWS integration must be verified before submission.

## Demonstration Personas

- **Amira:** High risk tolerance, long-term growth, and diversification.
- **Mateo:** Moderate risk, balanced investment objectives, and ESG preferences.
- **Robert:** Capital preservation, shorter investment horizon, and potential conflicts with speculative investments.

## Documentation

- [Project Overview & Requirements](docs/project_overview_requirements.md)
- [Data Analysis & Technical Report](docs/Data_Report.pdf)
- [Jupyter Notebook — Data Documentation, EDA & Visualizations](notebooks/WealthPilot_Data_Analysis.ipynb)

## Project Status

WealthPilot includes the application source code, financial analysis modules, AI Agent workflows, and preliminary technical documentation.

**Pending final verification:** Live deployment URL, end-to-end AWS execution, comprehensive testing results, and final demonstration materials.

## Disclaimer

WealthPilot is designed exclusively for educational investment simulations. It does not execute real trades, guarantee future returns, or provide regulated personalized financial advice.
