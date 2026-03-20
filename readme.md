#  Trader Performance vs Market Sentiment Analysis

##  Overview

This project explores how market sentiment (Fear vs Greed) influences trader behavior and performance on Hyperliquid. The goal was to identify patterns in trading activity and extract insights that could be useful for building smarter trading strategies.

The analysis combines historical trader data with Bitcoin market sentiment data and examines how different emotional states of the market impact profitability, risk-taking, and trading decisions.

---

##  Dataset Description

### 1. Market Sentiment Data
- Contains daily classification of market sentiment (Fear, Greed, Extreme Fear, etc.)
- Used as a proxy for overall market psychology

### 2. Trader Data (Hyperliquid)
Includes:
- Account (trader ID)
- Trade size (USD)
- Trade direction (BUY/SELL)
- Closed PnL
- Timestamp

---

##  Data Preparation

- Converted timestamps into a common **daily format**
- Aligned both datasets using the `date` column
- Removed a small number of unmatched rows (~6), which had negligible impact
- Standardized column names for consistency

### Feature Engineering
- **Win indicator** (profitable vs non-profitable trades)
- **Daily PnL per trader**
- **Trade frequency**
- **Average trade size**
- **Buy/Sell ratio**

---

##  Key Findings

### 1. Market Sentiment Impacts Profitability
- **Extreme Greed** showed the highest average PnL and win rate  
- Indicates strong trends and more predictable market conditions  

---

### 2. Fear Leads to Riskier Trading
- Traders used the **largest position sizes during Fear**
- However, win rate was lower → suggests **high-risk, high-reward behavior**

---

### 3. Contrarian Behavior in Greed Markets
- During **Extreme Greed**, traders placed more SELL trades (~55%)
- Suggests profit-taking or expectation of reversals  

---

### 4. Neutral Markets Offer Low Edge
- Lower profitability and average win rates  
- Indicates lack of clear direction → harder to trade effectively  

---

##  Strategy Recommendations

- **Trend-follow during Extreme Greed**  
  → Higher win probability and profitability  

- **Reduce position sizes during Fear**  
  → Traders tend to overexpose themselves in volatile conditions  

- **Look for short opportunities in Greed phases**  
  → Market shows signs of reversal behavior  

- **Avoid trading in Neutral sentiment**  
  → No strong edge observed  

---

##  Visualizations

The notebook includes:
- PnL distribution across sentiment categories  
- Win rate comparison  
- Buy vs Sell behavior analysis  

---

##  Conclusion

This analysis highlights how trader behavior shifts with market sentiment. Emotional states like Fear and Greed not only affect performance but also influence risk-taking and decision-making patterns.

Understanding these patterns can help design more adaptive and sentiment-aware trading strategies.

---

##  How to Run

```bash
pip install pandas matplotlib seaborn
