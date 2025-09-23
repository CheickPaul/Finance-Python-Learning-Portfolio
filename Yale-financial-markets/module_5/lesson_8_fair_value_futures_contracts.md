# [Fair Value in Futures Contracts]

## 1. Concept

The **fair value** of a futures contract is the theoretical price that reflects the cost of carrying the underlying asset until the delivery date.  
It ensures **no arbitrage** between the spot market and the futures market.

The standard formula is:

\[
F = S \times (1 + r + s)
\]

Where:

* **F** = Futures price  
* **S** = Spot price  
* **r** = Interest rate for the maturity considered (per year, per month, etc.)  
* **s** = Storage cost as a percentage of the spot price  

Since both **r** and **s** are usually positive, **futures markets are typically in contango** (upward-sloping curve).

---

## 2. Contango

* When futures prices are **above** spot prices.  
* Happens because storage and interest costs add to the spot.  
* The longer the maturity, the higher the cost → hence an upward slope.  
* Typical situation in commodities with **ample supply**.  

---

## 3. Backwardation

* Futures prices can sometimes be **below** spot prices.  
* This occurs when the effective storage cost is **negative**.  
* In other words, when the **benefit of holding the asset physically** is greater than the cost of carry.  

This benefit is called the **Convenience Yield**.  

Revised formula:

\[
F = S \times (1 + r + s - y)
\]

Where:

* **y** = Convenience yield  

If **y > (r + s)** → the futures curve goes into **backwardation**.  

---

## 4. Example: Wheat Shortage

Imagine a pasta manufacturer:  

* **Spot wheat price** = €100 / ton  
* **Interest rate (r)** = 5%  
* **Storage cost (s)** = 3%  

**Normal fair value (contango):**

\[
F = 100 \times (1 + 0.05 + 0.03) = 108
\]

Now suppose there is a **bad harvest** and wheat is very scarce.  
The manufacturer is willing to pay €10/ton just to secure physical availability (convenience yield = 10%).  

\[
F = 100 \times (1 + 0.05 + 0.03 - 0.10) = 98
\]

→ The futures price is below spot → **backwardation**.  

---

## 5. Real-World Case: Oil During Covid (April 2020)

* With global lockdowns, **oil demand collapsed** while supply kept flowing.  
* Storage facilities (e.g., Cushing, Oklahoma) were completely full.  
* Traders holding May 2020 WTI futures could not take delivery.  

**Result:**  

* The WTI May 2020 contract fell to **-37 USD per barrel**.  
* Sellers were paying buyers to take oil off their hands because **storage costs exploded** beyond capacity.  

This was an extreme case of:  

* **Negative effective storage cost**,  
* A dramatic example of **backwardation**,  
* And the first time in history oil traded at **negative prices**.  

---

## 6. Key Takeaways

* **Fair value** links spot and futures prices through the cost of carry.  
* **Contango** is the normal case (positive r and s).  
* **Backwardation** arises when the **convenience yield** outweighs the cost of carry.  
* The **Covid oil crash of April 2020** is a real-world reminder that storage, liquidity, and convenience yield can flip the entire futures curve upside down.  

---

# 📒 Notes – Arbitrage & Relative Value (Fixed Income & Commodities)

## 1. Arbitrage pur (Cash-and-Carry)

**Formule de non-arbitrage (commodities)** :

\[
F_t = S_t \cdot e^{(r + c - y)T}
\]

* \(S_t\) = prix spot  
* \(F_t\) = prix future  
* \(r\) = taux sans risque  
* \(c\) = coût de stockage  
* \(y\) = convenience yield  

**Détection** :  
* Si \(F_t > F_{theo}\) → Cash-and-Carry (long spot, short future).  
* Si \(F_t < F_{theo}\) → Reverse Cash-and-Carry (short spot, long future).  

**PnL** : convergence spot/future → profit risk-free (hors coûts).  

En pratique : sur Treasuries et indices, ces écarts disparaissent très vite (HFT, C++).  
Bon pour projets académiques et GitHub (ex. Oil, Gold).  

---

## 2. Arbitrage sur Treasuries futures (CTD & Basis)

* **Cheapest To Deliver (CTD)** = obligation la moins chère à livrer sur un future.  

**Basis** :

\[
Basis = P_{CTD} - (F \cdot CF)
\]

où \(CF\) = conversion factor.  

**Implied Repo Rate (IRR)** :

\[
IRR = \frac{(Coupons + P_{CTD} - (F \cdot CF))}{F \cdot CF} \cdot \frac{360}{Jours}
\]

* Arbitrage : comparer IRR au repo de marché.  
* Pas toujours risk-free car : CTD peut changer, repo varie, liquidité CTD limitée.  

---

## 3. Relative Value (pas risk-free mais “desk-friendly”)

### Bond vs Bond

**Spread Bund–OAT** :

\[
Spread = YTM_{OAT} - YTM_{Bund}
\]

**Spread 10Y–30Y US** :

\[
Spread = YTM_{30Y} - YTM_{10Y}
\]

Stratégie : parier sur convergence/divergence (steepener/flattener).  

⚠️ Risques : macro, politique, corrélation imparfaite.  

---

### Swap vs Bond (Swap Spread)

**Formule** :

\[
SwapSpread = SwapRate_{T} - YTM_{Gov,T}
\]

Stratégie : long bond / short swap (ou inverse) si le spread s’écarte trop.  

⚠️ Risques : liquidité, différence collateral, risque crédit souverain.  

---

## 4. Points clés retenus

* **Arbitrage pur** (commodities, futures) → théorique, très rare en pratique.  
* **Relative Value trades** → quotidien des desks Fixed Income :  
  * Bond vs Futures (basis, CTD).  
  * Bond vs Bond (yield spreads, curve trades).  
  * Swap vs Bond (swap spreads).  
* Mémo : *“On vend toujours la partie la plus chère et on achète la moins chère.”*  
* Profit : garanti à maturité en théorie, mais en pratique on peut sortir plus tôt dès que l’écart se referme.  
* Tech : Python = parfait pour recherche/projets GitHub ; C++/Rust = requis pour HFT ultra-low-latency.  

---

# Yield Curve Arbitrage – [Reflection]

## 1. Core Idea

* Bond arbitrage does **not** bet on the absolute direction of interest rates, but on the **relative relationship between two maturities**.  
* Classic case: the **10Y–30Y spread**.  
* Goal: neutralize overall rate risk (DV01-neutral) and profit only from curve mispricing.  

---

## 2. Forward Rates & Arbitrage

**Forward rates** are the implied future rates derived from the spot curve.  

\[
(1+R_n)^n = (1+R_m)^m \cdot (1+f_{m,n})^{(n-m)}
\]

If there is a difference between the **implied forward rate** and the **observed rate**, this creates an arbitrage opportunity.  

---

## 3. Z-score of the Spread

A statistical tool to measure whether the 10Y–30Y spread is “abnormal.”  

\[
Z = \frac{Spread_t - \mu_{Spread}}{\sigma_{Spread}}
\]

* If \(Z > +2\) → spread too wide (flattener opportunity).  
* If \(Z < -2\) → spread too low (steepener opportunity).  

---

## 4. Vanilla Arbitrage 10Y–30Y

Instruments: **ZN (10Y futures), UB (30Y futures)**.  

**DV01-neutral hedge ratio** :

\[
h = \frac{DV01_{30Y}}{DV01_{10Y}} \approx 2.5
\]

Example trade:  
* Short 1 UB (30Y)  
* Long 2.5 ZN (10Y)  
* → Bet on **flattening** (spread too wide).  

---

## 5. Frequency of Opportunities

* Arbitrage setups are less frequent than directional trading:  
  * Daily data: 1–2 signals per week.  
  * Intraday (futures): more micro-mispricings, but often noisy.  
* Best opportunities usually occur around **macro releases** (CPI, NFP, FOMC) or **UST auctions**.  

---

## 6. Risk Management

* Neutralize DV01 to avoid exposure to global rate shifts.  
* Use a **Z-score stop** (e.g., exit if \(|Z| > 3\)).  
* Optional: hedge tail risk with **options on futures** (UB/ZN) or **swaptions**.  

---

