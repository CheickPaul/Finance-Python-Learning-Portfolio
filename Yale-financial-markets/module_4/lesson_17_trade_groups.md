# Lesson – Market Makers, Brokers, Spreads & VPIN

## Key Concepts

### 1. From Fixed Commissions to Zero Commission
- Before 1975 (US) / 1986 (UK): Brokers charged fixed commissions (e.g., 0.25% per trade).  
- After deregulation → competition lowered fees → discount brokers emerged → online brokers pushed to zero commissions.  
- Today: brokers like Robinhood, Trade Republic advertise “zero commission.”  
👉 But *zero commission ≠ free trading* → true cost is hidden in spreads, PFOF, and execution quality.  

---

### 2. Broker ↔ Market Maker Relationship
- **Investor** sends order via broker.  
- **Broker** sells order flow to a Market Maker (MM) through Payment for Order Flow (PFOF).  
- **Market Maker** executes order, profits from spread, pays broker.  

Result:
- Investor sees zero commission.  
- Broker earns PFOF.  
- MM profits from the spread.  

---

### 3. How Market Makers Operate
- MM quotes **Bid / Ask**. Spread = Ask − Bid.  
- Example: Bid = 100.00, Ask = 100.05 → retail buys 100 shares → MM hedges at 100.00 → profit = $5.  
- Other revenue sources: internalization, exchange rebates, order-flow models.  

---

## My Notes & Reflection

### 4. Order Flow Toxicity (OFT)
- **Non-toxic flow (retail)**: small, random, intuitive orders → predictable → MMs capture spread consistently.  
- **Toxic flow (informed / HFT)**: large, fast, predictive → MM risks losses if quotes are too tight.  
- Consequence: MMs widen spreads or reduce liquidity when toxicity rises.  

👉 Insight: For MMs, *retail flow is gold* (predictable profits). *Institutional flow is dangerous* (risk of adverse selection).  

---

### 5. VPIN – Volume-Synchronized Probability of Informed Trading

**Concept**: VPIN detects imbalance between buys and sells → proxy for toxicity.  
- Balanced flow → low VPIN → calm market.  
- Imbalanced flow → high VPIN → institutions likely active.  

**Step-by-step**:
1. Classify volume (buy if price ↑, sell if ↓, split if flat).  
2. Build volume buckets (e.g., 2000 contracts).  
3. Measure imbalance:  
   - Example: 1200 buys vs 800 sells → Imbalance = 400 → Ratio = 20%.  
4. Smooth across last N buckets → VPIN.  

**Toy Example**:  
| Bucket | Buys | Sells | Imbalance | Ratio |
|--------|------|-------|-----------|-------|
| 1      | 600  | 400   | 200       | 0.20  |
| 2      | 800  | 200   | 600       | 0.60  |
| 3      | 500  | 500   | 0         | 0.00  |  
VPIN = (0.20 + 0.60 + 0.00) / 3 = 0.27 → elevated toxicity.  

---

### 6. Practical Interpretation
- **Low VPIN (0.05–0.10)**: calm, spreads tight, safe for MMs.  
- **High VPIN (0.25–0.40+)**: toxic flow, spreads widen, higher risk of adverse selection.  

---

### 7. Retail Strategies with VPIN
- **Risk filter**: avoid entering when VPIN is high.  
- **Momentum follow**: spike in VPIN → institutions pushing → ride short-term move, exit fast.  
- **Setup filter**: breakout + high VPIN = stronger conviction (confirmation of institutional activity).  

👉 Retail traders cannot beat HFT in speed, but VPIN is useful context to avoid traps and align with durable flows.  

---

## Key Takeaways
- Brokers earn from PFOF, not “free” commissions.  
- MMs profit from spread capture but are vulnerable to toxic flow.  
- OFT explains why retail order flow is valuable.  
- VPIN measures toxicity risk → useful for risk filters and context in trading.  
- Implementation: Python sufficient for backtesting, C++ only for HFT-level latency.  

