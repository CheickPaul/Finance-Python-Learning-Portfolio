# Lesson – Using Options to Hedge

## Hedging with Options vs Stop-Loss Orders

- **Put Option**  
  - Acts as insurance by setting a **floor on losses**.  
  - If stock price falls below strike, you exercise the put.  
  - Cost: upfront **premium**.  

- **Stop-Loss Order**  
  - Instruction to broker: sell if stock falls below a certain level.  
  - Appears free (only transaction costs).  
  - Risk: execution at worse prices (slippage), whipsaw trades (sell low, buy high).  

---

## Intel Case Example

- Stock price = **$31.63**  
- Investor sets stop-loss at **$20**  
- Scenario:  
  - Price dips to $19 → broker sells (below target).  
  - Price rebounds to $21 → investor may re-enter.  
  - Next day, falls again → repeated losses (sell low / buy high).  

**Contrast**: a put at strike 20 locks in insurance without repeated trading.  

---

## Why Put Protection May Be Superior

- **Stop-Loss Limitations**  
  - No guarantee of execution at chosen price.  
  - Exposes investor to whipsaws in volatile markets.  

- **Put Advantage**  
  - Certainty of payoff if strike breached.  
  - Cleaner hedge, though requires premium.  

**Decision** = trade-off between **premium cost** and **potential trading losses**.  

---

## Market Fear & the CBOE SKEW Index

- **Definition**: SKEW measures perceived tail risk using **out-of-the-money put prices**.  
- High SKEW = crash protection expensive → market is worried.  
- Historical notes:  
  - Spikes around events like 1987 crash, 1998 Russian debt crisis.  
  - Useful for **30-day risk forecasting**, not for multi-year crashes (e.g., 1929).  

---

## VIX vs SKEW: Interpreting Market Sentiment

- **VIX** = “Fear Gauge” → reflects **expected average volatility** (nervousness of daily market).  
- **SKEW** = “Tail Risk Gauge” → reflects **fear of extreme crashes** (black swans).  

### Combined Interpretation
- **VIX high + SKEW low** → market panics in short term, but no fear of a crash.  
- **VIX low + SKEW high** → market looks calm, but investors quietly fear a **big shock**.  

---

## Takeaway

- Hedging can be done with **stop-loss orders (cheap but unreliable)** or **put options (costly but certain)**.  
- Option markets provide **risk sentiment signals** through indices like VIX and SKEW.  
- **Insurance in markets is never free** → balance option premium vs. potential stop-loss inefficiencies.  

