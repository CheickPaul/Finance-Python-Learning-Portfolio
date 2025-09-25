# Lesson 5 – Consol and Annuity Formulas

## Key Concepts

### 1. Consol (Perpetual Bond)
- A **consol** is a perpetual bond: it pays a **fixed coupon \(x\)** every period, forever.  
- Present value formula:  

\[
PV_{\text{consol}} = \frac{x}{r}
\]

where:  
- \(x\) = coupon payment  
- \(r\) = discount rate  

---

### 2. Growing Consol
- A **growing consol** pays coupons that increase at a constant growth rate \(g\).  
- Formula:  

\[
PV_{\text{growing consol}} = \frac{x}{r - g}
\]

valid if \( r > g \).  

where:  
- \(x\) = first coupon  
- \(g\) = growth rate of coupon  

---

### 3. Annuity
- An **annuity** is a series of fixed payments \(x\), starting at \(t=1\), ending at \(t=T\).  
- Present value formula:  

\[
PV_{\text{annuity}} = x \times \frac{1 - (1+r)^{-T}}{r}
\]

where:  
- \(T\) = number of periods  
- \(r\) = discount rate  

---

### 4. Growing Annuity
- Payments grow at a constant rate \(g\) for \(T\) periods.  
- Formula:  

\[
PV_{\text{growing annuity}} = x \times \frac{1 - \left(\frac{1+g}{1+r}\right)^T}{r - g}
\]

valid if \( r > g \).  

---

## My Notes

- **Consols** were historically used by the British government to finance perpetual debt.  
- They are rare today but form the **foundation of bond pricing formulas**.  
- **Annuities** are common in pensions, mortgages, and structured finance.  
- Growing annuities and consols generalize to assets with **dividend growth**, like equities.  

---

## Reflection

- These formulas are the **building blocks** for fixed income and equity valuation.  
- Consols resemble **perpetual preferred stock** → infinite life, constant dividends.  
- Annuities link directly to **mortgage payments**: same math, just different context.  
- As a trader, understanding these PV formulas is essential to connect **cash flow timing** with **market prices**.  
- In equity valuation, the **Dividend Discount Model (DDM)** is just a **growing consol** formula applied to dividends.  
