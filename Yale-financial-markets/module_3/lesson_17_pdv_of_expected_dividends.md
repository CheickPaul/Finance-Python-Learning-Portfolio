# Lesson 17 – PDV of Expected Dividends

## Key Concepts

- **Core Idea**  
  The price of a stock equals the **Present Discounted Value (PDV)** of all its expected future dividends.

- **Discounting one cash flow**  
  Present value of \$1 received in one year at rate \(r\):  
  \[
  PDV = \frac{1}{1+r}
  \]

  Present value of \$1 received in \(n\) years:  
  \[
  PDV = \frac{1}{(1+r)^{n}}
  \]

- **Discounting a dividend stream**  
  Price today as the discounted sum of expected dividends \(\{D_t\}\):  
  \[
  P_0 = \sum_{t=1}^{T} \frac{D_t}{(1+r)^{t}}
  \]

- **Constant-growth (Gordon) case**  
  If dividends grow at constant rate \(g\) with \(r>g\):  
  \[
  P_0 = \frac{D_1}{\,r - g\,}
  \]

- **Link to P/E ratio**  
  When all earnings are paid as dividends so \(D_1 \approx E_1\):  
  \[
  \frac{P_0}{E_1} \;\approx\; \frac{1}{\,r - g\,}
  \]

---

## My Notes

- Even firms that do **not** pay dividends today are valued as claims on **future** distributions (dividends/buybacks/liquidation).  
- The two macro drivers embedded in valuation are the **discount rate \(r\)** (often tied to interest rates and risk premia) and **growth \(g\)**.  
- A rise in bond yields (higher \(r\)) compresses justified multiples; higher durable growth (higher \(g\)) expands them.  
- Sentiment and narratives can push market prices away from PDV for long stretches, but PDV remains the anchor.

---

## Reflection

- The dividend discount model is a **first-principles** bridge from cash flows to price. It clarifies why equity valuations move with rates and growth expectations.  
- For trading and risk: thinking of \(\text{P/E} \approx 1/(r-g)\) helps frame **multiple risk** when macro regimes shift.  
- Practical idea: build a small tool that maps index fair value over grids of \((r,g)\), then compare to market to spot over/undervaluation pockets.

---

## Key Takeaways

1. **Stocks are worth the discounted stream of future cash flows.**  
2. **Two levers matter most:** the discount rate \(r\) and growth \(g\).  
3. **Gordon formula** \(P_0=D_1/(r-g)\) is valid only if \(r>g\) and growth is stable.  
4. Market prices can deviate from PDV in the short run, but PDV provides the fundamental anchor.
