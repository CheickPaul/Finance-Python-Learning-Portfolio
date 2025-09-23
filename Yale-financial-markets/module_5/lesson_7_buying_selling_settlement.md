# [Buying, Selling, and Settlement]

## 1. Historical Origins – Dojima Exchange

- The first futures market dates back to **Dojima (Japan, 18th century)**.  
- Traders used **hand signals** (“pit trading”) to communicate buy/sell orders.  
- Trading sessions were timed with a **burning fuse**; “water men” stopped late trades with buckets of water.  
- These practices inspired modern futures markets such as the CME (Chicago Mercantile Exchange).  

---

## 2. Daily Settlement and Margin Accounts

Futures contracts are **marked-to-market daily**.

- A **margin account** is adjusted each day according to the profit and loss (P&L):  

**Long position**  
$$
\Delta \Pi_t^{\text{long}} = N \cdot M \cdot (F_t - F_{t-1})
$$

**Short position**  
$$
\Delta \Pi_t^{\text{short}} = -N \cdot M \cdot (F_t - F_{t-1})
$$

where:  
- \(N\) = number of contracts  
- \(M\) = contract multiplier  
- \(F_t\) = settlement price at time \(t\)  

If the account balance falls below the **maintenance margin**, a **margin call** occurs, requiring funds to be restored to the **initial margin**.

> **Note**: The settlement price \(F_t\) is not always the last trade of the day (to avoid manipulation). It is determined by a settlement committee.

---

## 3. Physical Delivery Futures

If a futures contract is **not closed before expiration**:

- **Seller (short)** must deliver the underlying asset.  
- **Buyer (long)** must receive it.  

Most financial traders avoid delivery by closing positions early.  
Only **hedgers** (farmers, refiners, bond dealers) typically go to delivery.

**Examples**  

- **Corn Futures**: A farmer short delivers bushels; a food processor long receives them.  
- **Oil Futures (WTI, Brent)**:  
  - Standard contract size = 1,000 barrels.  
  - WTI delivery point = **Cushing, Oklahoma**.  
  - Traders must exit before **First Notice Day (FND)** to avoid delivery.  
- **Ultra Bond Futures (UB30)**:  
  - Physically settled in a basket of U.S. Treasury Bonds with maturity ≥ 25 years.  
  - The short chooses which bond to deliver (*cheapest-to-deliver*).  
  - Pricing depends on the **conversion factor (CF)**.  

---

## 4. Arbitrage and Convergence

Futures converge to the **spot price** at maturity:

$$
\lim_{T \to 0} (F_T - S_T) = 0 \quad \Rightarrow \quad F_T \to S_T
$$

- If \(F_T < S_T\): Arbitrageurs buy futures, take delivery, and sell in the spot market.  
- If \(F_T > S_T\): Arbitrageurs short futures and sell spot.  

This mechanism enforces **market efficiency**.

---

## 5. Cash-Settled Futures

Cash settlement was introduced to handle assets that **cannot be delivered physically**.  

**Examples**:  
- **S&P 500 Futures**: Standard (\$250 × index) and E-mini (\$50 × index).  
- **Housing Price Futures**: No physical homes can be delivered → cash-only.  

**Advantages**:  
- Simpler arbitrage (automatic cash adjustment).  
- Broader scope: indices, housing, volatility, etc.  

---

## 6. Key Takeaways

- Futures markets evolved from **physical delivery** to **cash settlement**.  
- **Daily settlement** and **margins** mitigate counterparty risk.  
- **Physical delivery** remains common in commodities (oil, grains) and bonds (Treasuries).  
- **Cash settlement** enables trading of indices and non-standardized assets.  

For traders:  
- **Oil Futures and UB30 Futures are physically settled.**  
- Brokers usually require positions to be closed before delivery deadlines.  
- Industrial users (refiners, bond dealers) are the real delivery participants.
