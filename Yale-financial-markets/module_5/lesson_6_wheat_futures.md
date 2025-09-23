# Lesson – Wheat Futures

## Key Concepts
- Wheat futures provide **risk management (hedging)** and **price discovery**.  
- **Hedgers**: Producers/consumers use futures to stabilize income/costs.  
- **Speculators**: Provide liquidity, improve pricing accuracy.  
- Futures contracts:  
  - Underlying: **Soft Red Winter Wheat**.  
  - Size: **1,000 bushels**.  
  - Quoted in **cents per bushel**.  
  - Tick = **1/8 cent per bushel = $1.25 per contract**.  
- **Seasonality**: Winter wheat planted in fall, harvested in spring.  
- Futures curve shapes:  
  - **Contango**: Futures > spot (linked to storage & interest costs).  
  - **Backwardation**: Futures < spot (often at harvest when supply is abundant).  

---

## My Notes
- Public often confuses speculation with gambling. Shiller calls speculation a **noble profession** → ensures liquidity and efficiency.  
- Agricultural cycles strongly influence futures dynamics (prices fall at harvest, rise during scarcity).  
- Example: 2016–2018 data → futures systematically dipped in May during harvest.  
- Futures help smooth shocks by signaling **expected abundance or scarcity** before it happens.  
- Analogy: **Squirrels with acorns** → like farmers, they would hedge shortages if they had a futures market.  

---

## Reflection
### 1. Hedging in Practice
- **Farmer Hedge**:  
  - Produces 50,000 bushels, locks in futures at $5.  
  - If price falls to $4 → loses $50,000 on crop, gains $50,000 on futures.  
  - Secures stable revenue = $250,000.  
- **Bakery Hedge**:  
  - Needs 10,000 bushels in 6 months.  
  - Buys futures at $5.  
  - If price rises to $7 → pays more in spot, but gains on futures.  
  - Stabilizes production cost = $50,000.  

**Insight**: Hedgers seek stability, not profit. Speculators make hedging possible.  

---

### 2. Contango vs Backwardation

The **fair value of a futures contract** is given by the **cost-of-carry model**:  

\[
F = S \cdot e^{(r + c - y)T}
\]

Where:  
- \(F\) = futures price  
- \(S\) = spot price  
- \(r\) = risk-free rate  
- \(c\) = storage cost  
- \(y\) = convenience yield  
- \(T\) = time to maturity  

#### Contango
- Occurs when **futures > spot** (\(r + c > y\)).  
- Storage and financing costs push futures upward.  
- Typical when supply is ample.  

Example:  
\[
S = 100, \quad r = 5\%, \quad c = 3\%, \quad y = 0
\]  
\[
F = 100 \times e^{0.08} \approx 108.3
\]  
Futures curve slopes upward.  

#### Backwardation
- Occurs when **futures < spot** (\(y > r + c\)).  
- High convenience yield = value of immediate possession (e.g., during shortages).  

Example:  
\[
S = 100, \quad r = 5\%, \quad c = 3\%, \quad y = 10\%
\]  
\[
F = 100 \times e^{-0.02} \approx 98.0
\]  
Futures curve slopes downward.  

---

### 3. Takeaway
- Futures markets are **not casinos** but stabilizing mechanisms.  
- **Contango** = normal state (costs > convenience).  
- **Backwardation** = scarcity state (convenience > costs).  
- Farmers, bakeries, and other hedgers rely on these dynamics to **lock in certainty**.  

