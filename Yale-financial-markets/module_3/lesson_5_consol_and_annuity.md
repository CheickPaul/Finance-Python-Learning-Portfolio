# Lesson 5 – Inflation and Index Bonds

## Key Concepts
- **Nominal interest rate (\(r_{nominal}\))**  
  - Quoted in currency units (e.g., USD, EUR).  
  - Represents the growth of money, not purchasing power.  
  - Example: a 5% nominal yield on $100 = $105 after 1 year.  

- **Real interest rate (\(r_{real}\))**  
  - Adjusted for inflation, measures the growth of purchasing power.  
  - Tells you how many more goods and services you can buy after 1 year.  

- **Inflation rate (\(\pi\))**  
  - Rate at which prices of goods/services increase.  
  - Reduces the purchasing power of money.  

- **Fisher Equation (exact relationship)**  

  $$
  1 + r_{nominal} = (1 + r_{real})(1 + \pi)
  $$  

  Approximation (valid if rates are small):  

  $$
  r_{real} \approx r_{nominal} - \pi
  $$  

- **Index Bonds (Inflation-Protected Securities)**  
  - Principal and coupons are **indexed to inflation**.  
  - Protect investors from unexpected inflation.  
  - Guarantee a **real return** (instead of a nominal one).  
  - Example: U.S. TIPS (Treasury Inflation-Protected Securities).  

- **Breakeven Inflation Rate**  
  - Market-based measure of expected inflation.  
  - Defined as:  

  $$
  \text{Breakeven Inflation} = r_{nominal} - r_{TIPS}
  $$  

  - Example: if 10-year Treasury = 4.5% and 10-year TIPS = 2.0%, then expected inflation = 2.5%.  

- **Money Illusion**  
  - Investors often confuse nominal returns with real returns.  
  - Example: Earning 5% nominal with 6% inflation = –1% real return (loss in purchasing power).  

---

## My Notes
### 1. Nominal vs Real Rates
- Example: nominal yield = 6%, inflation = 2%.  
  - Real yield (approx):  

  $$
  r_{real} = 6\% - 2\% = 4\%
  $$  

- More precise:  

  $$
  r_{real} = \frac{1 + 0.06}{1 + 0.02} - 1 = 3.92\%
  $$  

### 2. Why Nominal > Real
- Investors demand compensation for **inflation risk**.  
- The difference ≈ expected inflation.  

### 3. Index Bonds
- Example: If CPI rises 3%, both principal and coupon increase by 3%.  
- Eliminate inflation risk for the investor, transfer it to the issuer (government).  
- Popular with **pension funds** and **long-term savers**.  

---

## Reflection
- Distinguishing between **nominal vs real** returns is crucial — investors often fall into the trap of **money illusion**.  
- Index bonds like TIPS allow **direct inflation hedging**, giving clarity about real returns.  
- In trading and quantitative finance:  
  - **Breakeven inflation** is extracted from the difference between nominal bonds and TIPS.  
  - It provides a **real-time market expectation of inflation**, which is key for anticipating **central bank policy** and **portfolio allocation**.  
- My takeaway: monitoring **inflation spreads** is essential for both macro strategies and fixed-income trading.  

