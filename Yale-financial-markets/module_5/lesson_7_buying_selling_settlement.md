# [Buying, Selling, and Settlement]

## 1. Historical Origins – Dojima Exchange

* The first futures market dates back to **Dojima (Japan, 18th century)**.  
* Traders used **hand signals** (“pit trading”) to communicate buy/sell orders.  
* Trading sessions were timed with a **burning fuse**; “water men” stopped late trades with buckets of water.  
* These practices inspired modern futures markets such as the CME (Chicago Mercantile Exchange).

---

## 2. Daily Settlement and Margin Accounts

Futures contracts are **marked-to-market daily**.

A **margin account** is adjusted each day according to the profit and loss (P&L).

**Long position**

\[
\Delta \Pi_t^{\text{long}} = N \cdot M \cdot \big(F_t - F_{t-1}\big)
\]

**Short position**

\[
\Delta \Pi_t^{\text{short}} = -\,N \cdot M \cdot \big(F_t - F_{t-1}\big)
\]

where:  
* \(N\) = number of contracts  
* \(M\) = contract multiplier  
* \(F_t\) = settlement price at time \(t\)  
* \(F_{t-1}\) = settlement price at time \(t-1\)

If the account balance falls below the **maintenance margin**, a **margin call** occurs to restore funds to the **initial margin**.

> Note – The settlement price \(F_t\) is not always the last trade of the day (to avoid manipulation). It is determined by a settlement committee.

---

## 3. Physical Delivery Futures

If a futures contract is **not closed before expiration**:

* **Seller (short)** must deliver the underlying asset.  
* **Buyer (long)** must receive it.

Most financial traders avoid delivery by closing positions in advance.  
Only **hedgers** (farmers, refiners, bond dealers) typically go to delivery.

**Examples**

* **Corn Futures**: A farmer short delivers bushels; a food processor long receives them.  
* **Oil Futures (WTI, Brent)**: contract size **1,000 barrels**; WTI delivery point **Cushing, Oklahoma**; exit before **First Notice Day (FND)** to avoid delivery.  
* **Ultra Bond Futures (UB30)**: physically settled in a basket of U.S. Treasury Bonds with maturity **≥ 25 years**; the short chooses the **cheapest-to-deliver (CTD)**; pricing uses a **conversion factor (CF)**.

---

## 4. Arbitrage and Convergence

At maturity, futures converge to spot.

\[
\lim_{T \to 0} \big(F_T - S_T\big) = 0 \;\;\Rightarrow\;\; F_T \to S_T
\]

* If \(F_T < S_T\): buy futures, take delivery, sell spot.  
* If \(F_T > S_T\): short futures and sell spot.

This mechanism enforces **market efficiency**.

---

## 5. Cash-Settled Futures

Cash settlement was introduced for assets that **cannot be delivered physically**.

**Examples**  
* **S&P 500 Futures** (Standard and E-mini)  
* **Housing Price Futures**

**Final cash adjustment**

\[
\text{Cash Settlement} = N \cdot M \cdot \big(I_{\text{final}} - F_{\text{final}}\big)
\]

where:  
* \(I_{\text{final}}\) = reference index level at final fixing  
* \(F_{\text{final}}\) = futures final settlement price

In practice, this equals the **sum of daily mark-to-market** adjustments.

**Advantages**
* Simpler arbitrage (automatic cash adjustment)  
* Enables trading on indices, housing, volatility, etc.

---

## 6. Cost of Carry, Basis and Cash-and-Carry

Define the **basis**:

\[
\text{Basis}_t = F_t - S_t
\]

Under the **cost-of-carry** model (risk-free rate \(r\), storage cost \(c\), convenience yield \(y\), time \(T\)):

\[
F_t = S_t \cdot e^{(r + c - y)T}
\]

* **Contango** when \(r + c > y\) ⇒ \(F_t > S_t\)  
* **Backwardation** when \(y > r + c\) ⇒ \(F_t < S_t\)

**Cash-and-Carry (if \(F_t\) too high)**  
Buy spot, finance at \(r\), store (cost \(c\)), and **sell** the future. Profit from convergence.

**Reverse Cash-and-Carry (if \(F_t\) too low)**  
Short/borrow the spot, invest proceeds at \(r\), and **buy** the future.

As \(T \to 0\), the basis closes:

\[
\text{Basis}_t \xrightarrow[t \to T]{} 0
\]

---

## 7. Bond Futures: Invoice Price, CF and CTD

For a deliverable bond future (e.g., **UB30**), the short delivers any eligible bond in the basket. The invoice paid to the short is:

\[
\text{Invoice Price} = F_{\text{final}} \times CF \times M + AI
\]

where:  
* \(F_{\text{final}}\) = futures final price  
* \(CF\) = **conversion factor** of the delivered bond  
* \(M\) = contract multiplier  
* \(AI\) = **accrued interest** on the delivered bond

**Choosing the CTD (cheapest-to-deliver)**

Net Basis (price view):

\[
\text{NetBasis} = P_{\text{bond}} - (F \cdot CF) - AI
\]

CTD tends to **minimize** NetBasis.

Implied Repo Rate (yield view):

\[
IRR = \frac{\big( \text{Coupons} + P_{\text{bond}} - (F \cdot CF) \big)}{F \cdot CF} \times \frac{360}{\text{days}}
\]

CTD tends to **maximize** \(IRR\) vs the market repo.

---

## 8. Key Takeaways

* Futures evolved from **physical delivery** (grains, oil, bonds) to **cash settlement** (indices, housing).  
* **Daily margining** reduces counterparty risk.  
* **Convergence** \(F_T \to S_T\) is enforced by arbitrage.  
* Delivery rules matter:  
  * **Oil** and **UB30** are **physically settled**, mind FND/LTD.  
  * **S&P 500** is **cash-settled**, avoiding operational delivery risk.  
* In bond futures, **CF** and **CTD** drive delivery economics and pricing.
