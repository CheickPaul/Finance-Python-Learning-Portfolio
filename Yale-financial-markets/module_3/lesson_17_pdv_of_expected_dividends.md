# Lesson 17 – PDV of Expected Dividends  

## Key Concepts  

- **Core Idea**  
  - The price of a stock equals the **Present Discounted Value (PDV)** of all its expected future dividends.  
  - Without the prospect of future dividends (or equivalent cash flows), a stock would be worth **zero**.  

- **Mathematical Formulation**  
  - Present value of one dollar in **1 year**:  
    $$
    PDV = \frac{1}{1+r}
    $$  
  - Present value of one dollar in **n years**:  
    $$
    PDV = \frac{1}{(1+r)^n}
    $$  
  - Present value of a stream of dividends:  
    $$
    P = \sum_{t=1}^T \frac{D_t}{(1+r)^t}
    $$  
  - If dividends grow at a constant rate $g$:  
    $$
    P = \frac{D_1}{r - g}
    $$  

- **P/E Ratio Link**  
  - If a company pays all its earnings as dividends:  
    $$
    \frac{P}{E} \approx \frac{1}{r - g}
    $$  
  - $r$ = required return (discount rate).  
  - $g$ = growth rate of earnings/dividends.  

- **Interpretation**  
  - **Low P/E** → high $r$ (risky) or low $g$ (weak growth).  
  - **High P/E** → low $r$ (safer) or high $g$ (strong growth).  

---

## My Notes  

- This framework is at the **core of fundamental equity valuation**.  
- Even if firms do not pay dividends today, valuation models assume **eventual payouts** (via dividends or buybacks).  
- Growth stocks with **no dividends** today still derive value from the assumption of **future distributions**.  
- Investor psychology often overrides fundamentals → **sentiment-driven deviations** (value vs growth investing).  

---

## Reflection  

This lesson reinforced that stocks are ultimately claims on **future cash flows**, not just speculative tickets.  
- The **dividend discount model (DDM)** is simple but powerful: it links valuation directly to $r$ and $g$.  
- For trading, the P/E ≈ $1 / (r-g)$ insight helps me think of equities relative to bond yields:  
  - If bond yields ($r$) rise, stock valuations mechanically fall.  
  - If growth expectations ($g$) rise, stocks justify higher multiples.  
- As a future quant trader, I see the **PDV framework as the bridge** between fundamental investing and relative value trading.  
- A practical project idea:  
  - Build a **Python dashboard** that estimates fair value of indices (e.g., S&P 500) using PDV with different $r$ and $g$ scenarios.  
  - Compare model fair value vs actual market price → detect potential over/undervaluation.  

---

## Key Takeaways  

1. **Stocks = discounted stream of dividends/cash flows.**  
2. P/E ratio connects valuation to risk-free rate and growth expectations.  
3. Changes in $r$ (interest rates) and $g$ (growth) are the two key drivers of valuation.  
4. Behavioral factors explain why market prices often diverge from strict PDV logic.  

