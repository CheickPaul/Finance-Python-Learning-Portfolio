# CHAP I : Introduction to Excell

--
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


<ins>**Import a CSV (stock data)** </ins>

- Data menu → From Text/CSV (older: Data → From Text).
- Import wizard:
  - Delimited → check Comma (,)
 

> Trader tip: keep columns as **Date, Time, Open, High, Low, Close, Volume** (in that order) to simplify formulas & charts.

--

<ins>**Quick formatting (Home)** </ins>

- Font: select `A1:G1` → Cambria, Size 14
- Style: Ctrl+B (bold), Ctrl+I (italic), Ctrl+U (underline)
- Text color: Font Color
- Background: Fill Color

> Better readability = fewer operational-risk errors

--


<ins>**Number formats**  </ins>

- Number Format: General (default), Number, Date, Time, Currency, Percentage, etc.
- Decimals: Increase Decimal / Decrease Decimal

> Standardize decimals (e.g., **2 d.p.** for prices, **4 d.p.** for rates) for consistent **P&L** (profit & loss).

---

<ins>**Filter the data (Data → Filter)** </ins>

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

--

<ins>**Sort the data (Data → Sort)** </ins>

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

---

<ins>Freeze Panes (View → Freeze Panes)</ins>

 **View** → section **Window** → click **Freeze Panes**.  
 
then 3 options :

- **Freeze Top Row** → keeps **row 1** visible when scrolling **down**.
  
- **Freeze First Column** → keeps **column A** visible when scrolling **right**.
  
- **Freeze Panes** → freezes **everything above and left** of the **active cell**.  
  *Example: if the active cell is **C2**, Excel freezes **row 1** and **columns A & B**.*

**Unfreeze:** **View → Freeze Panes → Unfreeze Panes**

> Great when scanning thousands of **intraday bars** (you keep headers/dates in view while scrolling).

--

<ins>**Useful shortcuts** </ins>

- **Ctrl+B / Ctrl+I / Ctrl+U**: bold / italic / underline
- **Alt, H, O, I**: AutoFit Column Width
- **Ctrl+1**: Format Cells dialog
- **Ctrl+Shift+L**: toggle Filter
- **Ctrl+T**: convert range to **Table** (stronger filtering/sorting + Slicers)

--

<ins>Mini exercise (OHLCV)</ins>

1. Import an OHLCV CSV.
2. Format header (Cambria 14, bold, center/middle).
3. Filter **Close > 480**, then **Volume > 10,000** (note the row count).
4. Sort **Volume** (*Largest to Smallest*) and note time of the peak.
5. **Freeze Top Row** + **Freeze First Column**.
6. Save as **.xlsx** to preserve formats.

---

<ins>Trader vocab (with brief explanation)</ins>

- **Price discovery**: process by which markets find a “fair” price (supply/demand).
- **Noise (bruit)**: variability with little information content.
- **P&L**: profit & loss (gains/losses).
- **Outlier**: extreme observation that can skew analysis.
- **Screening**: filtering a universe to focus on candidates of interest.



---
# Chap III :   Charts in Excel

---
# Chap IV :   Courses Files



