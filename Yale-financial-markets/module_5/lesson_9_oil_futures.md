# Lesson – Oil Futures

## Key Concepts

- **Light Sweet Crude Oil (WTI)** is the benchmark futures contract at **NYMEX**; **Brent** is the global benchmark at ICE (London).  
- **Contract size**: 1,000 barrels. Futures are **physically delivered**, though most traders close positions before expiry.  
- **Futures curve** often in **contango** due to:
  - Interest rates
  - Storage costs
  - Expectations of future oil prices  
- Oil has **natural storage in the ground**; above-ground storage is limited and costly.  
- Historically:
  - Prices artificially stabilized by **Texas Railroad Commission** (1917–1970).  
  - Post-1973: volatility surged after end of US production controls.  
- **OPEC (founded 1960)** acted as a cartel, driving major oil shocks:
  - 1973 Arab embargo (Yom-Kippur war).  
  - 1979–80 Iranian Revolution + Gulf War.  
- **Strategic Petroleum Reserve (SPR)** ≈ 60 days supply → for national security, not price smoothing.  
- **Volatility** in the 2000s driven by geopolitical shocks and fracking.  
- **Speculators**: add liquidity, forecast prices; can increase volatility but also improve efficiency.  
- **Manipulation risk** exists but is contained by exchange surveillance.  

---

## My Notes

- Oil is unique among commodities because its **main storage is underground** → above-ground storage costs are a bottleneck.  
- Futures curve analysis is key: **contango** = storage + financing costs; **backwardation** = scarcity and high convenience yield.  
- Oil market structure is a **mix of economics and geopolitics**: OPEC, wars, embargoes, and US SPR policies shape prices as much as fundamentals.  
- In practice, traders rarely go to delivery → but physical delivery rules (Cushing for WTI) still anchor futures to reality.  

---

## Reflection

- The concept of **contango and backwardation** applies strongly in oil markets.  
  The fair value formula is:  

  $$
  F = S \cdot e^{(r + c - y)T}
  $$

  where:  

  - \(S\): spot price  
  - \(r\): interest rate  
  - \(c\): storage cost  
  - \(y\): convenience yield  

- In **contango**:

$$
r + c > y \;\;\;\Rightarrow\;\;\; F > S
$$

- In **backwardation**:

$$
y > r + c \;\;\;\Rightarrow\;\;\; F < S
$$

- Oil’s volatility makes it a great case study for **macro-driven relative value trades**.  
- For my projects (e.g., UB30 arbitrage, fixed income vs commodities), oil futures provide a template for how **storage constraints and delivery rules** create arbitrage opportunities.  

