# [Reading Options Pricing]

## 1. Historical Origins
- The **first documented options** come from Holland (1600s–1730).  
- Example: option on shares of the Dutch East India Company (VOC).  
- Already at that time: **printed contracts** with handwritten blanks → early standardization → a step toward the information age.  

---

## 2. Modern Example: Intel Options (CBOE)
- **Underlying**: Intel stock (INTC), price ≈ **31.63 USD** (previous Friday close).  
- **Dividend**: 0.26 USD per share quarterly.  
- **Ticker**: INTC (4 letters → Nasdaq-listed).  

### Strike Prices
- 27, 30, 32, 35 USD.  
- Current price = 31 USD → some options are **in the money (ITM)**, others **out of the money (OTM)**.  

---

## 3. Why Buy an OTM Option?
- Example: **Call strike 35 USD**, premium = 2.36 USD.  
- Direct comparison with stock (31 < 35) seems irrational.  
- But it has **speculative value**: if the stock rises above 35, the option gains value.  

**Advantage**:  
- **Limited loss**:  
  \[
  \text{Max Loss} = \text{Premium Paid} = 2.36
  \]  
- Versus buying stock at 31 → potential total loss if company fails.  

---

## 4. Example of ITM Option
- **Call strike 27 USD**, premium = 7 USD.  
- Immediate exercise profit:  
  \[
  31.63 - 27 = 4.63 \, \text{USD}
  \]  
- But since premium = 7 > 4.63 → **early exercise = loss**.  

Usually you **do not exercise early**: keep the **time value** of the option.  

---

## 5. Bid-Ask Spread and Market Makers
- Quoted price = **last traded price**.  
- Market makers show:  
  - **Bid** = price dealers pay.  
  - **Ask** = price dealers charge.  

Example:  
- Bid = 6.05, Ask = 6.20 → Spread = 0.15.  
- This spread = **market maker’s profit margin**.  
- More liquid strikes (e.g., 35) → **narrower spreads**.  

---

## 6. Option Moneyness (ITM / OTM / ATM)

### Call Options (right to buy)
- **In the Money (ITM)**: \( S > K \) → profitable to exercise.  
- **At the Money (ATM)**: \( S \approx K \) → mostly time value.  
- **Out of the Money (OTM)**: \( S < K \) → no intrinsic value, only time value.  

### Put Options (right to sell)
- **In the Money (ITM)**: \( S < K \) → profitable to exercise.  
- **At the Money (ATM)**: \( S \approx K \) → mostly time value.  
- **Out of the Money (OTM)**: \( S > K \) → no intrinsic value, only time value.  

---

##  Key Takeaways
1. Options = **Intrinsic value** (strike vs spot) + **Time value** (future potential).  
2. Do **not exercise early** → preserve time value.  
3. **Bid-ask spreads** = market maker compensation.  
4. **Liquidity** reduces spreads (most traded strikes = most competitive).  
5. **Moneyness (ITM/OTM/ATM)** defines intrinsic vs time value.  

