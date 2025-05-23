
---
## Currently Fixing !!

I am trying to adjust the task here for the AI models for not predicting the actualy trend (due to the overfitting nd signal leg problems still severe in some case), but for helping rule-based stretegy for better judgement. Also, I am tryng to intergraet FinRL's API for better data preparation. So many design here might not be avaliable. I suggest to use the singal working cells for bulding new testing components.


## 📌 Features

- Dual-head Transformer model for weekly return prediction
- Per-ETF model training and top-weight selection (top-5 models)
- Strategy simulator with weekly rebalance and sell logic
- Predictive logs, value tracking, and benchmark comparisons
- Visual backtest results with matplotlib

---
## 📊 Prediction Visualization

Here is a sample output from the prediction module:

![ETF Prediction Demo](./assets/etf_pred_show.jpg)

## 🚀 Getting Started

### 1. Clone this repo

```bash
git clone <your-repo-url>
cd WEEKLY_SWING_TRANSFORMER
```

## Setup Python Environment
Make sure you have conda installed, then run:
```bash
conda env create -f environment.yml
conda activate stock_pred
python -m ipykernel install --user --name stock_pred --display-name "Python (stock_pred)"
```

## 3. Launch Notebook
Start Jupyter in VSCode or use:

```bash
jupyter notebook
```
Open agent/etf_weekly_swing.ipynb to train, predict, and backtest.

## Project Structure
```
.
├── agent/
│   └── etf_weekly_swing_test2.ipynb       # Main notebook
├── dataset/
│   ├── normalized_matrix/                 # Combined feature and mask matrices
│   ├── etf_prices_weekly.csv              # Raw weekly prices from Yahoo Finance
│   ├── backtest_trade_log.csv             # Log of buy/sell trades
│   └── backtest_value_log.csv             # Weekly portfolio valuation
├── model_weights/                         # Saved top-k models per ETF
├── environment.yml                        # Conda environment spec
└── README.md    # ← You are here!
```                          

## 📊 Strategy
Each week, predict returns using saved top-5 models

Select top 2 ETFs to buy with equal capital

Sell at end of week regardless of performance

Compare with SPY as a benchmark
