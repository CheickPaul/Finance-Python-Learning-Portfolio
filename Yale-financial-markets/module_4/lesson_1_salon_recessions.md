# Lesson 1 – Salon: Recessions

## 1. Nature of Recessions
- According to Robert Shiller (*Animal Spirits*, with George Akerlof), recessions are largely **psychological**.  
- Similar to depression: even with central bank or government intervention, recovery is not immediate.  

---

## 2. Inverted Yield Curves
- Occur when **short-term interest rates** > **long-term interest rates**.  
- Normally, long-term rates are higher due to the additional risk.  
- Historically, an **inverted yield curve** has often been a leading indicator of recession.  

**Possible explanations:**
- **Long-term pessimism**: investors expect weak growth and low investment (examples: Japan, Germany).  
- **Central bank tightening**: in the past, central banks raised short-term rates sharply to fight inflation, which often triggered recessions.  

---

## 3. Other Indicators
- **Stock market**: the most widely recognized leading indicator.  
  - Examples: 1929, 2000, 2007 → major declines preceded recessions.  
  - Self-fulfilling effect: falling markets increase fear, reduce spending and investment, and worsen the downturn.  

- **Bond market spreads** (e.g., LIBOR–OIS): can reflect stress but are generally less predictive than equities.  

---

## 4. Forecasting Challenges
- Recessions are hard to forecast until clear signs appear (e.g., rising unemployment).  
- Analogy: like predicting whether a movie will be successful → the key factor is **public sentiment and collective psychology**.  

---

## 5. Reflection and Research (Building a Sentiment Score)
Sentiment helps desks adjust risk earlier than macro models, but it’s fragile. The best practice is to treat it as an early-warning radar, not as a standalone trigger.

## Inputs (by family)

- **Market**: VIX, MOVE (rates volatility), HY–IG credit spreads, put/call ratio  
- **Macro**: CESI (economic surprise index), PMI sentiment surveys  
- **Retail/Survey**: AAII, University of Michigan, Conference Board  
- **Alt-data**: NLP on news, Google Trends, Twitter/Reddit sentiment  

---

##  Method

1. Normalize each series (z-score).  
2. Weight them (often via backtesting — testing which inputs anticipate markets best over different horizons).  
3. Aggregate into a composite index (e.g., *Sentiment Index* or *Risk Appetite Index*).  

---

##  Desk Usage

### Trading / Positioning
- If **Sentiment Score > upper threshold** (extreme fear) → contrarian buy (mean reversion).  
- If **Sentiment Score < lower threshold** (extreme euphoria) → reduce leverage, sell, or hedge.  

### Risk Management
- Dynamically adjust leverage or VAR limits.  
- Add hedges (puts, swaptions, volatility options) if sentiment deteriorates quickly.  

### Asset Allocation
- Macro funds (e.g., Bridgewater, AQR) build “Risk-On / Risk-Off” signals partly from sentiment.  
- Example: shift into defensive assets (UST, Bunds, Gold) if sentiment drops below a certain level.  

---

##  Concrete Example

A Global Sentiment Score might be:

$$
Score_t = w_1 \cdot Z(VIX_t) + w_2 \cdot Z(Spreads_t) + w_3 \cdot Z(NLP_t) + w_4 \cdot Z(Survey_t)
$$

### Interpretation
- $Score_t > +2$ → High stress (hedge / reduce risk-on positions).  
- $Score_t < -2$ → Euphoria (possible contrarian short).  
- **Neutral zone** = small tactical adjustments.  

