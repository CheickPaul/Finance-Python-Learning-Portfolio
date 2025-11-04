> **Disclaimer**
> These notes are my personal learning summaries based on the Statistics for Financial Markets (SFM) module I followed, **supplemented by additional personal research** and practice.
> To avoid sharing proprietary course material from QuantInsti, all examples, datasets, and diagrams have been independently created or sourced elsewhere. 
> The definitions and explanations below reflect my understanding at the time of writing and should not be taken as gospel. Please do your own research and verification. 
> I reserve the right to revise and update this document as my learning progresses and to correct any errors I discover.


> **Purpose:** The notes belows are include in my repository " Finance-Python-Learning-Portfolio". The purpose is to document my learning journey and centralizes my personal notes for future revision.
> It is non-commercial and respects QuantInsti’s IP; the aim is transparency in learning, not redistribution of course materials.



---


<h1 align="center">SECTION 1 : INTRO TO EXCEL</h1>
---

# <ins>Quant trading</ins>

- Building hypothesis ( Require Financial Knowledge)
- Testing Hypothesis ( Statistics and Programming Knowledge)
- Execution ( Programming Knowledge)

# <ins>Excel — Functions (with detailed examples)</ins>

 **Sample OHLCV Dataset**

Assume a table (A:G):

| Row | Date       | Open  | High  | Low   | Close | Volume | Spread |
|----:|------------|------:|------:|------:|------:|-------:|------:|
|  2  | 2025-10-20 | 170.0 | 172.0 | 169.5 | 171.2 | 12500  | 0.015 |
|  3  | 2025-10-21 | 171.5 | 173.4 | 170.9 | 173.0 |  9800  | 0.021 |
|  4  | 2025-10-22 | 169.8 | 170.4 | 168.2 | 168.9 | 15400  | 0.018 |
|  5  | 2025-10-23 | 173.7 | 175.0 | 173.2 | 174.3 | 11200  | 0.013 |
|  6  | 2025-10-24 | 170.4 | 171.0 | 169.1 | 170.0 |  8900  | 0.017 |

Column mapping: A=Date, B=Open, C=High, D=Low, E=Close, F=Volume, G=Spread.



## <ins>1) Math Functions</ins>

| Function | Purpose | Syntax | Step-by-step Example (using the table above) |
|---|---|---|---|
| `RAND()` | Random number in [0,1). Useful for simulation. | `=RAND()` | In H2: `=RAND()` → returns a number like `0.3721`. Recalculates on F9. |
| `RANDBETWEEN` | Random integer between bounds. | `=RANDBETWEEN(bottom, top)` | In H3: `=RANDBETWEEN(1,10)` → e.g., `7`. |
| `LN` / `LOG` | Natural log / log base *b*. | `=LN(x)` ; `=LOG(x, b)` | Log-return day 3 vs day 2: in H4: `=LN(E3/E2)` → `=LN(173.0/171.2)` ≈ **0.01046** (≈ **+1.046%**). |
| `PRODUCT` | Product of values (compounding). | `=PRODUCT(n1, n2, …)` | If J2:J4 = `+2%`, `-1%`, `+1.5%`: in H5: `=PRODUCT(1+J2,1+J3,1+J4)-1` → ≈ **+2.495%**. |
| `SUMIF` | Sum with one condition. | `=SUMIF(range, criteria, [sum_range])` | Sum of volumes where `Close>170`: `=SUMIF(E2:E6, ">170", F2:F6)` → rows 2,3,5 ⇒ **12500+9800+11200 = 33500**. |
| `COUNTIF` | Count with one condition. | `=COUNTIF(range, criteria)` | Days with `Spread<0.02`: `=COUNTIF(G2:G6,"<0.02")` → **4** (rows 2,4,5,6). |



## <ins>2) Statistical Functions</ins>

| Function | Purpose | Syntax | Step-by-step Example |
|---|---|---|---|
| `AVERAGE` | Arithmetic mean. | `=AVERAGE(numbers)` | Average of `Close`: `=AVERAGE(E2:E6)` → (171.2+173.0+168.9+174.3+170.0)/5 = **171.48**. |
| Related | Median / Std dev / Variance | `=MEDIAN(...)` / `=STDEV.S(...)` / `=VAR.S(...)` | Std dev of daily returns in H3:H6 (see logic section for returns): `=STDEV.S(H3:H6)` |



## <ins>3) Logical Functions</ins>

| Function | Purpose | Syntax | Step-by-step Example |
|---|---|---|---|
| `IF` | Test a condition and return A/B. | `=IF(test, value_if_true, value_if_false)` | Label “Up/Down”: in H2: `=IF(E2>B2,"Up","Down")`, then fill down to H6 → row 2 Up (171.2>170.0), row 3 Up, row 4 Down, row 5 Up, row 6 Down. |
| `IFS` | Multiple cases without nested IFs. | `=IFS(test1,val1, test2,val2, …)` | Classify the daily return (H = % vs prior day). First compute H3:H6: `=E3/E2-1`, `=E4/E3-1`, etc. Then in I3: `=IFS(H3<-0.02,"Large Down", H3<0,"Down", H3<0.02,"Up small", TRUE,"Large Up")` → H3≈+1.051% ⇒ Up small; H4≈−2.37% ⇒ Large Down; H5≈+3.197% ⇒ Large Up; H6≈−2.467% ⇒ Large Down. |
| `AND` / `OR` / `NOT` | Combine conditions. | `=AND(a,b)` ; `=OR(a,b)` | Signal when `Return>0` **and** `Volume>10000`: in J3: `=IF(AND(H3>0,F3>10000),1,0)` then fill down → only row 5 returns **1** (return>0 and volume 11200). |



## <ins>4) Lookup Functions</ins>

| Function | Purpose | Syntax | Step-by-step Example |
|---|---|---|---|
| `XLOOKUP` | Flexible lookup (replaces `VLOOKUP`). | `=XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found], [match_mode], [search_mode])` | Get `Volume` for a given date. If `K2` is `2025-10-23`: `=XLOOKUP(K2, A2:A6, F2:F6, "NA")` → **11200**. |
| `VLOOKUP` | Vertical lookup (key must be first column). | `=VLOOKUP(value, table, col_index, [exact])` | On block `A2:F6`: `=VLOOKUP(K2, A2:F6, 6, FALSE)` → **11200** (col 6 = Volume). |
| `INDEX` + `MATCH` | Robust combo (position + value). | `=INDEX(array, row)` + `=MATCH(value, array, 0)` | `=INDEX(F2:F6, MATCH(K2, A2:A6, 0))` → **11200**. |



## <ins>5) Dynamic Ranges / Indexing</ins>

| Function | Purpose | Syntax | Step-by-step Example |
|---|---|---|---|
| `OFFSET` | Returns a **shifted range** (volatile). | `=OFFSET(ref, rows, cols, [height], [width])` | Average of the **last 3** closes: `=AVERAGE( OFFSET(E2, COUNTA(E2:E6)-3, 0, 3, 1) )` → mean of E4:E6 = (168.9+174.3+170.0)/3 ≈ **171.067**. |
| `INDEX` (range) | Access by position (non-volatile). | `=INDEX(array, row_num, [col_num])` | Last close: `=INDEX(E2:E6, COUNTA(E2:E6))` → **170.0**. |
| `MATCH` | Return the position of a value. | `=MATCH(lookup_value, lookup_array, 0)` | Position of date `2025-10-23`: `=MATCH("2025-10-23", A2:A6, 0)` → **4** (4th entry in A2:A6). |



## <ins>6) Multiple Criteria (Bonus)</ins>

| Function | Purpose | Syntax | Step-by-step Example |
|---|---|---|---|
| `SUMIFS` | Sum with multiple criteria. | `=SUMIFS(sum_range, crit_range1, crit1, …)` | Sum `Volume` where `Volume>10000` **and** `Close>170`: `=SUMIFS(F2:F6, F2:F6, ">10000", E2:E6, ">170")` → rows 2 and 5 ⇒ **12500+11200 = 23700**. |
| `COUNTIFS` | Count with multiple criteria. | `=COUNTIFS(range1, crit1, …)` | Days with `Close>170` **and** `Spread<0.02`: `=COUNTIFS(E2:E6, ">170", G2:G6, "<0.02")` → **2** (rows 2 and 5). |


---

# <ins>Price Adjustsments & Return</ins>

## <ins>1)Adj close, Adj Factor</ins> :
Adjusted Close (Adj Close) is the closing price corrected for splits and dividends, so the series is consistent over time and reflects total-return performance. In case of split or dividends sharing the returns after this new action would be totally wrong if we did not adjust the close price. In practice we adjust the Adj Close price retrospectively.
Quick rules :
- Trading levels / OHLC analysis → **Close**
- Return / backtests / performance → **Adj Close**

Adj Factor = Close Price/ Adj Price

  ## <ins>2)Adj Prices, Adj Volume</ins> :


| Metric        | Adjusted formula           | Market comment (brief)                                      |
|---------------|----------------------------|--------------------------------------------------------------|
| **Adj Open**  | `Open_adj = Open_raw × F_p`  | F_p = price adjustment factor (splits; may include dividends for total return). |
| **Adj High**  | `High_adj = High_raw × F_p`  | Same logic for all OHLC.                                     |
| **Adj Low**   | `Low_adj = Low_raw × F_p`    | —                                                            |
| **Adj Close** | `Close_adj = Close_raw × F_p`| —                                                            |
| **Adj Volume**| `Vol_adj = Vol_raw ÷ F_p`    | Divide by F_p to offset unit change from splits (shares).    |

>  **Backward-adjusted** = rescale history so corporate actions don’t create artificial jumps.
> Volume is in **shares** (units), not dollars.


  ## <ins>3)Return, Cumulative return</ins> :

- Daily Return :(Today Adj - Yesterday Adj)/Yesterday Adj
- Cumulative Return : Adding Today's value to Yesterday's value ;
- Returns are always (Sell-buy)/Initial Investment.
---

# </ins>Technical Indicators<ins> (MA, VWAP, RSI) 

  ## <ins>1)Moving Average</ins> :

  - Calcultate the moving average of the last 30,100 or x closest days
  - When the blue line (MA30) cross the red line ( MA100) from top to BOttom, we sell
  - When the blue line (MA30) cross the red line ( MA100) from BOttom to top, we buy
    
<img width="786" height="668" alt="image" src="https://github.com/user-attachments/assets/6d5fe01e-8cac-42df-b425-af1aaa5f672c" />


### <ins>Example of different way to identify Signal wth MA</ins>

 **Dataset (raw data)**

| Scenario | Row (Date) | MA30 (Q) | MA100 (R) |
|---|---|---:|---:|
| BUY (*golden cross* — bullish crossover) | 260 (Yesterday) | 98 | 100 |
| BUY (*golden cross* — bullish crossover) | 261 (Today) | 101 | 100 |
| SELL (*death cross* — bearish crossover) | 260 (Yesterday) | 105 | 100 |
| SELL (*death cross* — bearish crossover) | 261 (Today) | 99 | 100 |

---

#### **IFS function** (crossover, text output)

> Guardrail: `COUNT(Q260:R261)=4` ensures all four cells are numeric (data quality check).

| Scenario             | Excel formula (EU `;`) to place on the **Today** row                                                                           | Expected output |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------ | --------------- |
| BUY (*golden cross*) | =IF(COUNT(Q260:R261)=4; IFS(AND(Q260<R260; Q261>R261); "BUY"; AND(Q260>R260; Q261<R261); "SELL"; TRUE; "-"); "-") | **BUY**         |
| SELL (*death cross*) | =IF(COUNT(Q260:R261)=4; IFS(AND(Q260<R260; Q261>R261); "BUY"; AND(Q260>R260; Q261<R261); "SELL"; TRUE; "-"); "-")` | **SELL**        |


---

#### 3) **Signal (SIGN method)** — ultra-compact (trader-style)

> Idea: compare the **sign** of *(MA30−MA100)* today vs yesterday to detect a true cross.  
> Output: **2** = golden cross (BUY), **−2** = death cross (SELL), else no trade.

| Scenario                | ΔSIGN (numeric) — Excel formula (EU `;`) on Today              | ΔSIGN value | Text mapping from ΔSIGN                        | Final signal |
| ----------------------- | -------------------------------------------------------------- | ----------- | ---------------------------------------------- | ------------ |
| BUY (*golden cross*)    | `=IF(COUNT(Q260:R261)=4; SIGN(Q261-R261)-SIGN(Q260-R260); "")` | `2`         | `=IF(S261=2; "BUY"; IF(S261=-2; "SELL"; "-"))` | **BUY**      |
| SELL (*death cross*)    | `=IF(COUNT(Q260:R261)=4; SIGN(Q261-R261)-SIGN(Q260-R260); "")` | `-2`        | `=IF(S261=2; "BUY"; IF(S261=-2; "SELL"; "-"))` | **SELL**     |
| No cross (flat/whipsaw) | `=IF(COUNT(Q260:R261)=4; SIGN(Q261-R261)-SIGN(Q260-R260); "")` | `0`         | `=IF(S261=2; "BUY"; IF(S261=-2; "SELL"; "-"))` | `-`          |


> Noise filter (anti-whipsaw = fewer false signals): round before `SIGN` to ignore micro-touches  
> ```excel
> =IF(COUNT(Q260:R261)=4; SIGN(ROUND(Q261-R261;4)) - SIGN(ROUND(Q260-R260;4)); "")
> ```


  ## <ins>2)VWAP-Volume Weighted Average Price</ins> :

Reminder :

<img width="687" height="776" alt="image" src="https://github.com/user-attachments/assets/52cd35b0-bf1a-4ace-8164-94b4f5a2908f" />

### <ins>VWAP Signals</ins> (mean-reversion)

**Rule**
- If **Price < VWAP** ⇒ **BUY**
- If **Price > VWAP** ⇒ **SELL**


The main reason is that we assume that VWAP is sort of  a fair price then if the market price is below, it will tend to get up and vice versa

  ***we assume the main reversion. if we assumed trend following it would change.***


Whenever we get signal, we square off the earlier position and enter a new position according to the signal

### <ins>Step by step calculations</ins> (mean-reversion)
- (1) If we have a daily volume, we must to calculate de **average daily price** between Adj High, Adj Low, Adj close
- (2) AVERAGE DAILY PRICE * VOLUME
- (3) CUMMULATIVE P*V
- (4) CUMMULATIVE VOLUME
- (5) VWAP

VERY IMPORTANT : SQUARRE OFF THE LAST SIGNAL
We “square off” (close the position) on the last line so the return reflects a complete round-trip and the performance is measurable in cash.

  ## <ins>3)VWAP On a rolling period</ins> :
Instead of computing cummulative P*V, we do it on a rolling basis(e.g. 10 days)

  ## <ins>4) Relative Strength Indicator (RSI)</ins>

-Momentum gauge: relative strength of up moves vs. down moves (buying vs. selling pressure).

-Overbought/Oversold: classic thresholds at 70/30.

-Price–RSI divergences: signals of momentum rollover (loss of momentum).

- Gain : If today adj close price greater than yesterday, we calculate the spread otherwise 0.
- Losses : If today adj close price smaller than yesterday, we calculate the difference

### <ins>Step by step calculations RSI</ins>

IDEA : We sell if RSI >70. We buy if RSI <30

-(1) Calculate Gain and Loss
-(2) Calculate Avg Gain / Avg Loss (rolling 14 days)
-(3) Calculate MAR (ratio : Avg Gain/ Avg Losses )
-(4) Calculate RSI

Reminder :

<img width="562" height="105" alt="image" src="https://github.com/user-attachments/assets/562bc024-13a3-4479-ab6d-89f0e22911d6" />

-(5) SIGNAL / TRADE / INVENTORY (NET POSITION)



---

# <ins>Basic Strategy Construction</ins>

---

<h1 align="center">SECTION 2 : BASIC STATISTICS</h1>
---

# <ins>1.Basic Statistic</ins>

why stat : it helps us understand and quantify the risk associated with any investment.

# <ins>2. Probability</ins>

-Probability can be defined as the chance an event occurs
-P(Event)=(count of Event = true)/ total number of event outcomes

## <ins>2.1 Joint Events Probability / Conditional Probability</ins>

| Relation                                 | Simple definition                                           | Intersection / Conditional formula               | Trader intuition (market vocab)                                                                                        |
| ---------------------------------------- | ----------------------------------------------------------- | ------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| **General (always true)**                | Holds without any assumption                                | $P(A\cap B)=P(A),P(B\mid A)=P(B),P(A\mid B)$     | Read via **conditioning** (information flow): “probability of B *given A*”.                                            |
| **Conditional probability** $P(B\mid A)$ | Probability of **B given A** (info update)                  | $P(B\mid A)=\frac{P(A\cap B)}{P(A)} ;; (P(A)>0)$ | Measures **edge** (stat advantage) from A: after **volume spike (A)**, chance of **breakout (B)**.                     |
| **Independent**                          | A does **not** change the probability of B (and vice versa) | $P(A\cap B)=P(A),P(B)$                           | No **information flow** between signals → no extra **edge** from conditioning.                                         |
| **Dependent**                            | A **does** change the probability of B (and/or vice versa)  | $P(A\cap B)=P(A),P(B\mid A)=P(B),P(A\mid B)$     | **Linked signals** (co-movement). If positive association: $P(A\cap B) > P(A)P(B)$ (combined edge); if negative: $<$ . |
| **Mutually exclusive (disjoint)**        | Cannot occur together                                       | $P(A\cap B)=0$                                   | “Never together” (limit case of anti-co-occurrence).                                                                   |

*Example 1. :*

 Setup (events & probabilities)
 
- A: Volume spike (rare signal), P(A)=0.20
- B: Breakout (price move), P(B)=0.30

Independent (no information flow)
   P(A∩B)=P(A)P(B)=0.20×0.30=0.06

Dependent (positive association) breakout more likely after a spike with P(B∣A)=0.50
    P(A∩B)=P(A)P(B∣A)=0.20×0.50=0.10


 *Example 2. :* Disjoint (mutually exclusive on the same asset / same bar)


- A: Daily return > 0 (close above open).
- B: Daily return < 0 (close below open).

  P(A∩B)=0

  *Example 3. :*  Effect of Interest rates on Index - Conditional probability

  F1 : Hike days 780 days / F2 : Cut days 620 days
  - on f1 (hikes) : index down on 468 days; up on 312 days
  - on f2(cuts) : index up on 403 days ; up on 217 days
 
    -P(D∣F1​) = 468/780 = 0.6 ; P(D∣F2​) = 217/620 = 0.35 ; P(U∣F2​)= 0.65

    - Likelihood ratio:  P(D∣F1​)/P(D∣F2​) = 1.71

  ## <ins>2.2 Expected Value : Sum of { all values * their probability} </ins>
  
The EV of rolling a fair dice is 3.5. that's mean if we roll 1M times the average will be around 3.5.
In a fair value of game, the Expected Value of winning is equal to the Expected value of lossing 

# <ins>3. Visualising Data</ins>

Data in the raw form does not tell any story. Then we need to set the data in order to benefit from it. We need to summarize the data (reduction to a small number of data) ; identify what hypothesis are most likely ( mean reversion, trending,any relationship between variables)

  ## <ins>3.1 Pyramid of Data </ins>
| Level                                 | Definition                                             | Typical transforms (pipeline)                                                | Trading examples                                                                               | Deliverables                                                                             | Common pitfalls                                                                                    |
| ------------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **DATA** (raw)                        | Unprocessed facts straight from sources.               | Ingest → timestamping → deduplication → basic QC (NA/outliers).              | Tick data, OHLCV bars, L2 order book, corporate actions, macro headlines.                      | Reliable raw datasets; reproducible logs.                                                | Noise, bad timestamps, survivorship bias, incomplete fields, mixed timezones.                      |
| **INFORMATION** (structured signals)  | Cleaned/organized data with context; features.         | Resampling, normalization, feature engineering, labeling.                    | Returns (r_t), realized vol σ, VWAP, volume profile, order-flow imbalance, RSI/MAs.     | Feature tables ready for backtests; documentation of feature definitions.                | Data leakage, look-ahead bias, inconsistent calendars, over-smoothed series.                       |
| **KNOWLEDGE** (validated rules/edges) | Relationships that survive testing (statistical edge). | Hypothesis tests, backtests, cross-validation, regime checks, cost modeling. | P(down∣Fed hike), LR>1 after CPI surprise, volume spike ⇒ breakout prob ↑. | Playbook rules with KPIs: Sharpe, hit rate, payoff ratio, max DD, turnover, cost/impact. | Overfitting/p-hacking, ignoring slippage/market impact, unstable across regimes, weak sample size. |
| **WISDOM** (decision & risk)          | Executable decisions under constraints.                | Position sizing, portfolio/risk budgeting, execution algos, monitoring.      | Size with capped-Kelly, hedge via options, TWAP/VWAP scheduling, kill-switches.                | Live runbook, guardrails (limits/alerts), PnL & risk attribution, post-trade analytics.  | Breaching risk budget, poor execution (slippage), operational risk, model drift not monitored.     |

Notes (market vocab)


- Edge = statistical advantage (positive expected value).
- Data leakage : using information that wasn’t available at decision time (or is too correlated with the target). e.g., "Look-ahead" (seen in the future): computing a Friday signal using Friday’s close when the decision should be made before the close.
- Risk budget = how much risk each strategy can consume.
- Slippage/impact = execution costs that erode edge.
- Regime = market state (vol/liquidity/rates) — always test robustness across regimes.

  ## <ins>3.2 Sample and Populationn</ins>

The bigger is the random sample, the closer will be the resemblance.


# <ins>4. Moments of Data - Mean and Variance - Covariance and Correlation</ins>

| Concept                                        | Symbol / Notation              | Mathematical Formula                                                                                                               | Interpretation / Key Points                                                                                                              |
| ---------------------------------------------- | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Expected value (mean) of a variable            | E[X]                           | E[X] = Mean(X)                                                                                                                     | Long-run average value of X. This is the "expected return".                                                                              |
| Linearity of expectation (sum)                 | E[X+Y]                         | E[X+Y] = E[X] + E[Y]                                                                                                               | Always true, even if X and Y are dependent.                                                                                              |
| Linearity of expectation (linear combination)  | E[aX + bY]                     | E[aX + bY] = a · E[X] + b · E[Y]                                                                                                   | Constants a and b can be pulled out. Used for portfolio expected return.                                                                |
| Variance of a variable                         | Var(X) = σₓ²                   | Var(X) = E[(X − E[X])²]                                                                                                            | How much X fluctuates around its mean. Higher variance = higher risk / volatility.                                                      |
| Standard deviation                             | σₓ                             | σₓ = √( Var(X) )                                                                                                                   | Volatility of X. In finance we usually talk about σ as "risk".                                                                          |
| Covariance                                     | Cov(X,Y)                       | Cov(X,Y) = E[(X − E[X]) · (Y − E[Y])]                                                                                              | Cov > 0: X and Y tend to move together. Cov < 0: they tend to move in opposite directions. Magnitude depends on units.                 |
| Correlation                                    | Corr(X,Y) = ρₓᵧ               | Corr(X,Y) = Cov(X,Y) / ( σₓ · σᵧ )                                                                                                | Normalized version of covariance. Always between −1 and +1. Makes assets comparable.                                                    |
| Covariance ↔ correlation link                  | Cov(X,Y) and ρₓᵧ              | Cov(X,Y) = ρₓᵧ · σₓ · σᵧ                                                                                                          | If you know correlation and volatilities (σₓ, σᵧ), you can recover the covariance.                                                      |
| Independence (idea)                            | X ⟂ Y                          | If X and Y are independent ⇒ Cov(X,Y) = 0                                                                                          | In real markets this is rarely true because assets share common drivers (macro, flows, market sentiment).                              |
| Variance of a sum                              | Var(X+Y)                       | Var(X+Y) = Var(X) + Var(Y) + 2 · Cov(X,Y)                                                                                          | Total risk is not just "risk1 + risk2". How they co-move matters.                                                                       |
| Variance of a linear combination               | Var(aX + bY)                   | Var(aX + bY) = a² · Var(X) + b² · Var(Y) + 2ab · Cov(X,Y)                                                                          | General risk formula for any 2-position combination.                                                                                    |
| 2-asset portfolio: return                      | Rₚ = w₁ · R₁ + w₂ · R₂        | E[Rₚ] = w₁ · E[R₁] + w₂ · E[R₂]                                                                                                   | The portfolio return is the weighted sum of individual asset returns.                                                                  |
| 2-asset portfolio: variance                    | Var(Rₚ)                        | Var(Rₚ) = w₁² · σ₁² + w₂² · σ₂² + 2 · w₁ · w₂ · Cov(R₁,R₂)                                                                         | Portfolio risk depends on individual risks AND on covariance. If covariance ↓, total risk ↓ (diversification).                         |
| 2-asset portfolio: volatility (stdev)          | σₚ                             | σₚ = √( w₁² · σ₁² + w₂² · σ₂² + 2 · w₁ · w₂ · ρ₁₂ · σ₁ · σ₂ )                                                                     | Core formula for total portfolio volatility with 2 assets. This is what is actually used in risk management.                           |
| Case correlation = +1                          | ρ₁₂ = 1                        | σₚ = w₁ · σ₁ + w₂ · σ₂                                                                                                            | Zero diversification: both assets move like one single block.                                                                          |
| Case correlation = −1                          | ρ₁₂ = −1                       | You can choose w₁, w₂ so that σₚ ≈ 0                                                                                               | Almost perfect hedge: one asset offsets the other.                                                                                      |
| Why covariance matters                         | 2 · w₁ · w₂ · Cov(R₁,R₂) in Var(Rₚ) | If you assume Cov = 0 but in reality Cov > 0, you underestimate true portfolio risk.                                              | In stressed markets, many assets fall together → correlation spikes → the portfolio is riskier than expected.                          |

n asset :

| Concept                                      | Formula / Notation                                                                                         | Interpretation / Key Points                                                                                                                 |
| -------------------------------------------- | ----------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| n-asset portfolio return                     | Rₚ = w₁ · R₁ + w₂ · R₂ + … + wₙ · Rₙ                                                                        | The portfolio return is the weighted combination of the n individual asset returns.                                                         |
| Weight vector                                | w = (w₁, w₂, … , wₙ)ᵀ                                                                                       | wᵢ = portfolio weight in asset i. Typically w₁ + w₂ + … + wₙ = 1 (100% of capital invested).                                                |
| Covariance matrix                            | Σ = [ Cov(Rᵢ , Rⱼ) ]                                                                                        | Σ is an n×n matrix. Entry (i,j) is the covariance between asset i and asset j.                                                              |
| Portfolio variance (double sum form)         | Var(Rₚ) = Σᵢ Σⱼ [ wᵢ · wⱼ · Cov(Rᵢ , Rⱼ) ]                                                                  | Add up the risk contribution of every pair of assets (i,j).                                                                                |
| Portfolio variance (separated form)          | Var(Rₚ) = Σᵢ [ wᵢ² · σᵢ² ] + 2 · Σ_{i<j} [ wᵢ · wⱼ · Cov(Rᵢ , Rⱼ) ]                                        | (1) Own risk of each asset (wᵢ² σᵢ²) + (2) interaction terms between assets (diversification via covariance).                             |
| Portfolio variance (using correlation)       | Var(Rₚ) = Σᵢ [ wᵢ² · σᵢ² ] + 2 · Σ_{i<j} [ wᵢ · wⱼ · ρᵢⱼ · σᵢ · σⱼ ]                                       | Same idea but written with the correlation ρᵢⱼ between asset i and asset j, which is often more intuitive for risk management.             |
| Portfolio variance (matrix form)             | Var(Rₚ) = wᵀ · Σ · w                                                                                         | Compact notation used in quantitative finance, portfolio optimization, and risk systems.                                                   |
| Total portfolio volatility                   | σₚ = √( wᵀ · Σ · w )                                                                                        | σₚ is the standard deviation of the portfolio returns. This is the standard “risk” number of the portfolio.                               |
| Diversification (intuition)                  | Term wᵢ · wⱼ · Cov(Rᵢ , Rⱼ) for i ≠ j                                                                       | If ρᵢⱼ (and therefore Cov) is low or negative between two assets, combining them reduces total risk without necessarily reducing return.  |
| Extreme case: perfectly correlated assets    | If ρᵢⱼ = 1 for all i,j                                                                                       | All assets behave like one single “mega-asset.” No real diversification: the portfolio is just scaling the same exposure.                  |
| Extreme case: strong hedge                   | If some ρᵢⱼ are very negative                                                                               | Some assets offset the movement of others → σₚ can drop a lot. This is the logic of hedging / risk protection.                             |


## Risk Application Note (How I Use These Formulas)

(1). Volatility (σ) is my unit of risk  
   - σ of an asset (σ₁, σ₂, …) tells me how violently it moves.
   - Portfolio volatility σₚ tells me how violently my total book can move.
   - I should never judge risk only by PnL expectations. I must look at σ.

(2). Portfolio risk is not just “sum of individual risks”  
   - Portfolio variance is not just Var(asset 1) + Var(asset 2).
   - The real risk is Var(Rₚ) = wᵀ · Σ · w.
   - The covariance terms (Cov(Rᵢ,Rⱼ)) and correlations (ρᵢⱼ) tell me how positions interact.
   - Translation: even two “small” trades can create huge total risk if they move together.

(3). Correlation tells me if I am repeating the same bet  
   - High correlation (ρ close to +1) means both trades are basically the same exposure.
     → Example: I am not diversifying. I am doubling the same view.
   - Low or negative correlation means the trades behave differently.
     → This can reduce total portfolio risk.

(4). “Is this a new edge or just leverage on the same idea?”  
   - Before adding a new strategy/position, I should ask:
     - Does it increase σₚ a lot?
     - Is its correlation with my current book high or low?
   - If correlation with the existing book is very high, I am mostly scaling up the same theme (same macro bet, same regime sensitivity).
   - If correlation is low or negative, I may actually be diversifying.

(5). Hedging logic  
   - If two positions have negative correlation (ρ < 0), they can hedge each other.
   - A hedge is not “a position I like less”. A hedge is “a position that reduces σₚ”.
   - Good hedges reduce the 2 · wᵢ · wⱼ · Cov(Rᵢ,Rⱼ) part of portfolio variance.

(6). Sizing and leverage should be done from risk, not from conviction  
   - High-σ assets (or high-σ strategies) should usually get smaller weights wᵢ.
   - I can target a desired portfolio volatility (for example: “keep σₚ under a limit”).
   - Position sizing is not random: it comes from the math of Var(Rₚ) and σₚ.

(7). Production mindset (algo trading)  
   - These formulas are not academic.
   - In practice:
     - I estimate Σ (the covariance matrix of strategy/asset returns).
     - I compute σₚ = √( wᵀ Σ w ) for my current allocation.
     - I check how σₚ changes if I add a new trade.
   - If σₚ explodes, I am adding unstable risk.
   - If σₚ stays controlled or even goes down, I am improving the portfolio.

(8). Dynamic sizing
   - I don't keep the same weights forever. I adjust the weights w₁, w₂, …, wₙ.
   - Goal: for a given target return, I try to get the lowest possible total risk.
   - In math terms: I choose the weights w that make portfolio variance (wᵀ Σ w) as small as possible,
     while still hitting the return I want and staying inside my risk budget.
   - Practically:
     - I cut size in strategies that add a lot of risk but don't pay enough.
     - I increase size in strategies that bring return without adding too much correlation with the rest.
     - If two strategies are basically the same bet (high correlation), I don't size them both big.
   - This is not “I like this trade more.” It's “this weight makes the whole book safer for the same expected PnL.”

Summary:
- σ = how risky something is alone.
- ρ = how two things move together.
- wᵀ Σ w = how dangerous the full book is.
- The job is not only “find return,” it’s “control portfolio σₚ while getting return.”

# <ins>5. Application - Capital Asset Pricing Model</ins>

## <ins>5.1 Efficient Frontier - MARKOWITZ </ins>

<img width="960" height="337" alt="image" src="https://github.com/user-attachments/assets/b86dabdc-7bf4-4290-94e0-e5e5a6960d59" />


<img width="1117" height="719" alt="image" src="https://github.com/user-attachments/assets/20053ed9-07b9-482e-ac7f-469731861456" />


In this chart, I evaluate the risk and return of a two-stock portfolio. We simulate 101 hypothetical portfolios with different fractions of wealth invested in each stock. According to the chart, the portfolio with the highest return for the minimum level of risk has an expected return of 11.7% and a standard deviation of 6%. In our simulations, this corresponds to portfolio 67, which allocates 66% of the wealth to Stock A and 34% to Stock B. The efficient frontier is constructed using Markowitz’s mean–variance framework.


## <ins>5.2 Minimum-Variance Portfolio</ins>

For a given set of assets, the *minimum-variance portfolio* (min-var) is the portfolio with the **lowest possible volatility** (risk), regardless of expected return.  
On the Markowitz efficient frontier, it is the **left-most point** (smallest σ). The Min-Var (low-vol) is a reference Portfolio, the one with the lowest possible risk. 

<img width="1079" height="674" alt="image" src="https://github.com/user-attachments/assets/faebebaa-8222-418b-9fd1-e21c434a1a11" />

<img width="926" height="633" alt="image" src="https://github.com/user-attachments/assets/0114fe8d-0ea1-430f-b799-ddfa4f9104af" />


*2 Assets Portfolio (X and Y) :*

| Concept                                      | Formula                                                                                                  | Explanation                                                                                                             |
|----------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| 2-asset portfolio variance                   | σₚ² = wₓ²·σₓ² + wᵧ²·σᵧ² + 2·wₓ·wᵧ·ρₓᵧ·σₓ·σᵧ                                                             | General variance of a two-asset portfolio combining assets X and Y with correlation ρₓᵧ.                              |
| 2-asset portfolio volatility (st. dev.)      | σₚ = √(σₚ²)                                                                                             | The portfolio volatility is the square root of the portfolio variance.                                                 |
| Min-variance weight on X                     | wₓ* = (σᵧ² − ρₓᵧ·σₓ·σᵧ) / (σₓ² + σᵧ² − 2·ρₓᵧ·σₓ·σᵧ)                                                    | Optimal weight on asset X that minimizes the portfolio variance (two-asset Markowitz closed-form solution).            |
| Min-variance weight on Y                     | wᵧ* = 1 − wₓ*                                                                                           | Since the portfolio is fully invested in X and Y, the optimal weight on Y is one minus the optimal weight on X.        |
| Min-variance portfolio variance              | σₚ,ₘᵢₙ² = (wₓ*)²·σₓ² + (wᵧ*)²·σᵧ² + 2·wₓ*·wᵧ*·ρₓᵧ·σₓ·σᵧ                                               | Plug the optimal weights wₓ* and wᵧ* into the variance formula to obtain the minimum achievable portfolio variance.    |
| Min-variance portfolio volatility (st. dev.) | σₚ,ₘᵢₙ = √(σₚ,ₘᵢₙ²)                                                                                    | The minimum-variance portfolio volatility is the square root of the minimum-variance portfolio variance.              |
           |

*n Assets Portfolio :*


| Concept                                    | Formula                                                     | Explanation                                                                                                       |
|--------------------------------------------|-------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| n-asset portfolio variance                 | σₚ² = wᵀ · Σ · w                                            | Portfolio variance as a quadratic form of the weight vector w and the covariance matrix Σ.                       |
| n-asset portfolio volatility (st. dev.)    | σₚ = √( wᵀ · Σ · w )                                       | Portfolio volatility is the square root of the portfolio variance.                                               |
| Ones vector                                | 1 = (1, 1, … , 1)ᵀ                                         | 1 is an n×1 vector of ones, used to impose the “fully invested” constraint 1ᵀ · w = 1.                           |
| Global min-variance weights (vector form)  | w* = Σ⁻¹ · 1 / ( 1ᵀ · Σ⁻¹ · 1 )                            | Closed-form solution for the global minimum-variance portfolio (fully invested, no other constraints).           |
| Global min-variance portfolio variance     | σₚ,ₘᵢₙ² = 1 / ( 1ᵀ · Σ⁻¹ · 1 )                             | Plugging w* into σₚ² = wᵀ Σ w gives the minimum achievable variance on the global minimum-variance portfolio.   |
| Global min-variance portfolio volatility   | σₚ,ₘᵢₙ = √( 1 / ( 1ᵀ · Σ⁻¹ · 1 ) )                         | Volatility of the global minimum-variance portfolio.                                                             |

## <ins>5.3 Minimum-Variance Portfolio vs Current Book</ins>

Comparing the **minimum-variance portfolio** to the **current portfolio (Current PF)** helps to understand how much extra risk we are taking and whether this extra risk is compensated by a higher expected return.

- If **σ(Current PF) is close to σ(Min-Var)** and the expected return is only slightly higher, the investor is taking **more risk for a relatively small gain in return**.
- If **σ(Current PF) is much higher than σ(Min-Var)**, the portfolio is **aggressive** relative to the most diversified combination of the same assets.
- If there exists a portfolio on the efficient frontier with the **same volatility as the Current PF but a higher expected return**, then the Current PF is **inefficient** (same risk, lower return).

In practice, the min-var portfolio can be used as:

- a **low-risk anchor** (baseline allocation in a “defensive” regime),
- a **reference point** to measure how far the Current PF is from the lowest-risk configuration,
- a **diagnostic tool** to check if the Current PF is reasonably positioned on or near the efficient frontier, or if it is taking unnecessary risk for too little return.

<ins>In our numerical example </ins> :

σ(Min-Var) ≈ 5.90% with an expected return of 10.85%, while the Current PF has σ ≈ 6.00% and an expected return of 11.70%. The increase in volatility is very small (+0.10 percentage point), whereas the increase in expected return is relatively large (+0.85 percentage point). In this case, moving from Min-Var to the Current PF looks like a reasonable trade-off: slightly more risk for a clearly higher expected return, and the Current PF remains an efficient portfolio on the Markowitz frontier.


# <ins>6. Probability Distribution</ins>


---


<h1 align="center">SECTION 3 : Practical session Basics Statistics</h1>


