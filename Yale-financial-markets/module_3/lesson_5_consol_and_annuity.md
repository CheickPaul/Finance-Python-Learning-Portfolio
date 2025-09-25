# Lesson 5 – Consol and Annuity Formulas

## Key Concepts

### 1. Consol (Perpetual Bond)
A **consol** is a perpetual bond that pays a fixed coupon \(X\) every period, forever.  

$$
PV_{\text{consol}} = \frac{X}{r}
$$

where  
- \(X\) = coupon payment  
- \(r\) = discount rate  

---

### 2. Growing Consol
A **growing consol** pays coupons that increase at a constant growth rate \(g\).  

$$
PV_{\text{growing consol}} = \frac{X}{r - g}, \quad r > g
$$

---

### 3. Annuity
An **annuity** is a series of fixed payments \(X\), starting at \(t=1\), ending at \(t=T\).  

$$
PV_{\text{annuity}} = X \cdot \frac{1 - (1+r)^{-T}}{r}
$$

---

### 4. Growing Annuity
A **growing annuity** has payments that increase at a constant growth rate \(g\) for \(T\) periods.  

$$
PV_{\text{growing annuity}} = X \cdot \frac{1 - \left(\frac{1+g}{1+r}\right)^T}{r - g}, \quad r > g
$$

---

## My Notes

- Consols were historically issued by the British government to finance perpetual debt.  
- Annuities appear in pensions, mortgages, and structured finance.  
- Growing versions generalize to assets with dividend growth, like equities.  

---

## Reflection

- Consol = perpetual cash flows, like preferred shares.  
- Annuity = finite stream of payments, like mortgages.  
- Growing versions → connect directly to the Dividend Discount Model (DDM) in equity valuation.  
- As a trader, mastering these formulas links **cash flow timing** with **market valuation**.  
