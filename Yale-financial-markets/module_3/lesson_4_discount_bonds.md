# Lesson 4 – Forward Rates and Expectation Theory

## Key Concepts
- **Forward rates** = interest rates implied by today’s yield curve for future periods.  
- The **Expectation Theory**: long-term interest rates reflect the market’s expectation of future short-term rates.  
- Relation between spot rates, forward rates, and bond pricing.  

## My Notes
### 1. Present Discount Value (recap)
For a zero-coupon bond maturing in \( n \) years with rate \( r_n \):  

$$
PDV = \frac{1}{(1+r_n)^n}
$$

### 2. Linking Spot and Forward Rates
Let:  
- \( r_1 \) = 1-year rate today  
- \( r_2 \) = 2-year rate today  
- \( f_{2} \) = forward rate for year 2 (the implied 1-year rate one year from now)

No-arbitrage condition:  

$$
(1+r_2)^2 = (1+r_1)(1+f_2)
$$

General case for \( n \) years:  

$$
(1+r_n)^n = (1+r_{n-1})^{n-1}(1+f_n)
$$

This lets us solve for the forward rate:  

$$
f_n = \frac{(1+r_n)^n}{(1+r_{n-1})^{n-1}} - 1
$$

### 3. Expectation Theory
The forward rate is interpreted as the **expected future short rate**:  

$$
f_{t+1} \approx E[r_{t+1}]
$$

- Example: If the 2-year yield is higher than the 1-year yield, it implies markets expect 1-year rates to rise.  
- Limitations: ignores risk premia and liquidity effects.

### 4. Example
Suppose:  
- 1-year rate = 5%  
- 2-year rate = 6%  

Forward rate for year 2:  

$$
(1+0.06)^2 = (1+0.05)(1+f_2)
$$  

$$
1.1236 = 1.05(1+f_2)
$$  

$$
1+f_2 = \frac{1.1236}{1.05} \approx 1.0701
$$  

$$
f_2 \approx 7.01\%
$$  

👉 Market expects the 1-year rate in year 2 to be about **7%**.

## Reflection
- Forward rates provide a **bridge between today’s yield curve and tomorrow’s short rates**.  
- They are crucial for traders in **fixed income** and **derivatives pricing**: futures and swaps often embed forward rate logic.  
- However, pure expectation theory is **too simplistic**: in reality, investors demand a **risk premium** for holding long bonds.  
- In practice, traders distinguish between:
  - **Pure forwards (model-implied)**  
  - **Risk-adjusted expectations (term premium included)**  
- For my projects, this shows how to link **bond yields, interest rate derivatives, and expectations of monetary policy**.  

