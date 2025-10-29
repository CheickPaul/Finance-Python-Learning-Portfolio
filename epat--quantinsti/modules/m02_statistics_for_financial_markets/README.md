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

| Scenario | Excel formula (EU `;`) to place on the **Today** row | Expected output |
|---|---|---|
| BUY (*golden cross*) | ```excel
=IFS(
  AND(COUNT(Q260:R261)=4; Q260<R260; Q261>R261); "BUY",
  AND(COUNT(Q260:R261)=4; Q260>R260; Q261<R261); "SELL",
  TRUE; "-"
)
``` | **BUY** |
| SELL (*death cross*) | ```excel
=IFS(
  AND(COUNT(Q260:R261)=4; Q260<R260; Q261>R261); "BUY",
  AND(COUNT(Q260:R261)=4; Q260>R260; Q261<R261); "SELL",
  TRUE; "-"
)
``` | **SELL** |

---

#### 3) **Signal (SIGN method)** — ultra-compact (trader-style)

> Idea: compare the **sign** of *(MA30−MA100)* today vs yesterday to detect a true cross.  
> Output: **2** = golden cross (BUY), **−2** = death cross (SELL), else no trade.

| Scenario | ΔSIGN (numeric) — Excel formula (EU `;`) on **Today** | ΔSIGN value | Text mapping from ΔSIGN | Final signal |
|---|---|---:|---|---|
| BUY (*golden cross*) | ```excel
=IF(COUNT(Q260:R261)=4; SIGN(Q261-R261) - SIGN(Q260-R260); "")
``` | **2** | ```excel
=IF(S261=2; "BUY"; IF(S261=-2; "SELL"; "-"))
``` | **BUY** |
| SELL (*death cross*) | ```excel
=IF(COUNT(Q260:R261)=4; SIGN(Q261-R261) - SIGN(Q260-R260); "")
``` | **-2** | ```excel
=IF(S261=2; "BUY"; IF(S261=-2; "SELL"; "-"))
``` | **SELL** |

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

-(1) Calculate Gain and Loss
-(2) Calculate Avg Gain / Avg Loss (rolling 14 days)
-(3) Calculate MAR (ratio : Avg Gain/ Avg Losses )
---

# <ins>Basic Strategy Construction</ins>

---

<h1 align="center">SECTION 2 : BASIC STATISTICS</h1>

---

<h1 align="center">SECTION 3 : Practical session Basics Statistics</h1>


