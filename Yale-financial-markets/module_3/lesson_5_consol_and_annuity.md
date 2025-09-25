# Lesson 5 – Inflation and Index Bonds

## Key Concepts

- **Nominal Interest Rate (\(r_{nominal}\))**  
  Expressed in currency units. Represents growth of money but not purchasing power.  

  Exemple :  
  \[
  100 \ \text{USD} \times (1 + 0.05) = 105 \ \text{USD après 1 an}
  \]

- **Real Interest Rate (\(r_{real}\))**  
  Adjusted for inflation. Represents growth of purchasing power.  

- **Inflation (\(\pi\))**  
  Annual rate of increase in prices. Reduces the real value of money.  

- **Fisher Equation (exact)**  

  \[
  1 + r_{nominal} = (1 + r_{real})(1 + \pi)
  \]

  **Approximation (if rates are small):**  

  \[
  r_{real} \approx r_{nominal} - \pi
  \]

- **Index Bonds (Inflation-Protected Securities)**  
  Coupon and principal indexed to inflation.  
  Guarantee a fixed **real return**.  
  Example: U.S. TIPS.  

- **Breakeven Inflation Rate**  

  \[
  \pi^{e} = r_{nominal} - r_{TIPS}
  \]

  Exemple :  
  - 10Y Treasury = 4.5%  
  - 10Y TIPS = 2.0%  

  \[
  \pi^{e} = 4.5\% - 2.0\% = 2.5\%
  \]

- **Money Illusion**  
  Confusing nominal vs real returns.  

  Exemple :  
  \[
  r_{nominal} = 5\%, \quad \pi = 6\% \quad \Rightarrow \quad r_{real} \approx -1\%
  \]

---

## My Notes

### 1. Nominal vs Real
Exemple : \( r_{nominal} = 6\% \), \( \pi = 2\% \).  

Approximation :  
\[
r_{real} \approx 6\% - 2\% = 4\%
\]

Exact :  
\[
r_{real} = \frac{1 + r_{nominal}}{1 + \pi} - 1 = \frac{1.06}{1.02} - 1 = 3.92\%
\]

### 2. Why Nominal > Real
Investors require compensation for inflation risk.  
\[
r_{nominal} \approx r_{real} + \pi
\]

### 3. Index Bonds
If CPI = +3%: both coupon and principal rise by 3%.  

Formally:  
\[
C_t = C_0 \times (1 + \pi_t), \quad P_t = P_0 \times (1 + \pi_t)
\]

Where:  
- \( C_t \) = coupon at time \(t\)  
- \( P_t \) = principal at time \(t\)  
- \( \pi_t \) = cumulative inflation since issuance  

---

## Reflection

- **Key insight**: separating **nominal vs real** returns avoids money illusion.  
- **TIPS** (and other index bonds) provide direct protection against inflation.  
- **Breakeven inflation** gives a **market-implied forecast** of inflation and is a major tool for macro/fixed income desks.  
- As a trader, I see how inflation spreads can signal shifts in **central bank policy** or **asset allocation**.  
