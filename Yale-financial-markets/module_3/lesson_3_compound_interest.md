# Lesson 3 – Coupon Bonds

## Key Concepts
- **Coupon bonds** pay periodic interest (coupons) plus the face value at maturity.  
- Price = Present Discounted Value (PDV) of all future payments.  
- Most government and corporate bonds are coupon bonds.

## My Notes
- Unlike discount bonds, coupon bonds generate **cash flows every 6 months or annually**.  
- Par value is usually **$100 or $1,000** depending on the market.  

### 1. Price of a Coupon Bond
For a bond with coupon \( C \), maturity \( T \), face value \( F \), and interest rate \( r \):  

$$
P = \frac{C}{1+r} + \frac{C}{(1+r)^2} + \cdots + \frac{C}{(1+r)^T} + \frac{F}{(1+r)^T}
$$

- Each coupon is discounted according to the time it is paid.  
- The face value \( F \) is received at maturity and discounted back.  

### 2. Yield to Maturity (YTM)
The **YTM** is the interest rate \( r \) that makes the bond price equal to the PDV of future payments:  

$$
P = \sum_{t=1}^{T} \frac{C}{(1+r)^t} + \frac{F}{(1+r)^T}
$$

In practice, solving for \( r \) requires iteration (numerical methods).

### 3. Consols (Perpetual Bonds)
A **consol** pays a constant coupon \( C \) forever.  

$$
P = \frac{C}{r}
$$

- A **growing consol** pays coupons growing at rate \( g \):  

$$
P = \frac{C}{r-g}, \quad (r > g)
$$

### 4. Annuities
An annuity pays a fixed amount \( C \) for \( T \) periods:  

$$
P = \frac{C}{r} \left( 1 - \frac{1}{(1+r)^T} \right)
$$

- Example: mortgages and retirement pensions.

## Reflection
- Coupon bonds generalize discount bonds: they are just a **bundle of discount bonds** (each coupon = one payment).  
- Consols are a theoretical case but very useful in **valuation of perpetual income streams** (like preferred stock).  
- Annuities connect finance directly to **household decisions** (mortgages, insurance, pensions).  
- As a trader, recognizing this structure helps when pricing fixed income products and detecting mispricing across maturities.  

