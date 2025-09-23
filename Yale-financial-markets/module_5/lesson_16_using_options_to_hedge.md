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
- **VIX = volatility fear / SKEW = crash fear** → together they give a fuller picture of market sentiment.  

---

# Reflections on Hedging

### Stop-Loss Inefficiency and Option Hedge
I have already experienced situations where my stop-loss was ineffective due to **slippage during major economic announcements**.  
For a long time, I thought the solution was simply **not to trade on days of high-impact releases**.  
Now I realize that to cancel this risk, the right approach is to **hedge with options on expected announcement days**.  
This way, even if the market gaps, the option acts as insurance and sets a floor to my loss.  

Sometimes my setups required a **large stop-loss**, and I used to avoid taking these trades.  
With an option hedge, I can now take them and reduce my risk — it is as if I **lower the theoretical loss** I am willing to accept.  

---

### Hedging by Volatility
On days of expected **high volatility**, the main challenge is that we **cannot know the direction** of the market move.  
Using **straddles or strangles** can be effective in such cases:  
- They benefit if the market makes a large move in either direction.  
- They reduce exposure to “directional uncertainty”.  
- The cost is the option premium, but it buys protection against both tails.  

---

### Idea of a Scenario-Based Hedging Dashboard
It is not enough to test a single path when comparing Stop-Loss vs Put.  
Monte Carlo allows me to simulate thousands of possible scenarios and see the full **PnL distribution**.  
This makes the analysis more realistic, since it shows how each strategy behaves under many outcomes, not just one.  

It would also be interesting to build a **dashboard** that groups all these PnL simulations:  
- Inputs: lot sizes, chosen coverage products (puts, calls, straddles, etc.), market scenarios.  
- Output: simulated PnL distributions and risk metrics.  
Such a tool would make hedging decisions more objective and systematic.  

---

### Interest Rate Risk and Vega Risk
In fixed income trading, **interest rate risk** is central: when rates rise, bond prices fall.  
Options like swaptions or puts on Treasury futures can be used to hedge this exposure.  

Another important dimension is **Vega risk**: the value of an option depends on implied volatility.  
If implied volatility decreases, the time value of the option shrinks, and its price can drop even if the underlying does not move.  
This means that holding a long option is not only a bet on direction, but also a bet on volatility staying high or increasing.  
