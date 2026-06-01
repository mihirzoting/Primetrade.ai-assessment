# Assesment: Sentiment vs Trading Performance

## Project Overview
This project analyzes historical trading performance against the Fear & Greed Index to understand how market sentiment relates to profitability, win rate, activity, and trade behavior. The notebook produces summary tables and visualizations, and saves all charts to the `images/` folder.

## Dataset Description
1. `dataset/historical_data.csv` — Trade-level history with timestamps, PnL, size, fees, side, coin, and account.
2. `dataset/fear_greed_index.csv` — Daily sentiment index with `date`, `classification`, and `value`.

## Installation
**Prerequisite:** Python 3.10+ installed.

### Windows VS Code Setup
1. Install VS Code and the **Python** and **Jupyter** extensions.
2. Open the project folder in VS Code.
3. Create and activate a virtual environment, install requirements, and register a kernel:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m ipykernel install --user --name assesment --display-name "Assesment (venv)"
```

## Running `analysis.ipynb`
1. Open `analysis.ipynb` in VS Code.
2. Select the **Assesment (venv)** kernel.
3. Run all cells top-to-bottom. Charts are saved under `images/`.

## Key Findings
1. **Extreme Greed** shows the strongest performance: average PnL ≈ **130.21** and win rate ≈ **89.17%**.
2. **Extreme Greed** also has the highest profit factor at **≈ 11.02**.
3. Top profitable coins include **@107, HYPE, SOL, ETH, BTC**.

## Project Structure
```
Assesment/
├── analysis.ipynb
├── dataset/
│   ├── historical_data.csv
│   └── fear_greed_index.csv
└── images/
```
