
# [Financial Futures: S&P 500 Index & Federal Funds Rate]

## 1. S&P 500 Futures (Index Futures)

* **Type**: Cash-settled (no physical delivery).
* **Settlement Formula**:

$$
\text{Settlement Value} = 250 \times \big( \text{Index Level on Last Day} - \text{Futures Price on Previous Day} \big)
$$

* **Fair Value Formula**:

$$
F = S \times (1 + r - y)
$$

where:  

- \( S \) = Spot price of the index  
- \( r \) = Risk-free rate  
- \( y \) = Dividend yield (acts like a negative storage cost)  

 Intuition: Holding stocks pays dividends, so the cost of carry is adjusted downward by the dividend yield.

---

## 2. Federal Funds Rate (FFR) Futures

* **Launched**: Chicago Board of Trade (1988).  
* **Underlying**: The overnight **federal funds rate** (interbank lending rate targeted by the Fed).  
* **Settlement**: Cash-settled.  

$$
\text{Price} = 100 - \text{Annualized FFR (average over contract month)}
$$

* **Usage**:
  - Barometer of **market expectations** for upcoming **Federal Open Market Committee (FOMC)** decisions.  
  - Example: If FFR futures trade at 97.75 → implied FFR = **2.25%**.  

 Different from commodities or index futures: no arbitrage pricing model, because an **interest rate cannot be stored**.

---

## 3. Predictive Value of FFR Futures

### Why They Are Predictive
- The Fed’s decision (target rate) is **clear and binary**.  
- FFR futures prices directly encode what the market expects that decision to be.  

### Why They Work Well
- **Clear outcome** → Fed announces a target rate.  
- **Near-term horizon** → contracts focus on the next few months.  
- **High attention** → speculators and analysts study the Fed intensively.  

### Comparison with Stock Market Predictions

| Aspect                | FFR Futures                        | Stock Market (Equities)                  |
| --------------------- | ---------------------------------- | ---------------------------------------- |
| **Prediction target** | Next Fed decision (rate level)     | Long-term dividends/earnings             |
| **Time horizon**      | Weeks / months                     | Many years / indefinite                  |
| **Uncertainty**       | Low (binary, well-defined outcome) | High (economic cycles, innovation, etc.) |
| **Efficiency**        | High – strong short-term predictor | Weaker – noisy long-term predictor       |

---

##  Key Takeaways

- **Index futures** follow a cost-of-carry model adjusted for dividends.  
- **FFR futures** are pure prediction markets for Fed policy.  
- Prediction markets work best when the outcome is:  
  1. Short-term  
  2. Clear  
  3. Widely studied  
