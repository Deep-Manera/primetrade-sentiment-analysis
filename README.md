# Trader Performance vs Market Sentiment  
**Primetrade.ai – Round-0 Assignment**

---

## Objective
This project analyzes how Bitcoin market sentiment, measured using the **Fear & Greed Index**, impacts trader behavior and performance on **Hyperliquid**. The goal is to extract actionablae insights that can support sentiment-aware trading strategies.

---

## Datasets
Two datasets were used:

- **Bitcoin Fear & Greed Index**  
  Daily sentiment classification (Fear, Greed, etc.)

- **Hyperliquid Historical Trader Data**  
  Trade-level execution data including price, size, side, PnL, and timestamps

---

## Methodology
- Trade timestamps were converted from **epoch milliseconds** to calendar dates.
- Data was aggregated at a **daily per-trader level**.
- Market sentiment was aligned by date.
- The following metrics were computed:
  - Daily profit and loss (PnL)
  - Trades per day
  - Average trade size (USD)
  - Long/short bias (buy ratio)
- Traders were segmented based on trading activity to analyze behavioral differences.

---

## Key Insights

### 1. Trader performance varies across sentiment conditions
Traders show a **higher average daily PnL during Fear periods**, but with significantly higher variance. This suggests Fear markets offer greater profit opportunities at increased risk, while Greed markets tend to produce lower but more stable returns.

**Evidence**
- Daily PnL distribution by sentiment
- Summary statistics of daily PnL by sentiment class

---

### 2. Traders increase activity and risk during Fear
During Fear phases, traders place **more trades per day** and use **larger average position sizes**, indicating aggressive and opportunistic behavior. Greed phases are associated with comparatively cautious trading.

**Evidence**
- Average trades per day by sentiment
- Average trade size comparison across sentiment regimes

---

### 3. Trading segments respond differently to sentiment
**Frequent traders** outperform infrequent traders during Fear periods but tend to underperform during Greed periods. This implies that active traders benefit from volatility-driven opportunities in Fear markets, while overtrading in optimistic conditions can reduce performance.

**Evidence**
- Trader segmentation based on activity level
- Segment-wise average PnL across sentiment classes

---

## Strategy Recommendations

### Rule 1: Sentiment-based leverage control
- During **Fear** periods, allow higher leverage only for traders with a proven positive performance history.
- During **Greed** periods, enforce stricter leverage limits to reduce losses from overconfidence.

---

### Rule 2: Activity-based trade filtering
- In **Greed** markets, reduce trade frequency for high-activity traders and prioritize selective setups.
- In **Fear** markets, allow increased activity for traders who have demonstrated consistent profitability under volatility.

---

## Limitations
- Analysis is based on **daily aggregation** and does not capture intraday sentiment changes.
- Limited observations for **Extreme Greed** days.
- Incomplete leverage data restricted more granular risk-adjusted analysis.

---

## Environment & Reproducibility
This analysis was developed and executed using **Google Colab**.

The default Colab environment was used with standard data science libraries:
- pandas
- numpy
- matplotlib
- scikit-learn (optional modeling)

No additional setup is required to run the notebook in Colab.

---

## Repository Structure
