## [Put–Call Parity]

### 1. Intrinsic Value at Expiration

* **Call Option (right to buy):**  
  On the last day, its value is:  

  $$
  C_T = \max(S_T - K, 0)
  $$

  * If $S_T < K$, the call is worthless.  
  * If $S_T > K$, its value equals the difference between stock price and strike.  

* **Put Option (right to sell):**  
  On the last day, its value is:  

  $$
  P_T = \max(K - S_T, 0)
  $$

  * You exercise only if $K > S_T$.  

At expiration, options only have **intrinsic value**.  
Before expiration, they also contain **time value**.

---

### 2. Put–Call Parity Relation

For European options with the same strike ($K$) and expiration ($T$):  

$$
C + PV(K) + PV(\text{Dividends}) - P = S
$$

Where:  

* $C$ = Call price  
* $P$ = Put price  
* $S$ = Current stock price  
* $PV(K)$ = Present value of strike (discounted at the risk-free rate)  
* $PV(\text{Dividends})$ = Present value of dividends to be paid before expiration  

This relation is enforced by **arbitrage**: if violated, traders exploit the difference until equilibrium is restored.

---

### 3. Market Example (Intel case study)

* Strike = 27  
* Call midpoint price ≈ 6.125  
* Put midpoint price ≈ (observed in market)  
* Dividends between now and expiry ≈ 2.08  

Ignoring interest rates for simplicity, the computed parity was **close** to the actual stock price (~31.63).  

Small discrepancies are due to:  

* No discounting for interest rates.  
* Market timing mismatches (bid/ask vs last price).  
* Imperfect synchrony in quotes.  

---

### 4. Why Out-of-the-Money (OTM) Options Still Have Value

* Even if $S < K$ (call OTM), the option is **not worthless** before expiry.  
* Reason: there is still **time** for the stock to move above strike.  
* This potential movement is the **time value** investors are willing to pay for.  

---

### 5. No-Arbitrage Principle

* **Arbitrage = risk-free profit**.  
* If put–call parity is violated, arbitrageurs immediately exploit it.  

Example:  
If the stock is mispriced relative to $(C - P + PV(K))$, traders create risk-free positions.  

Result: markets **self-correct**, so put–call parity holds in practice.

---

### 6. Reflection

* **Put–Call Parity** links the prices of calls, puts, and the underlying asset.  
* You don’t need both puts and calls — knowing one lets you deduce the other.  
* It is a **fundamental principle** of option pricing, used to detect mispricings and ensure market efficiency.

