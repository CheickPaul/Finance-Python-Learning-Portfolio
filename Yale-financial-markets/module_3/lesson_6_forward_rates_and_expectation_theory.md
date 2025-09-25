# Lesson 6 – Forward Rates and Expectation Theory

## Key Concepts

### 1. Forward Rate
A **forward rate** is the interest rate agreed today for a loan (or investment) that will occur in the future.  
It links **spot rates** (current yields for maturities \(n\)) with **future expected rates**.

Mathematically:

$$
(1 + R_n)^n = (1 + R_m)^m \cdot (1 + f_{m,n})^{(n-m)}
$$

where:
- \(R_n\) = n-period spot rate  
- \(R_m\) = m-period spot rate  
- \(f_{m,n}\) = forward rate between \(m\) and \(n\)

---

### 2. Expectation Theory
The theory states that **long-term interest rates are averages of expected short-term rates**.

For example:

$$
R_2^2 = (1 + R_1)(1 + f_{1,2})
$$

so the **1-year forward rate one year from now** is:

$$
f_{1,2} = \frac{(1+R_2)^2}{(1+R_1)} - 1
$$

Implication: If the yield curve is upward-sloping, markets expect future short-term rates to rise.

---

### 3. Risk Premium (Liquidity Preference)
In reality, forward rates are not perfect predictors of future short-term rates.  
Investors demand a **term premium** for holding longer maturities.  

Adjusted formula:

$$
f_{m,n} = E(r_{m,n}) + \pi_{m,n}
$$

where:
- \(E(r_{m,n})\) = expected short-term rate between \(m\) and \(n\)  
- \(\pi_{m,n}\) = risk (or liquidity) premium

---

## My Notes

- Forward rates = prices for borrowing/lending in the future, implied by today’s yield curve.  
- Expectation theory: yield curve embeds market expectations of future short-term rates.  
- In practice, forward ≠ expected → there is always a risk premium.  
- Key tool for:  
  - **Monetary policy analysis** (inferring rate expectations).  
  - **Trading** (curve steepener/flatteners).  
  - **Risk management** (pricing swaps, FRAs, futures).  

---

## Reflection

- Forward rates are central in **fixed income trading**: they allow us to derive implied market expectations.  
- The limitation is the **liquidity premium**: forward ≠ future realized rate.  
- As a trader, I can use forwards to **anticipate curve movements**:  
  - Example: if the forward curve implies 3% but I expect only 2%, there is a **relative value trade** (buy long maturity, short short-term).  
- These formulas are also the **bridge** between bond pricing and **derivatives on rates** (FRAs, swaps, futures).  

