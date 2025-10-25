# CHAP I : Introduction to Excell


# Chap II :   Data formatting

Data formatting enables good data hygiene, reducing noise and improving price discovery

## <ins>Quick Summary</ins>

- Proper **data formatting** ⇒ better **data hygiene** (clean structure), **lower noise**, improved **price discovery**.
- **Filters are cumulative (AND)** across columns; use **Custom Filter** or a **helper column** for **OR** logic.
- **Sort** safely: always check **“My data has headers”** to protect header row and sort by field names.
- **Freeze Panes** (View → Freeze Panes) to keep headers/dates visible when scrolling large OHLCV tables.
- **Standardize number formats/decimals** (prices=2 d.p., rates=4 d.p.) for consistent **P&L** (profit & loss).
- Clean formatting ⇒ higher **readability** ⇒ fewer **operational-risk (ops risk)** errors during handling.
- Handy shortcuts: **Ctrl+Shift+L** (Filter), **Ctrl+T** (Table), **Alt,H,O,I** (AutoFit), **Ctrl+1** (Format Cells).


## <ins>**Import a CSV (stock data)** </ins>

- Data menu → From Text/CSV (older: Data → From Text).
- Import wizard:
  - Delimited → check Comma (,)
 

> Trader tip: keep columns as **Date, Time, Open, High, Low, Close, Volume** (in that order) to simplify formulas & charts.



## <ins>**Quick formatting (Home)** </ins>

- Font: select `A1:G1` → Cambria, Size 14
- Style: Ctrl+B (bold), Ctrl+I (italic), Ctrl+U (underline)
- Text color: Font Color
- Background: Fill Color

> Better readability = fewer operational-risk errors




## <ins>**Number formats**  </ins>

- Number Format: General (default), Number, Date, Time, Currency, Percentage, etc.
- Decimals: Increase Decimal / Decrease Decimal

> Standardize decimals (e.g., **2 d.p.** for prices, **4 d.p.** for rates) for consistent **P&L** (profit & loss).



## <ins>**Filter the data (Data → Filter)** </ins>

**Where to click:** select header row → Data → Sort & Filter → Filter (or **Ctrl+Shift+L**).  
A dropdown appears on each header.

**Example 1 — Filter Close > 480**
- Click **CLOSE** dropdown → **Number Filters → Greater Than…** → enter **480** → **OK**.
- Result: Excel hides all rows with **Close ≤ 480** and shows only **Close > 480**.

**Example 2 — Add Volume > 10,000 (chaining = AND)**
- Click **VOLUME** dropdown → **Number Filters → Greater Than…** → **10,000** → **OK**.
- Filters are **cumulative**: only rows that meet **Close > 480 AND Volume > 10,000** remain visible.

**Key point (“chained” filters):** Filtering **Close** does **not** automatically filter **Volume**.  
You must set a separate criterion on **Volume**. Excel then applies **all active filters simultaneously** (logical **AND**).

**OR logic (optional)**
- Use **Number Filters → Custom Filter…** and select “is greater than” OR “is equal to”, etc.
- For advanced OR across columns, use a **helper column** with a logical formula (e.g., `=OR(Close>480, Volume>10000)`).



## <ins>**Sort the data (Data → Sort)** </ins>

**Where to click:** **Data → Sort & Filter → Sort** (opens Sort dialog).

**Check “My data has headers” — what it means**
- If the first row contains **column names** (e.g., Date, Open, High, Low, Close, Volume), **check** this box.
- Excel then **excludes the header row** from sorting will let choose fields by **name** (Close, Volume), not by Column A/B/C.
- If we **don’t** check it, Excel may treat the first row as data and **scramble the header** (bad).

**Typical sort**
- Sort → check **My data has headers**
- Sort by: **Volume**
- Order: **Largest to Smallest**
- (Optional) Sort by **Cell/Font/Fill Color** to prioritize visually marked rows.

> Use-case: find **peak liquidity** (max volume), e.g., **10:35** shows **453,968**.



## <ins>Freeze Panes (View → Freeze Panes)</ins>

 **View** → section **Window** → click **Freeze Panes**.  
 
then 3 options :

- **Freeze Top Row** → keeps **row 1** visible when scrolling **down**.
  
- **Freeze First Column** → keeps **column A** visible when scrolling **right**.
  
- **Freeze Panes** → freezes **everything above and left** of the **active cell**.  
  *Example: if the active cell is **C2**, Excel freezes **row 1** and **columns A & B**.*

**Unfreeze:** **View → Freeze Panes → Unfreeze Panes**

> Great when scanning thousands of **intraday bars** (you keep headers/dates in view while scrolling).



## <ins>**Useful shortcuts** </ins>

- **Ctrl+B / Ctrl+I / Ctrl+U**: bold / italic / underline
- **Alt, H, O, I**: AutoFit Column Width
- **Ctrl+1**: Format Cells dialog
- **Ctrl+Shift+L**: toggle Filter
- **Ctrl+T**: convert range to **Table** (stronger filtering/sorting + Slicers)




## <ins>Trader vocab (with brief explanation)</ins>

- **Price discovery**: process by which markets find a “fair” price (supply/demand).
- **Noise (bruit)**: variability with little information content.
- **P&L**: profit & loss (gains/losses).
- **Outlier**: extreme observation that can skew analysis.
- **Screening**: filtering a universe to focus on candidates of interest.



---

# Chap III :   Charts in Excel


Charts (Line, Histogram, Scatter) give fast insight into **price action** (time path of prices), **distribution** (shape, skew, tails), and **cross-variable relations** (correlation).

## <ins>Quick Summary</ins>

- **Line chart** = price **vs** time → visualize **price action** and **volatility

- regimes** (periods of distinct vol levels).

- **Histogram** = distribution view (shape, skew, tails) → read the **risk profile**.

- **Scatterplot** = X–Y relation (correlation) → co-movement, patterns, outliers.

- Always set **X-axis** (time/categories) and **Y-axis** (values) correctly to reduce **ops risk** (operational risk).

- For histograms, enable **Analysis ToolPak** and choose **bins** carefully (not too wide/narrow).

- Clear labeling (titles, axes, units) improves **readability** → fewer handling errors.



## <ins>Line Chart — Close vs Time</ins>

**Goal (markets)**: track **Close** over time (trend, pullbacks, ranges).

**Steps**
1. Select the **Close** column (header click or `Ctrl + Space`).

2. **Insert → Line** (Charts).

3. **X-axis as real time**:  
   Right-click X-axis → **Select Data…** → **Horizontal (Category) Axis Labels → Edit** → select **Time** range → **OK**.

4. Axis titles (Chart Tools → Layout):  
   **Primary Horizontal Axis Title → Title Below Axis** → `Time`  
   **Primary Vertical Axis Title → Rotated Title** → `Prices`

5. Chart title: double-click → `ABC Stock`.

> **Trader tip**: For large price ranges, try **log scale** to read **returns** (proportional moves) more intuitively.



## <ins>Histogram — Volume Distribution</ins>

**Goal (markets)**: characterize **liquidity** (execution capacity with limited **slippage**), check **skew** and **tail risk**.

**Prereq**: enable **Analysis ToolPak**  
`File → Options → Add-Ins → Manage: Excel Add-ins → Go → tick "Analysis ToolPak" → OK`

**Steps**

1. Create a **Bins** column (e.g., 1,000 → 10,000 with constant step).

2. **Data → Data Analysis → Histogram → OK**
   
   - **Input Range**: **Volume** values (no header)  

    - **Bin Range**: your **Bins**  

   - **Output Options**: **New Worksheet Ply** + **Chart Output** → **OK**

4. Output = **frequency table** + **histogram chart**.

> **Trader tip**: Equal-width **bins** help compare **tails**. Too wide = loss of granularity; too narrow = **noise**.



## <ins>Scatterplot — Open vs Close</ins>

**Goal (markets)**: assess **intraday correlation** between **Open** (X) and **Close** (Y).

**Steps**

1. **Insert → Scatter (only markers)**.

2. Right-click chart → **Select Data… → Add**:  
   - **Series name**: `Open-Close`  
   - **Series X values**: **Open** range  
   - **Series Y values**: **Close** range  
   - **OK → OK**

3. Axis titles (Layout): **X = Open**, **Y = Close**.

**Reading**: upward cloud = **positive correlation**. Wide dispersion = **volatility clustering** (vol in “clusters”).



## <ins>Chart Hygiene (axes, formats, readability)</ins>

- **Axes**: consistent number formats (prices 2 d.p., rates 4 d.p.).  

- Light **gridlines**, clear **legend**, explicit **titles** (ticker, timeframe).  

- **Freeze Panes** (`View → Freeze Panes`) to keep headers visible when scrolling large OHLCV tables.



## <ins>Pitfalls to Avoid</ins>

- Using index on X-axis instead of **Time** → misleading trajectory.  

- Histogram with ad-hoc **bins** → unreadable distribution.  

- Mixed **text/number** types in time/price columns → broken axes/sorts.  

- Missing units or wrong scale (linear vs log) → misread **risk/return**.



## <ins>Useful Shortcuts</ins>

- Select column: `Ctrl + Space`  

- Duplicate chart: `Ctrl + C`, `Ctrl + V`  

- Format Cells: `Ctrl + 1`  

- AutoFit Column Width: `Alt, H, O, I`  

- Toggle Filter: `Ctrl + Shift + L`  

- New sheet: `Shift + F11`



## <ins>Mini Exercise (OHLCV)</ins>

1. **Line**: Close vs Time. Add axis labels + chart title `ABC Stock`.  
2. **Histogram**: Volume (bins 1k→10k) via **Data Analysis → Histogram** (table + chart).  
3. **Scatter**: Open (X) vs Close (Y). Add axis titles.  
4. Note two **market** observations:  
   - (i) a **price action** feature (trend/range)  
   - (ii) a distribution (skew/tails) or **correlation** takeaway.  
5. Keep **Freeze Top Row + First Column**; save as **.xlsx**.



## <ins>Trader Vocab (with brief explanations)</ins>

- **Price action**: raw price movement (no indicators).  

- **Liquidity**: ability to execute with limited **slippage** (execution gap).  

- **Skew**: distribution asymmetry (heavier tail on one side).  

- **Tails**: distribution extremes (rare, high-impact events → **tail risk**).  

- **Volatility clustering**: vol tends to persist in “clusters”.  

- **Correlation (ρ)**: co-movement between two series.



## <ins>Data Quality (pre-chart)</ins>


- Time/Date in proper types (not text), no **duplicate timestamps**.  

- **OHLCV** column order: **Date, Time, Open, High, Low, Close, Volume**.  

- Remove **NA/blank rows** to avoid holes in charts.

---

# Chap IV :   Functions in Excel
 ---
 
 PART 1
 
 ---
 
 Excel functions + proper cell **referencing** lead to faster analysis and fewer **operationals errors** 

# <ins>Functions in Excel – Part I</ins>

## 1 Introduction
In the previous video, we learned how to visualize data in Excel and how it can be plotted on charts.  
In this video, we will learn about **referencing** and various **inbuilt functions**.

## 2 Referencing (Références de cellule)
Often in data analysis, one value is used in multiple cells.  
If this value changes, it should automatically update everywhere.  
Excel allows this through **cell referencing**.

### Relative Reference
**Example:**
- Cell `A1` contains `22`.
- In `C1`, type `=A1` → displays `22`.
- If you change `A1`, `C1` updates automatically.
- When copied down (`C2`, `C3`, …), Excel adjusts the reference automatically (`A2`, `A3`, …).  
  → This is **Relative Referencing**.

### Absolute Reference
To lock the reference (always point to `A1`), use `$`:
- Example: `=$A$1`
- When copied anywhere, still refers to `A1`.
- **Shortcut:** Press **F4** to toggle between relative/absolute references.

### Mixed Reference
- `$A1` → locks **column A**, row changes.  
- `A$1` → locks **row 1**, column changes.

## 3 Ranges & Functions
You can reference a **range** of cells as well, e.g. `=SUM(A1:D2)`.

**Common usage in trading spreadsheets (desk usage):**  
Sum up **OHLCV** data, compute **total volume**, **daily returns**, etc.

## 4 Formulas (Personnalized formulas)
A **formula** = combination of **values + operators** that returns a single value.  
Example: `=Cell1 + Cell2`  
Formulas are written in the **Formula Bar**.

## 5 Functions (Built-in functions)
Functions are **built-in formulas** that:
- take arguments (numbers or cell references),
- perform an operation,
- return a result.

**Categories:** Mathematical • Statistical • Logical

Using Excel functions speeds up **data analysis** and **decision-making** — crucial in finance for automation and reducing **operational risk** (risque opérationnel).

## 6 Logical Functions (Fonctions logiques)

### IF Function
Performs a logical test, returns one value for TRUE and another for FALSE.

**Example (Trading logic):** Check if daily return > 2%:
excel 
=IF(D3>0.02,"Above 2%","Below 2%")

 ---
 PART 2
 ---
 
# <ins>Functions in Excel – Part II</ins>

## 1 Introduction

This lesson extends Part I with practical tools for time-series analysis and data retrieval in Excel: RAND, AVERAGE, rolling averages, CORREL, rolling correlation, VLOOKUP, and OFFSET. It also introduces standard deviation (sample vs population) and their rolling versions — key in finance for measuring volatility (risk), momentum (trend), and correlation (co-movement).


## 2 Random Numbers & Averages

### 2.1 Random Numbers (simulations)

Generate uniform random values in (0,1): `=RAND()`

Generate random integers between two bounds (e.g., 1–100): `=RANDBETWEEN(1,100)`

Use case: basic Monte Carlo simulations for portfolio P&L or price paths.


### 2.2 Average (mean)

Arithmetic mean of a range: `=AVERAGE(D3:D22)`

Trading usage: average daily return, average traded volume.


### 2.3 Rolling Average (moving average)

Daily returns in column D, 20-day window (place in E22 and fill down):  
`=IF(ROW()<22,"", AVERAGE( INDEX($D:$D,ROW()-20+1) : INDEX($D:$D,ROW()) ))`

Replace 20 with your window size n. The IF prevents partial windows. Use as a trend filter (noise reduction).


## 3 Standard Deviation (Volatility)

### 3.1 Sample vs Population

STDEV.S divides by (n−1): unbiased estimator for a sample (estimation context).  
`=STDEV.S(D3:D22)`

STDEV.P divides by n: for the entire population (rare in markets).  
`=STDEV.P(D3:D22)`

Rule of thumb: use STDEV.S for realized volatility estimated from sample returns.


### 3.2 Rolling Standard Deviation (rolling vol)

20-day rolling volatility in F22, fill down:  
`=IF(ROW()<22,"", STDEV.S( INDEX($D:$D,ROW()-20+1) : INDEX($D:$D,ROW()) ))`

Interpretation: short-term dispersion; a common risk proxy.


## 4 Correlation

### 4.1 Static Correlation

Correlation between two series (e.g., D and E):  
`=CORREL(D3:D252, E3:E252)`

Interpretation: linear co-movement (rho). Useful for hedging, diversification.


### 4.2 Rolling Correlation

20-day rolling correlation in G22, fill down:  
`=IF(ROW()<22,"", CORREL( INDEX($D:$D,ROW()-20+1):INDEX($D:$D,ROW()), INDEX($E:$E,ROW()-20+1):INDEX($E:$E,ROW()) ))`

Use case: monitor regime shifts or correlation breakdowns and adjust hedges.


## 5 Lookup & Reference Functions — VLOOKUP and OFFSET

### 5.1 VLOOKUP

Syntax: VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])

- lookup_value: value to search (e.g., ticker).

- table_array: table to search; key must be first column.

- col_index_num: 1-based column number to return.

- [range_lookup]: FALSE = exact match (recommended), TRUE = approximate (sorted first col required).

Example (exact match, return Close price):  
`=VLOOKUP($A2, $H$2:$L$1000, 3, FALSE)`

Tip: lock the table range with $ to keep references stable when filling down.


### 5.2 OFFSET (dynamic ranges)

Syntax: OFFSET(reference, rows, cols, [height], [width])

Returns a range offset from a starting reference. Powerful for dynamic windows but volatile (recalculates frequently).

Example: last n observations’ average; n stored in $B$1:  
`=AVERAGE( OFFSET( D3, COUNTA($D:$D)-$B$1, 0, $B$1, 1 ) )`

Performance note: prefer INDEX-based rolling formulas for large models.


## 6 Rolling Formula Patterns (INDEX-based, non-volatile)

### 6.1 Rolling Average

`=IF(ROW()<($R$1), "", AVERAGE( INDEX($D:$D, ROW()-$R$1+1) : INDEX($D:$D, ROW()) ))`

$R$1 holds the window length n (e.g., 20).


### 6.2 Rolling STDEV.S (realized vol)

`=IF(ROW()<($R$1), "", STDEV.S( INDEX($D:$D, ROW()-$R$1+1) : INDEX($D:$D, ROW()) ))`


### 6.3 Rolling CORREL (between D and E)

`=IF(ROW()<($R$1), "", CORREL( INDEX($D:$D,ROW()-$R$1+1):INDEX($D:$D,ROW()), INDEX($E:$E,ROW()-$R$1+1):INDEX($E:$E,ROW()) ))`


## 7 Quick Reference (Cheat Sheet)

- RAND() → random value (0–1) for simulations.

- AVERAGE(range) → mean (signal smoothing).

- Rolling AVERAGE → moving-window trend filter.

- STDEV.S / STDEV.P → sample vs population volatility (use S for estimation).

- Rolling STDEV.S → rolling realized volatility.

- CORREL(r1,r2) → static correlation.

- Rolling CORREL → dynamic co-movement tracking.

- VLOOKUP(value, table, col, FALSE) → exact-match table retrieval.

- OFFSET(ref, rows, cols, [h], [w]) → dynamic ranges (use carefully).

Operational note: INDEX-based rolling windows reduce volatile recalculations, improving model stability and lowering operational risk (process errors, latency).


---
# Chap IV :   Courses Files



