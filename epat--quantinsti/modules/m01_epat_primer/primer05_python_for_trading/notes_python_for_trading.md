Disclaimer These notes are my personal learning summaries based on the Python primer module I followed, supplemented by additional personal research and practice. To avoid sharing proprietary course material from QuantInsti, all examples, datasets, and diagrams have been independently created or sourced elsewhere. The definitions and explanations below reflect my understanding at the time of writing and should not be taken as gospel. Please do your own research and verification. I reserve the right to revise and update this document as my learning progresses and to correct any errors I discover.

Purpose: The notes belows are include in my repository " Finance-Python-Learning-Portfolio". The purpose is to document my learning journey and centralizes my personal notes for future revision. It is non-commercial and respects QuantInsti’s IP; the aim is transparency in learning, not redistribution of course materials.
 
 # TABLE OF CONTENTS


### SECTION 1 - Intro :
 how python is used in trading desk 
### SECTION 2 - Variables & Packages :
Store data in variables and usebasic libraries (math, spicy) for numeral work
### SECTION 3 - Time Value of Money :
 compute present value and future value of cash flows in Python
### SECTION 4 - Data Structure :
Use lists, tuples and dictionaries to organise market data
### SECTION 5 - Market Data and Charts :
Import price series and plot line charts and candlestick charts
### SECTION 6 - Functions : 
write function to automate repetitive trading calculations
### SECTION 7 - NumPy :
Use NumPy arrays for fast vectorised calculations ( returns, volatility,etc)
### SECTION 8  - Pandas :
Use DataFrames to manipulate time series ( resample, join, rolling stats)
### SECTION 9 - Controls and condition : 
Use if, for, while to code simple trading rules and signal
### Section 10 - Environment Setup :
Install Python locally and run codes for trading experiments

---

## Section 1. <ins>Intro</ins>


**Key ideas:**
- **Algorithmic trading** is about codifying a trader’s behaviour into a set of rules that can be executed automatically on the exchange (order execution logic).
- **Quant trading** is about trading strategies built on **statistics and modelling** (math-backed trading models).
- **Algo trading a subset of quant trading**; **automated trading** is when the algo places orders on behalf of the human without manual clicks.
- A typical day on an algo desk mixes **operations (reports)**, **research to improve live strategies**, and **development of new strategies**.
- **Why Python?**  
  -(1) We use it because is a rich ecosystem of **libraries** for data, stats, ML and infrastructure (we do not need to reinvent the wheel).  
  -(2) The new Machine Learning packages are released in Python first, then ported to R/others.  
  -(3) Python code is **production-ready**: you can deploy it, unlike Excel sheets.  
  -(4) There is a huge **community support** → any error or question, someone has already faced it.
  -(5) Compared to older tools (C, MATLAB, R, etc.), Python is easier to learn, faster to prototype with, and better suited to **data science / quant trading**.
-(6)To start, we learn the basics (syntax, variables, if-conditions, loops, functions) and apply them to **small trading projects.

---

## Section 2.

### <ins>Variables, object references and operator</ins>

 **Variable** is a **name** that points to a value stored in memory

  **Object** could be everything : number, strings, list, function etc. An object has a **type** (int for "integer", float for " floating point number or decimal number", str for "string or sequence characters" and list "for exemple list of float, list of int, list of str"),a **value**, and a **location in memory**
 exemple : price = 105.5. In python, price is a variable pointing to 105.5
  example : 
 ```python    
  price = 105.50   # 105.50 is a float object in memory
  symbol = "AAPL"  # "AAPL" is a string object in memory
```

**Object reference**: A variable does not store the value directly, it store a **reference** to an an object in memory. 

Example:
  ```python
  prices = [100, 101, 102]  # list object in memory
  ref = prices              # 'ref' is another reference to the *same* object
  ref.append(103)
  print(prices)             # [100, 101, 102, 103]

Both prices and ref point to the same list object, so modifying one also changes the other.
```
### <ins>The Use of Jupiter</ins>
Jupiter is a core tool. it´s an interactive document that mixes **English explantion** and **Python code**:

<img width="618" height="724" alt="image" src="https://github.com/user-attachments/assets/8949ec43-5b10-4770-ab12-e9bcc7156111" />

<img width="477" height="740" alt="image" src="https://github.com/user-attachments/assets/e641321f-5b63-4b0f-b19f-96add738cd3b" />

<img width="414" height="666" alt="image" src="https://github.com/user-attachments/assets/b7c6412b-de57-4f96-866e-987fe953678c" />

<img width="460" height="744" alt="image" src="https://github.com/user-attachments/assets/5d9afd4c-3afc-4658-8121-0fec63851663" />

<img width="469" height="760" alt="image" src="https://github.com/user-attachments/assets/bf98e281-ef36-428e-80ec-4d8ac0bda08d" />

""" XXXXXXX """ represents the chain of characters (string)  & # is the real comment 

return → sends a value back to the caller (can be stored and reused in further calculations).
print → only displays the value on screen (for humans / debugging).

### <ins> Modules,Packages & Libraries</ins>

| Concept                   | Short definition                                                                 | Example code                            | Trader / quant view (use case)                                  |
|---------------------------|----------------------------------------------------------------------------------|-----------------------------------------|------------------------------------------------------------------|
| **Module**                | A single `.py` file containing Python code (functions, classes, variables,object).      | `import math`                           | One tool-box file: your own `trading_utils.py` for returns, PnL, risk. |
| **Package**               | A collection of modules grouped in a folder (often with `__init__.py`).          | `import numpy` / `import pandas`        | Bigger tool-set: arrays, stats, time series, plotting etc.       |
| **Library**               | General term for a reusable set of code (often one or more packages).            | “NumPy library”, “Pandas library”       | “Library” and “package” are often used interchangeably in Python. |
| **Python Standard Library** | Built-in collection of essential modules that ship with Python.                 | `import math`, `import datetime`, `import os` | Core utilities available without extra installation (dates, filesystem, math). |
| **NumPy alias `np`**      | Short name (alias) used when importing NumPy.                                    | `import numpy as np`                    | Standard shorthand in quant code: `np.array`, `np.mean`, `np.std`, etc. |

example : 

| Code / keyword                    | Simple explanation                                                                                                      |
|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| `dir(math)`<br>`print(dir(math))` | We use `dir(math)` to list all available names (functions, constants, etc.) inside the `math` module. For example, we can see tools like `math.log`, `math.exp`, `math.sqrt`, `math.pi` that are useful for pricing, returns and discounting (basic market math toolbox). |
| `pip install yfinance`            | We use `pip install yfinance` in the terminal to install an **external package** that is not included by default (here, `yfinance` is often used to download historical market data from Yahoo Finance). Once installed, we can `import yfinance as yf` in our code. |
| `import numpy as np`             | We import the **NumPy package** and give it the alias `np`. The alias is a short name used to refer to the package. In quant code, `np` is standard: we write `np.array`, `np.mean`, `np.std` instead of `numpy.array`, etc. |
| `import scipy as sp`             | We import the **SciPy package** and give it the alias `sp`. SciPy is built on top of NumPy and provides more advanced tools: optimisation, statistics, numerical integration, etc. We typically use it for model calibration, statistical tests and risk models. |
| **Alias (general idea)**         | An **alias** is just an alternative short name for a module or package. Syntax: `import module_name as alias`. We use aliases to make code shorter and easier to read, especially for libraries we call all the time (e.g. `import pandas as pd`, `import numpy as np`, `import scipy as sp`). |
| `np.diag(...)`                   | NumPy function that works with the **diagonal elements of a matrix**. We use it frequently in linear algebra tasks such as working with covariance matrices or risk models. |
| `np.cos(...)`                    | NumPy cosine function (vectorised). It applies the cosine to an entire array at once, which is useful in numerical methods and simulations. |

---
## Section 3.

### <ins>Time Value of Money (TVM)</ins>

| Concept                  | Simple definition (market style, **we** voice)                                                       | Example from the lesson (how **we** see it)                                                  |
|--------------------------|------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| Time Value of Money (TVM)| We say money today is worth more than the same amount in the future (inflation + return opportunity).| We know 1,000 USD today is not equal to 1,000 USD in one year.                             |
| Inflation                | We see inflation as a general price increase that reduces our **purchasing power**.                 | With 4% inflation, we treat our 1,000 USD as having the buying power of 960 USD in 1 year. |
| Present Discounted Value | We prefer cash today, because uninvested cash loses value over time (it is “discounted” in future). | If we keep 1,000 USD in a cupboard, we effectively lose 40 USD of value with 4% inflation. |
| Future Value (FV)        | We look at FV as the value of money at a future date, given an interest / growth rate.              | If we invest 1,000 USD at 5%, we get a future value of 1,050 USD after one year.           |
| Nominal return           | We call the raw % return in currency terms the **nominal return** (before inflation).               | On a 1,000 USD bond at 5%, we book a nominal return of 50 USD.                             |
| Real return              | We use **real return** for the return after removing inflation (true gain in purchasing power).     | We take 50 USD nominal − 40 USD inflation effect, so we keep a real return of 10 USD.      |
| Risk-free / sovereign bond| We treat a sovereign bond as our proxy for **risk-free** (very low default risk) rate.             | We park 1,000 USD in a sovereign bond yielding 5% per year.                                |
| Buying power             | We focus on what our cash can actually buy in goods/services (real economic value).                 | We know 1,000 USD today buys more than 1,000 USD in one year if inflation is 4%.           |

### <ins>Compounding in Time Value</ins>
| Concept        | How we describe it (market style, using “we”)                                         | Example from the lesson                            |
|----------------|----------------------------------------------------------------------------------------|---------------------------------------------------|
| Compounding    | We let interest earn more interest (we reinvest the coupons/interest payments).        | We reinvest the 25 USD interest for the next 6M.  |
| Principal (PV) | We call this our starting capital / present value.                                     | We invest 1,000 USD in the bond.                  |
| Annual rate r  | We use r for the yearly interest rate (nominal rate).                                 | r = 5% per year.                                  |
| Periodic rate  | We divide r by the number of periods per year to get the rate per period.             | Semiannual: 5% / 2 = 2.5% per half-year.          |
| First period   | We earn interest once on the initial principal.                                       | 1,000 × 2.5% = 25 USD after 6 months.             |
| Second period  | We earn interest on principal **plus** first interest (interest on interest).          | 1,025 × 2.5% = 25.625 USD.                        |
| Future Value   | We call FV the value of our investment after all periods of compounding.              | FV = 1,025 + 25.625 = 1,050.625 USD.              |
| Extra gain     | We compare simple interest vs compounding to see the extra profit from reinvesting.   | We earn 0.625 USD more than simple 5% (1,050).    |

-Simple interest corresponds to the scenario where we do not reinvest the interest
-Coumpounding corresponds to the scenario where we reinvest the earned interest after each period.

- Relation between FV & PV 

| Case / Usage                           | Formula we use                                          | How we think about it                                  |
|----------------------------------------|---------------------------------------------------------|--------------------------------------------------------|
| Simple annual compounding              | 𝐹𝑉 = 𝑃𝑉 × (1 + 𝑟)ⁿ                                    | We compound once per year (𝑛 = number of years).      |
| General compounding (any frequency)    | 𝐹𝑉 = 𝑃𝑉 × (1 + 𝑟∕𝑛)^(𝑛⋅𝑡)                             | We compound 𝑛 times per year, during 𝑡 years.         |
| Semiannual compounding (example)       | 𝐹𝑉 = 𝑃𝑉 × (1 + 𝑟∕2)^(2⋅𝑡)                             | We compound twice per year (every 6 months).           |
| Quarterly compounding (example)        | 𝐹𝑉 = 𝑃𝑉 × (1 + 𝑟∕4)^(4⋅𝑡)                             | We compound four times per year (every 3 months).      |
| Monthly compounding (example)          | 𝐹𝑉 = 𝑃𝑉 × (1 + 𝑟∕12)^(12⋅𝑡)                           | We compound every month.                               |
| Continuous compounding | 𝐹𝑉 = 𝑃𝑉 × 𝑒^(𝑟⋅𝑡)                                     | We use the continuous limit (theoretical, in pricing). |

### <ins>Funding a future obligation </ins>

#### 1) Basic data

- Future obligation (liability): 𝐹𝑉ₗ at horizon 𝑇  
- Expected return on the saving plan: 𝑟 per period  

Annual example:  
- 𝐹𝑉ₗ = 10 000 €  
- 𝑇 = 5 years  
- 𝑟 = 5 % = 0.05  



#### 2) Step 1 – Discount the future obligation (Present Value)

We “price” the future obligation like a zero-coupon bond: we compute its present value 𝑃𝑉.

Discounting formula:

- 𝑃𝑉 = 𝐹𝑉ₗ ÷ (1 + 𝑟)ᵀ  

With the numbers:

- (1 + 0.05)⁵ ≈ 1.2763  
- 𝑃𝑉 ≈ 10 000 ÷ 1.2763 ≈ 7 835.26  

Market interpretation:  
If we invest about 7 835.26 € today at 5 % per year, we obtain 10 000 € in 5 years.  
This is the cost today of the future liability.



#### 3) Step 2 – Two ways to fund the liability

##### Case A – Single lump sum today

We invest the present value 𝑃𝑉 today:

- Amount to invest now: ≈ 7 835.26 €  
- No intermediate contributions

This is the simplest solution: a lump sum that compounds until maturity.


##### Case B – Saving plan (annuity of contributions)

We prefer to make regular contributions 𝐶 at the end of each year for 𝑇 years.  
This is a saving annuity (series of equal payments invested at rate 𝑟).

Future value of an annuity:

- 𝐹𝑉 = 𝐶 × ((1 + 𝑟)ᵀ − 1) ÷ 𝑟  

We want the future value of the saving plan to match the liability:

- 𝐹𝑉 = 𝐹𝑉ₗ  

So we solve for 𝐶:

- 𝐶 = 𝐹𝑉ₗ ÷ ( ((1 + 𝑟)ᵀ − 1) ÷ 𝑟 )  

With the numbers (𝑟 = 0.05, 𝑇 = 5):

- Accumulation factor of the annuity:  
  ((1 + 0.05)⁵ − 1) ÷ 0.05 ≈ 5.5256  
- Yearly contribution:  
  𝐶 ≈ 10 000 ÷ 5.5256 ≈ 1 809.75 €  

Interpretation:  
If we contribute about 1 809.75 € at the end of each year for 5 years,  
and the capital earns 5 % per year,  
our saving plan reaches 10 000 € at year 5 and we can pay the future obligation.



#### 4) Mindset: asset–liability matching (ALM)

1. We start from the liability (future obligation):  
   𝐹𝑉ₗ at horizon 𝑇.  
2. We discount it to find the present value:  
   𝑃𝑉 = 𝐹𝑉ₗ ÷ (1 + 𝑟)ᵀ.  
3. We choose the funding strategy on the asset side:  
   - either a lump sum today: we invest 𝑃𝑉 now,  
   - or a saving plan (annuity): we solve for 𝐶 using  
     𝐶 = 𝐹𝑉ₗ ÷ ( ((1 + 𝑟)ᵀ − 1) ÷ 𝑟 ).  

This is the core idea of asset–liability management:  
we start from future cash flows (liabilities) and design the asset cash flows that fund them.




### Variant 2 – Monthly example (monthly compounding)

We keep the same logic, but now contributions and compounding are monthly.

#### 1) Basic data (monthly)

- Future obligation (liability): 𝐹𝑉ₗ = 5 000 €  
- Horizon: 𝑇 = 3 years  
- Annual nominal rate: 𝑟ₐ = 4 % = 0.04  
- Compounding and contributions: monthly  

We define:

- Monthly rate: 𝑟ₘ = 𝑟ₐ ÷ 12  
- Total number of months: 𝑛 = 12 × 𝑇  

Numerically:

- 𝑟ₘ = 0.04 ÷ 12 ≈ 0.003333…  
- 𝑛 = 12 × 3 = 36 months  


#### 2) Monthly discounting of the obligation (Present Value)

We treat the liability like a zero-coupon with monthly compounding:

- 𝑃𝑉 = 𝐹𝑉ₗ ÷ (1 + 𝑟ₘ)ⁿ  

Here:

- (1 + 0.003333…)³⁶ ≈ 1.1275  
- 𝑃𝑉 ≈ 5 000 ÷ 1.1275 ≈ 4 433.5 € (approximate)  

Market interpretation:  
If we invest about 4 433.5 € today at 4 % per year with monthly compounding,  
we obtain 5 000 € in 3 years.


#### 3) Monthly saving plan to fund the liability

We prefer to make monthly contributions 𝐶ₘ at the end of each month for 𝑛 months.

Future value of a monthly annuity:

- 𝐹𝑉 = 𝐶ₘ × ((1 + 𝑟ₘ)ⁿ − 1) ÷ 𝑟ₘ  

To fund the liability:

- 𝐹𝑉 = 𝐹𝑉ₗ  

So:

- 𝐶ₘ = 𝐹𝑉ₗ ÷ ( ((1 + 𝑟ₘ)ⁿ − 1) ÷ 𝑟ₘ )  

With the numbers:

- (1 + 0.003333…)³⁶ ≈ 1.1275  
- ((1 + 0.003333…)³⁶ − 1) ÷ 0.003333… ≈ 38.247 (monthly accumulation factor)  
- 𝐶ₘ ≈ 5 000 ÷ 38.247 ≈ 130.7 € (approximate)  

Interpretation:  
If we contribute about 131 € at the end of each month for 36 months,  
and the capital earns 4 % per year with monthly compounding,  
the saving plan reaches 5 000 € at maturity and we can honour the future obligation.


### Annual vs monthly: quick comparison (market vocabulary)

| Dimension                | Annual                              | Monthly                                  |
|-------------------------|--------------------------------------|------------------------------------------|
| Horizon                 | 𝑇 years                             | 𝑛 months (= 12 × 𝑇)                     |
| Rate per period         | 𝑟 (per year)                        | 𝑟ₘ = 𝑟ₐ ÷ 12                            |
| Zero-coupon PV          | 𝑃𝑉 = 𝐹𝑉 ÷ (1 + 𝑟)ᵀ                | 𝑃𝑉 = 𝐹𝑉 ÷ (1 + 𝑟ₘ)ⁿ                     |
| Annuity future value    | 𝐹𝑉 = 𝐶 × ((1 + 𝑟)ᵀ − 1) ÷ 𝑟        | 𝐹𝑉 = 𝐶ₘ × ((1 + 𝑟ₘ)ⁿ − 1) ÷ 𝑟ₘ         |
| Unknown to solve for    | 𝑃𝑉 or 𝐶                            | 𝑃𝑉 or 𝐶ₘ                                 |

ALM mindset (monthly version):  
We start from 𝐹𝑉ₗ (future obligation), choose a market rate and a compounding frequency (monthly),  
then we solve either for the initial lump sum 𝑃𝑉, or for the periodic contribution 𝐶ₘ.



### <ins> Funding a retirement plan</ins>

#### 1) Define the retirement target

We first translate the retirement objective into clear cash flows:

- Current age and retirement age → working horizon 𝑇ʷᵒʳᵏ (years until retirement)  
- Target retirement income per year: 𝑊 (for example, 30 000 € per year)  
- Planned length of retirement: 𝑁 years (for example, 25 years)  
- Expected portfolio return **during retirement**: 𝑟ʳᵉᵗ (real return after inflation, if we think in real terms)  

Example (retirement objective):

- We want 𝑊 = 30 000 € per year in retirement  
- For 𝑁 = 25 years  
- With an expected real return in retirement 𝑟ʳᵉᵗ = 3 % = 0.03  


---

#### 2) Step 1 – Price the retirement income as an annuity at retirement date

At retirement, the stream of withdrawals 𝑊 during 𝑁 years is a **retirement annuity** (series of future cash flows).  
We compute its **present value at retirement date**, noted 𝑃𝑉ʀ (PV at retirement).

Present value of an annuity (at retirement):

- 𝑃𝑉ʀ = 𝑊 × ( 1 − (1 + 𝑟ʳᵉᵗ)^(−𝑁) ) ÷ 𝑟ʳᵉᵗ  

With the example:

- 𝑊 = 30 000  
- 𝑁 = 25  
- 𝑟ʳᵉᵗ = 0.03  

We get approximately:

- 𝑃𝑉ʀ ≈ 522 394 €  

Interpretation (market language):

- 𝑃𝑉ʀ is the **capital required at retirement** to finance the desired withdrawals.  
- If we arrive at retirement with about 522 394 € and we earn 3 % per year, then withdrawing 30 000 € per year for 25 years is feasible.


---

#### 3) Step 2 – Bring the cost of retirement back to today

Now we move from the **retirement date** back to **today**.

We assume an expected return **during working years** 𝑅ᵃᶜᶜ (accumulation return, for example 5 % per year),  
and a working horizon of 𝑇ʷᵒʳᵏ years until retirement.

We discount 𝑃𝑉ʀ back to today:

- 𝑃𝑉₀ = 𝑃𝑉ʀ ÷ (1 + 𝑅ᵃᶜᶜ)^(𝑇ʷᵒʳᵏ)  

Example:

- 𝑃𝑉ʀ ≈ 522 394  
- 𝑅ᵃᶜᶜ = 5 % = 0.05  
- 𝑇ʷᵒʳᵏ = 25 years  

Then:

- 𝑃𝑉₀ ≈ 522 394 ÷ (1.05)²⁵ ≈ 154 265 € (approximate)  

Interpretation:

- 𝑃𝑉₀ is the **lump sum today** that would be enough to fund the entire retirement plan,  
  if we could invest it immediately and leave it invested until retirement.


---

#### 4) Step 3 – Solve for a saving plan during working years

In practice we usually do not have 𝑃𝑉₀ available today.  
Instead, we build a **saving plan** (regular contributions during working years).

We assume:

- Annual contribution during working years: 𝐶ʷᵒʳᵏ (we want to find this)  
- Working horizon: 𝑇ʷᵒʳᵏ years  
- Expected accumulation return: 𝑅ᵃᶜᶜ  

Future value of an annual saving annuity at retirement:

- 𝐹𝑉ʷᵒʳᵏ = 𝐶ʷᵒʳᵏ × ( (1 + 𝑅ᵃᶜᶜ)^(𝑇ʷᵒʳᵏ) − 1 ) ÷ 𝑅ᵃᶜᶜ  

We want this future value to equal the capital needed at retirement:

- 𝐹𝑉ʷᵒʳᵏ = 𝑃𝑉ʀ  

So we solve for the annual contribution 𝐶ʷᵒʳᵏ:

- 𝐶ʷᵒʳᵏ = 𝑃𝑉ʀ ÷ ( ( (1 + 𝑅ᵃᶜᶜ)^(𝑇ʷᵒʳᵏ) − 1 ) ÷ 𝑅ᵃᶜᶜ )  

With the numbers:

- 𝑃𝑉ʀ ≈ 522 394  
- 𝑅ᵃᶜᶜ = 0.05  
- 𝑇ʷᵒʳᵏ = 25  

Accumulation factor of the working-phase annuity:

- ( (1 + 0.05)²⁵ − 1 ) ÷ 0.05 ≈ 47.73  

Annual contribution:

- 𝐶ʷᵒʳᵏ ≈ 522 394 ÷ 47.73 ≈ 10 945 € per year  

If we want the monthly equivalent in a rough way, we can divide by 12:

- ≈ 10 945 ÷ 12 ≈ 912 € per month  

Interpretation:

If we contribute around 10 945 € per year (about 912 € per month) during 25 years,  
and our portfolio earns 5 % per year on average,  
we arrive at retirement with about 522 394 €, which is enough to pay 30 000 € per year for 25 years at 3 % return in retirement.


---

#### 5) ALM mindset for retirement planning

We can summarise the logic as an asset–liability management (ALM) framework:

1. We **start from the liability** in retirement:  
   target income 𝑊, number of years 𝑁, retirement return 𝑟ʳᵉᵗ.  
2. We **price** this retirement income as an annuity at the retirement date:  
   𝑃𝑉ʀ = 𝑊 × ( 1 − (1 + 𝑟ʳᵉᵗ)^(−𝑁) ) ÷ 𝑟ʳᵉᵗ.  
3. We **discount** 𝑃𝑉ʀ back to today using an accumulation return 𝑅ᵃᶜᶜ and horizon 𝑇ʷᵒʳᵏ:  
   𝑃𝑉₀ = 𝑃𝑉ʀ ÷ (1 + 𝑅ᵃᶜᶜ)^(𝑇ʷᵒʳᵏ).  
4. We **design the saving plan** (asset side) that funds this liability:  
   either a lump sum today 𝑃𝑉₀, or a stream of contributions 𝐶ʷᵒʳᵏ solving  
   𝐹𝑉ʷᵒʳᵏ = 𝑃𝑉ʀ.  

In other words, we treat the retirement income as a **liability stream** and we build an **asset strategy** (saving plan + expected returns) that matches it.





<ins>Summary</ins>

| Quantity / Term          | Formula (Unicode)                                                                                   | Comment (how we use it)                                          |
|--------------------------|------------------------------------------------------------------------------------------------------|------------------------------------------------------------------|
| Future value (lump sum)  | 𝐅𝐕 = 𝐏𝐕 × (1 + 𝐫 ∕ 𝐧)⁽ⁿ⋅ᵗ⁾                                                                        | We grow one initial amount to the future.                        |
| Present value (lump sum) | 𝐏𝐕 = 𝐅𝐕 ∕ (1 + 𝐫 ∕ 𝐧)⁽ⁿ⋅ᵗ⁾                                                                        | We discount one future amount back to today.                     |
| FV – simple annual       | 𝐅𝐕 = 𝐏𝐕 × (1 + 𝐫)ⁿ                                                                                | Special case with 𝐧 = 1 (once per year).                         |
| PV of annuity (ordinary) | 𝐏𝐕 = 𝐂 × [1 − (1 + 𝐫 ∕ 𝐧)⁻⁽ⁿ⋅ᵗ⁾] ∕ (𝐫 ∕ 𝐧)                                                       | We price a stream of payments at **end** of each period.         |
| PV of annuity (due)      | 𝐏𝐕_dᵤₑ = 𝐏𝐕 × (1 + 𝐫 ∕ 𝐧)                                                                         | Same annuity, but payments at **beginning** of each period.      |
| FV of saving annuity     | 𝐅𝐕 = 𝐂 × [((1 + 𝐫 ∕ 𝐧)⁽ⁿ⋅ᵗ⁾ − 1) ∕ (𝐫 ∕ 𝐧)]                                                       | We grow regular savings (saving plan) to a future date.          |
| Required saving payment  | 𝐂ₛₐᵥₑ = 𝐅𝐕ₜₐᵣgₑₜ × (𝐫 ∕ 𝐧) ∕ [(1 + 𝐫 ∕ 𝐧)⁽ⁿ⋅ᵗ⁾ − 1]                                           | We solve for the yearly/monthly saving to hit a target 𝐅𝐕.       |
| Payment from a given PV  | 𝐂 = 𝐏𝐕 × (𝐫 ∕ 𝐧) ∕ [1 − (1 + 𝐫 ∕ 𝐧)⁻⁽ⁿ⋅ᵗ⁾]                                                        | We solve for the periodic withdrawal compatible with a fund 𝐏𝐕. |
| Continuous compounding   | 𝐅𝐕 = 𝐏𝐕 × 𝑒⁽ʳ⋅ᵗ⁾                                                                                | We grow money with continuous compounding.                       |
| Discount factor (discrete)| 𝐃(𝐭) = 1 ∕ (1 + 𝐫 ∕ 𝐧)⁽ⁿ⋅ᵗ⁾                                                                      | We discount any cash flow at time 𝐭 with discrete compounding.   |
| Discount factor (cont.)  | 𝐃(𝐭) = 𝑒⁻⁽ʳ⋅ᵗ⁾                                                                                   | We discount with a continuous rate (pricing intuit

--- 

##Section 3.

### <ins> lists</ins>
 A list is an ordered, mutable sequence of object.
The syntax of a list is a bracket + comma to separate elements
e.g.   prices = [100, 101.5, 99.8] ;  tickers = ["AAPL", "MSFT", "GOOG"] ;   mixed   = [1, 2.5, "EURUSD", True]

In python, we use the list to store series of values : prices, returns, trades etc

#### Core properties

**1. Ordered**
   Ordered means each object has a specific position called an index
   .e.g : assets = ["BOND", "STOCK", "OPTION"]
   index 0 -> "Bond"
   index 1 -> "STOCK"
   index 2 -> "OPTION"

   OR


´´´
  assets[0]   # "BOND"
  assets[1]   # "STOCK"
  assets[2]   # "OPTION"
  assets[-1]  # "OPTION" (last)
  ``


**2. Mutable**
By mutable we mean we can change, add or remvove elements

lst = [10, 20, 30]
lst[1] = 99      # [10, 99, 30]


**3. Can contain any object**
Integers, floats, strings, other lists, even custom objects
e.g. : mixed = [1, 2.5, "AAPL", False]

**4. Nestable (list of list)**
Useful for tables, matrices, portfolios.

e.g.: matrix = [[1, 2], [3, 4]] ; portfolio = [ ["AAPL", 100], ["MSFT", 50], ]

**5. Dynamic size** 
The list cand be grew or shrinked during execution

#### Core Operations we need to memorize 
### Core list operations to know by heart

| Operation           | Syntax / Example                          | Explanation                                                                  |
|------------------------------------|-------------------------------------------|-------------------------------------------------------------------------------------------|
| Create a list                      | `lst = [10, 20, 30]`                      | We build a sequence of values (like a small time series of prices).                      |
| Length (number of elements)        | `len(lst)`                                | Returns how many elements are in the list (size of the series).                          |
| Access by index                    | `lst[0]`, `lst[1]`, `lst[-1]`            | Read element at a given position: 0 = first, -1 = last (like day 1, day 2, last day).    |
| Change an element                  | `lst[1] = 99`                             | Overwrite a value at a given position (update a price, a quantity, etc.).                |
| Append at the end                  | `lst.append(40)`                          | Add a new element at the end (like adding the latest price or last trade).               |
| Insert at a given position         | `lst.insert(1, 15)`                       | Insert a value at index 1, shifting the others to the right.                             |
| Remove last element (pop LIFO)     | `x = lst.pop()`                           | Remove and return the last element (stack / LIFO: last in, first out).                   |
| Remove element at index (pop i)    | `x = lst.pop(1)`                          | Remove and return the element at index 1.                                                |
| Remove by value                    | `lst.remove(15)`                          | Remove the first occurrence of the value 15 (if it exists).                              |
| Slice: from a to b (sub-window)    | `lst[a:b]`                                | Sub-list from index a to b−1 (b excluded). Like taking a date range in a time series.    |
| Slice: from a to end               | `lst[a:]`                                 | All elements from index a to the end (e.g. all prices after a given date).               |
| Slice: from start to b             | `lst[:b]`                                 | All elements from the start up to b−1 (e.g. first b observations).                       |
| Slice: last n elements             | `lst[-n:]`                                | Last n elements (e.g. last 20 trading days).                                             |
| Copy a list (shallow copy)         | `copy_lst = lst[:]`                       | Simple way to duplicate a list (so changes on one do not affect the other).              |

---

### <ins> Stacks, Queues, Graphe & Trees</ins>

- List as stacks : A stack is a collection of objects which worsk as **LIFO** (Last In, First out). In the LIFO principle, the operation of adding object is called a push operation and the operation that consists of removing is called a pop. We respectively use the function lst.append(number to add), lst.pop() for removing the last object and lst.pop(index) by removing depending of the index

- List as queues  : A queue is a collection of object which works as **FIFO** (First in, First out). A deque allows fast appends and pops from both ends (append, appendleft, pop, popleft) which is more efficient than a plain list for queues.

  ```
  from collections import deque

# Initial queue: Roger arrives first, Novak arrives last
my_queue = deque(["Roger Federer", "Rafael Nadal", "Novak Djokovic"])

# Two more people join the queue
my_queue.append("Andre Agassi")
my_queue.append("Pete Sampras")
# deque(['Roger Federer', 'Rafael Nadal', 'Novak Djokovic', 'Andre Agassi', 'Pete Sampras'])

# First In, First Out: we remove from the left
first = my_queue.popleft()   # 'Roger Federer'
second = my_queue.popleft()  # 'Rafael Nadal'

# Now the queue starts with Novak
# deque(['Novak Djokovic', 'Andre Agassi', 'Pete Sampras'])

---

### <ins> Dictionary</ins>
A dictionary is a data structure used for mapping. it connects a key to a value. like a phone directorie that connect a name to a phone number. Regarding the wyntax. dict is enclosed in brace brackets {}. Key–value pairs separated by commas, key and value separated by :.

Example:

```python
prices = {
    "AAPL": 190.5,
    "MSFT": 340.2,
    "EURUSD": 1.0850
}
In thi example, "AAPL", "MSFT", "EURUSD" are keys and 190.5, 340.2, 1.0850 are values. to get the value we use the key as described below :
prices["AAPL"]   # 190.5
```

#### Core properties

**1. Indexed by keys, not by position**

The dictionary is indexed by the key and not by the position suc as a list (0,1,2,...)
my_list = [100, 200, 300]
my_list[0]       # 100

my_dict = {"AAPL": 190.5, "MSFT": 340.2}
my_dict["AAPL"]  # 190.5


**2. Unordered (conceptually)**
The dictionary is not indexed by the position so we do not rely on an ordered sequence of elements. Then, a dictionary is conceptualy unordered

**3. Keys are unique**
we cannot have 2 indentical keys with different values. If we reassign, the value is overwritten
d = {"AAPL": 100}
d["AAPL"] = 105   # now "AAPL" -> 105

**4. dictionaries are mutable**
we can change, add, remove elements without changing the identity of the dict.

**5. Keys must be immutable**
- Typical key types: str, int, float, tuple…
- Lists cannot be keys (because lists are mutable).


#### Core dictionary operations 


| Operation                       | Syntax / Example                                          | Explanation                                                                                  |
|--------------------------------------------------|-----------------------------------------------------------|------------------------------------------------------------------------------------------------------------|
| Create a dictionary                              | `d = {"AAPL": 190.5, "MSFT": 340.2}`                     | Map **keys → values** (e.g. ticker → last price).                                                          |
| Empty dictionary                                 | `d = {}`                                                  | Start with no data, then add keys later.                                                                   |
| Access value by key                              | `d["AAPL"]`                                               | Lookup: we use the **key** (ticker) to get the value (price).                                             |
| Add a new key/value                              | `d["GOOG"] = 2800.0`                                      | If key does not exist, we **create** it.                                                                   |
| Update an existing key                           | `d["AAPL"] = 195.0`                                       | If key exists, we **overwrite** the old value.                                                             |
| Check if key exists                              | `"AAPL" in d`                                             | Returns `True` if the key is present (like checking if a ticker is in our mapping).                        |
| Remove and return value (`pop`)                  | `price = d.pop("MSFT")`                                   | Deletes the key and returns its value (like closing a position and reading its PnL).                       |
| Delete key (no return)                           | `del d["AAPL"]`                                           | Removes key/value from the dictionary, no value returned.                                                  |
| Get all keys                                     | `d.keys()`                                                | View all keys (e.g. list of tickers or account IDs).                                                       |
| Get all values                                   | `d.values()`                                              | View all values (e.g. list of prices, PnL, exposures).                                                     |
| Get key–value pairs                              | `d.items()`                                               | Returns pairs `(key, value)` → useful for looping (ticker and its price together).                         |
| Safe lookup with default (`get`)                 | `d.get("TSLA", 0.0)`                                      | Returns value if key exists, otherwise returns default (here `0.0`) instead of raising an error.          |
| Number of entries                                | `len(d)`                                                  | Count how many key/value pairs (e.g. how many tickers/accounts we track).                                 |
| Sorted list of keys                              | `sorted(d)` or `sorted(d.keys())`                        | Returns a **new list** of keys sorted (e.g. tickers sorted alphabetically). Dictionary itself not changed. |
| Sorted list of values                            | `sorted(d.values())`                                      | Returns a **new list** of values sorted (e.g. prices or PnL sorted from lowest to highest).               |
| Sorted by key–value pairs (e.g. sort by value)   | `sorted(d.items(), key=lambda x: x[1])`                  | Returns a **sorted list of (key, value)** pairs, e.g. accounts sorted by PnL, exposures, or risk.         |

---



### <ins> Tuples and sets </ins>

A tuple is like a list but immutable.
- we can store a hetereogenous sequence of elements ( ints float,...)
- We cannot append, edit, or remove elements once the tuple is created.
- We usually use tuple when we want data that should **not change** ( protection against accidental modification),
- we want to use data as a **key in dictionnary**

Tuples are enclosed in **parentheses** `(...)`, elements are separated by commas.

example :

```
python
empty_tuple = ()
single_tuple = (10,)                # note the comma
coords = (52.5, 13.4)
mixed = ( "AAPL", 100, 190.5 )
nested = ( ("EURUSD", 1.085), ("GBPUSD", 1.27) )

```

#### Core properties

Tuples are **immutable** ( we cannot cahnge or add items), **ordered** ( we access by index like list)  and **can be used as dictionary keys** ( exampe belows)
```
prices = {
    ("AAPL", "NASDAQ"): 190.5,
    ("MSFT", "NASDAQ"): 340.2
}
```

#### Tuple operations

| Operation (what we do) | Syntax / Example                | Explanation                                    |
| ---------------------- | ------------------------------- | ---------------------------------------------- |
| Create a tuple         | `t = (10, 20, 30)`              | Fixed, ordered collection of elements.         |
| Single-element tuple   | `t = (10,)`                     | Comma is required, otherwise it’s just `10`.   |
| Length                 | `len(t)`                        | Number of elements in the tuple.               |
| Access by index        | `t[0]`, `t[1]`, `t[-1]`         | Same as lists: 0 = first, -1 = last.           |
| Slicing (sub-tuple)    | `t[a:b]`                        | From index `a` to `b-1` (like for lists).      |
| Concatenation          | `t1 + t2`                       | Combine two tuples into a new one.             |
| Repetition             | `t * 3`                         | Repeat the tuple 3 times.                      |
| Membership test        | `20 in t`                       | Check if a value is inside the tuple.          |
| Tuple unpacking        | `a, b, c = t`                   | Assign each element to a variable.             |
| Use as dictionary key  | `d[(“AAPL”, “NASDAQ”)] = 190.5` | Tuples can be keys because they are immutable. |


<ins> Sets </ins>

A set is an unordered collection with unique elements. We can store a heterogeneous collection of elements (ints, floats, strings,…).
A set cannot contain duplicates → each value appears at most once.
A set is mutable → we can add or remove elements after creation.

We usually use a set when we want:

to keep unique values (no duplicates),

to do set operations (union, intersection, difference) between datasets.

Sets are enclosed in curly braces {...} or created with the set() function.
Elements are separated by commas.

Example :

```
# ⚠ {} is an empty dict, not a set
empty_dict = {}
type(empty_dict)          # dict

# Proper empty set
empty_set = set()
type(empty_set)           # set

# Basic sets
names = {'Neo', 'Morphius', 'Trinity', 'Agent Smith', 'Oracle'}
type(names)               # set

# Duplicates are removed automatically
names = {'Neo', 'Morphius', 'Trinity', 'Agent Smith',
         'Agent Smith', 'Agent Smith', 'Oracle'}
print(names)
# {'Morphius', 'Trinity', 'Neo', 'Agent Smith', 'Oracle'}

# Using set() on an iterable (string here)
x_set = set('THEMATRIX')
print(x_set)
# {'R', 'I', 'E', 'T', 'M', 'X', 'H', 'A'}

y_set = set('THETERMINATOR')
print(y_set)
# {'R', 'O', 'I', 'E', 'N', 'T', 'M', 'H', 'A'}
```

#### Core properties

Sets are unordered (no index like lists), unique (no duplicates), and mutable (we can add/remove items).
No indexing: we do not use s[0] or slicing.
Membership is fast: x in my_set is very efficient.
Typical use cases:
clean a dataset to get unique tickers / IDs,
compare two datasets (common items, only in A, only in B),
implement logical filters via set operations.

#### Set Operation 

We assume : 
x_set = set('ABCDE')   # {'B', 'C', 'E', 'D', 'A'}
y_set = set('CDEFG')   # {'C', 'E', 'D', 'G', 'F'}

| Operation (what we do)        | Syntax / Example                    | Explanation                                         |
| ----------------------------- | ----------------------------------- | --------------------------------------------------- |
| Create empty set              | `s = set()`                         | Proper way to create an empty set.                  |
| Create literal set            | `s = {'A', 'B', 'C'}`               | Collection of unique elements.                      |
| Create from iterable          | `s = set('ABCDE')`                  | Build a set from list/string/etc.                   |
| Length                        | `len(s)`                            | Number of elements in the set.                      |
| Membership test               | `'A' in x_set`                      | Check if an element is in the set.                  |
| Add one element               | `x_set.add('H')`                    | Add a single item to the set.                       |
| Discard element (safe remove) | `x_set.discard('H')`                | Remove if present, do nothing if not.               |
| Remove element (strict)       | `x_set.remove('A')`                 | Remove element; raises error if not present.        |
| Pop arbitrary element         | `elem = x_set.pop()`                | Remove and return an arbitrary element.             |
| Copy                          | `copy_x = x_set.copy()`             | Shallow copy of the set.                            |
| Clear all elements            | `x_set.clear()`                     | Empty the set (`set()` afterwards).                 |
| Union (A ∪ B)                 | `x_set.union(y_set)`                | New set with elements in **A or B** (or both).      |
| Union (operator)              | `x_set \| y_set`                    | Same as `union()`.                                  |
| Intersection (A ∩ B)          | `x_set.intersection(y_set)`         | New set with elements **common** to both.           |
| Intersection (operator)       | `x_set & y_set`                     | Same as `intersection()`.                           |
| Difference (A − B)            | `x_set.difference(y_set)`           | Elements in `x_set` but **not** in `y_set`.         |
| Difference (operator)         | `x_set - y_set`                     | Same as `difference()`.                             |
| Symmetric difference (A △ B)  | `x_set.symmetric_difference(y_set)` | Elements in A or B, but not both.                   |
| In-place difference update    | `x_set.difference_update(y_set)`    | Remove from `x_set` all elements also in `y_set`.   |
| Disjoint test                 | `x_set.isdisjoint(y_set)`           | `True` if sets have **no element in common**.       |
| Subset test (B ⊆ A)           | `y_set.issubset(x_set)`             | `True` if all elements of `y_set` are in `x_set`.   |
| Superset test (A ⊇ B)         | `x_set.issuperset(y_set)`           | `True` if `x_set` contains all elements of `y_set`. |

### Global summary – Core data structures & usages

| Structure            | Definition (what it is)                                                                 | Typical syntax (Python)                                                                 | Ordered?                         | Mutable?                        | Duplicates allowed?                      | Indexed by                | Typical use / notes                                                                                          |
|----------------------|-----------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|----------------------------------|---------------------------------|------------------------------------------|---------------------------|--------------------------------------------------------------------------------------------------------------|
| **List**             | Ordered sequence of objects (general container).                                       | `lst = [10, 20, 30]`                                                                    | Yes (keeps insertion order)      | Yes (we can change/add/remove) | Yes                                      | Integer index (`lst[i]`) | Time series (prices, returns), lists of trades, generic containers.                                          |
| **List as stack**    | List used as **LIFO** stack (Last In, First Out).                                      | `stack = []`<br>`stack.append(x)`<br>`x = stack.pop()`                                  | Yes (top = end of list)         | Yes                             | Yes                                      | Top via `stack[-1]`      | Call stacks, temporary buffers, undo history, evaluation of expressions.                                     |
| **List as queue**    | List used as **FIFO** queue (First In, First Out).                                     | `queue = []`<br>`queue.append(x)`<br>`x = queue.pop(0)`                                 | Yes                              | Yes                             | Yes                                      | Front via index `0`      | Simple queues, but inefficient for large N (shifts elements on `pop(0)`).                                    |
| **Deque (queue)**    | Double-ended queue, efficient for FIFO/LIFO.                                           | `from collections import deque`<br>`q = deque([...])`<br>`q.append(x)` / `q.popleft()`  | Logical order (left→right)       | Yes                             | Yes                                      | Front/back (no index use) | Real queues (FIFO) for events/messages, logs, task scheduling.                                               |
| **Graph**            | Network of nodes (vertices) connected by edges.                                        | `g = {'A': ['B','C'], 'B': ['A','C','D'], ...}`                                         | Depends on implementation        | Yes (dict + lists)             | Yes (but usually unique neighbors)       | By node key              | Adjacency lists: networks, routes, counterparty graphs, state transitions.                                   |
| **Tree**             | Hierarchical structure (root → branches → leaves).                                     | `class Tree: ...`<br>`tree = Tree("Root", left, right)`                                | Hierarchical, not linear index   | Yes (via objects)              | Yes                                      | Attributes (`node.left`) | Game trees, scenario trees, decision trees, parsing, search.                                                 |
| **Dictionary (dict)**| Mapping **key → value**.                                                                | `d = {"AAPL": 190.5, "MSFT": 340.2}`                                                    | Insertion order kept (Py3.7+)    | Yes (we can add/change keys)   | Keys must be unique                       | By key (`d["AAPL"]`)     | Lookup tables: ticker → price, account → PnL, ISIN → bond info, parameters, config.                          |
| **Tuple**            | Immutable ordered sequence (like a read-only list).                                    | `t = (10, 20, 30)`<br>`single = (10,)`                                                  | Yes                              | **No** (cannot modify)         | Yes                                      | Integer index (`t[i]`)   | Fixed records `(ticker, qty)`, return multiple values, keys for dicts.                                       |
| **Set**              | Unordered collection of **unique** elements.                                           | `s = {"AAPL", "MSFT"}`<br>`s = set([1, 2, 2, 3])`                                       | No (conceptually unordered)      | Yes (can add/remove)           | **No** (duplicates removed automatically) | Not indexed              | Unique tickers/IDs, membership tests (`x in s`), set operations (union/intersection/difference) on datasets. |
| **Empty dict**       | Dictionary with no entries.                                                             | `empty_dict = {}`                                                                       | –                                | Yes                             | –                                        | –                         | Start a mapping and fill it later.                                                                            |
| **Empty set**        | Set with no elements.                                                                   | `empty_set = set()`                                                                     | –                                | Yes                             | –                                        | –                         | Start a unique-collection container; important: `{}` is **dict**, not set.                                   |

---
## SECTION 5 : Market Data and Charts

### <ins> Time Series Data </ins>

A **time series** is a series of observations of a variable **indexed in time order**.

- We observe a variable (price, volume, PnL, rate…) at **different points in time**.
- Each observation = **value + timestamp**.
- Observations are usually recorded at **specific and regular intervals** (1s, 1 min, 1 day…).

In finance, almost everything important (prices, volumes, indicators) is stored as **time series data**.

---

#### Core definition

> **Time series data** = a collection of observations of a variable ordered in time  
> (e.g. daily closing price of AAPL, 1-minute LTP of a future, hourly FX rate).

Examples:
- Daily closing price of AAPL for 1 year.
- 5-min OHLCV bars of ES futures.
- 1-second Last Traded Price (LTP) stream on a crypto.

---

#### OHLCV time series

One of the most important formats for short-term trading is the **OHLCV** time series:

- **O** = Open (opening price of the bar/day)  
- **H** = High (highest price within the bar/day)  
- **L** = Low (lowest price within the bar/day)  
- **C** = Close (closing price of the bar/day)  
- **V** = Volume (traded quantity during the bar/day)

These are usually stored as **bars** over a chosen horizon (granularity):
- Daily OHLCV  
- 1-hour OHLCV  
- 5-minute OHLCV, etc.

OHLCV time series allow us to:
- analyse and forecast price movements,
- build indicators,
- plot candlestick charts,
- backtest trading strategies.

---

### LTP time series (Last Traded Price)

For intraday / high-frequency:

- We can work with **LTP (Last Traded Price)** time series.
- LTP can be recorded, for example:
  - every **1 second**
  - every **1 minute**
  - every **tick** (every trade)

This is useful when:
- we do **intraday trading**,  
- we train **machine learning** models on high-frequency data.

---

#### Granularity (time resolution)

**Granularity** = length of the time interval between observations.

Examples of granularity:
- 1 second LTP
- 1 minute OHLC
- 5 minute OHLC
- 1 hour OHLC
- 1 day OHLCV

Choosing the **right granularity** is crucial:

- For **intraday ML model** → very low granularity (e.g. 1-second LTP) is often used to train the algorithm.
- For **Japanese candlestick / chart-based trading** → 1-minute or 5-minute OHLC data is more suitable.

Rule of thumb:
- Higher granularity (1 day) → smoother view, less noise, less detail.  
- Lower granularity (1s, ticks) → more detail, more noise, heavier data.

---
#### Other data structures (beyond simple time series)

| Data type        | Time dimension?          | Entities (what we observe)         | Variables (what we measure)              | Example (markets)                                                                 |
|------------------|--------------------------|-------------------------------------|------------------------------------------|-----------------------------------------------------------------------------------|
| Time series      | Yes (multiple dates)     | 1 entity                            | 1 or several variables                   | Daily OHLCV of **AAPL** over 1 year.                                             |
| Cross-sectional  | Single timestamp         | Many entities at one point in time  | 1 or several variables                   | OHLC of **AAPL, MSFT, TSLA** at **11:30am** today.                               |
| Longitudinal     | Yes (over time)          | 1 entity                            | Several characteristics of that entity   | 1-week **OHLC** time series for **Infosys**.                                     |
| Panel            | Yes (over time)          | Many entities                       | Usually 1 main characteristic per entity | Daily **closing price** of **AAPL, MSFT, TSLA** over **1 year** (panel of stocks). |


### <ins> Import Time series data</ins>
