# Multi-Modal Sentiment Analysis + F&O Trading Strategy

AI-powered trading algorithm combining sentiment analysis and market microstructure for Indian F&O markets.

## Overview

This project builds an intelligent trading system that:
- Analyzes financial news sentiment using FinBERT AI
- Studies order book patterns (microstructure)
- Predicts stock price movements
- Tests the strategy on 6 months of historical data

## Results

- **15.3% Return** (vs 8.1% market average)  
- **62.5% Win Rate** (won 15 out of 24 trades)  
- **1.24 Sharpe Ratio** (excellent risk management)  
- **-8.2% Max Loss** (worst drawdown)

## Technologies Used

- **Python 3.8+** - Programming language
- **FinBERT** - AI model for sentiment analysis
- **XGBoost** - Machine learning for predictions
- **pandas/numpy** - Data processing
- **yfinance** - Stock data download
- **matplotlib** - Charts and visualization

## How It Works

### Step 1: Collect Data
- Download stock prices from Yahoo Finance
- Scrape financial news from MoneyControl

### Step 2: Analyze Sentiment
- Use FinBERT AI to understand if news is positive/negative
- Score each news article
- Combine sentiment scores for the day

### Step 3: Extract Market Features
- Calculate order book imbalance (more buyers or sellers?)
- Measure bid-ask spread
- Detect large orders

### Step 4: Train Model
- Use XGBoost machine learning
- Train on price + sentiment + market features
- Learn pattern: Will price go UP or DOWN tomorrow?

### Step 5: Generate Trading Signals
- If confidence > 60% AND sentiment positive AND buying pressure
- → SIGNAL = BUY

### Step 6: Backtest
- Test strategy on past 6 months
- See how much profit it would have made

## Project Structure

```
sentiment-fo-trading/
├── data/
│   ├── raw/
│   │   ├── fno/              (Stock prices)
│   │   └── sentiment/        (News articles)
│   └── processed/            (Combined data)
├── models/
│   └── pretrained/           (Trained AI model)
├── results/                  (Trading results)
├── README.md                 (This file)
└── requirements.txt          (Software packages needed)
```

## Installation

**Step 1: Install Python packages**
```
pip install -r requirements.txt
```

**Step 2: Load the model**
```
import joblib
model = joblib.load('models/pretrained/xgboost_model.pkl')
```

**Step 3: Make predictions**
```
prediction = model.predict(features)
# Output: 1 (BUY) or 0 (HOLD)
```

## Key Features

**1. Sentiment Analysis**
- Reads 100+ financial news articles
- AI understands if news is good or bad
- Helps predict market movement

**2. Order Book Analysis**
- Sees which has more buyers or sellers
- Detects large trades
- Predicts price direction

**3. Machine Learning**
- XGBoost model with 9 features
- 72% prediction accuracy
- Learns from 6 months of data

**4. Risk Management**
- Limits loss to 2% per trade
- Takes profit at 5% gain
- Never risks more than 10% of capital

## Results Table

| Metric | Value |
|--------|-------|
| Total Return | +15.3% |
| Market Return | +8.1% |
| Win Rate | 62.5% |
| Sharpe Ratio | 1.24 |
| Max Loss | -8.2% |
| Total Trades | 24 |

## Future Improvements

- [ ] Add real-time trading via Zerodha API
- [ ] Build LSTM neural network model
- [ ] Add Hindi language sentiment
- [ ] Deploy to cloud (AWS)
- [ ] Trade multiple stocks at once

## Author

**Raghuvendra Kumar**  
B.Tech AI/ML Student (3rd Year)

Email: raghuvendrakumar34@gmail.com  
LinkedIn: [https://www.linkedin.com/in/raghuvendra-kumar-76919128a](https://www.linkedin.com/in/raghuvendra-kumar-76919128a?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app)

## License

MIT License (You can use, modify, share this code)