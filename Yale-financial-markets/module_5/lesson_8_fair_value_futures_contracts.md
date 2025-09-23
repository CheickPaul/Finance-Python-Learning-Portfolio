# [Fair Value in Futures Contracts]

## 1. Concept

The **fair value** of a futures contract is the theoretical price that reflects the cost of carrying the underlying asset until the delivery date.  
It ensures **no arbitrage** between the spot market and the futures market.

The standard formula is:

$$
F = S \times (1 + r + s)
$$

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

$$
F = S \times (1 + r + s - y)
$$

Where:  

* **y** = Convenience yield  

If:

$$
y > (r + s)
$$

then the futures curve goes into **backwardation**.  

---

## 4. Example: Wheat Shortage

Imagine a pasta manufacturer:

* **Spot wheat price** = €100 / ton  
* **Interest rate (r)** = 5%  
* **Storage cost (s)** = 3%  

**Normal fair value (contango):**

$$
F = 100 \times (1 + 0.05 + 0.03) = 108
$$

Now suppose there is a **bad harvest** and wheat is very scarce.  
The manufacturer is willing to pay €10/ton just to secure physical availability (convenience yield = 10%).  

$$
F = 100 \times (1 + 0.05 + 0.03 - 0.10) = 98
$$

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

**Formule de non-arbitrage (commodities):**

$$
F_t = S_t \cdot e^{(r + c - y)T}
$$

* \(S_t\) = prix spot  
* \(F_t\) = prix future  
* \(r\) = taux sans risque  
* \(c\) = coût de stockage  
* \(y\) = convenience yield  

**Détection:**  

* Si \(F_t > F_{theo}\) → Cash-and-Carry (long spot, short future).  
* Si \(F_t < F_{theo}\) → Reverse Cash-and-Carry (short spot, long future).  

**PnL:** convergence spot/future → profit risk-free (hors coûts).  

---

## 2. Arbitrage sur Treasuries futures (CTD & Basis)

**Basis:**

$$
Basis = P_{CTD} - (F \cdot CF)
$$

où \(CF\) = conversion factor.  

**Implied Repo Rate (IRR):**

$$
IRR = \frac{(Coupons + P_{CTD} - (F \cdot CF))}{F \cdot CF} \cdot \frac{360}{Jours}
$$

---

## 3. Relative Value (pas risk-free mais “desk-friendly”)

### Bond vs Bond

**Spread Bund–OAT:**

$$
Spread = YTM_{OAT} - YTM_{Bund}
$$

**Spread 10Y–30Y US:**

$$
Spread = YTM_{30Y} - YTM_{10Y}
$$

---

### Swap vs Bond (Swap Spread)

**Formule:**

$$
SwapSpread = SwapRate_{T} - YTM_{Gov,T}
$$

---

# Yield Curve Arbitrage – [Reflection]

## 1. Core Idea

Bond arbitrage does **not** bet on the absolute direction of interest rates, but on the **relative relationship between two maturities**.  

---

## 2. Forward Rates & Arbitrage

**Forward rate formula:**

$$
(1+R_n)^n = (1+R_m)^m \cdot (1+f_{m,n})^{(n-m)}
$$

---

## 3. Z-score of the Spread

**Formula:**

$$
Z = \frac{Spread_t - \mu_{Spread}}{\sigma_{Spread}}
$$

---

## 4. Vanilla Arbitrage 10Y–30Y

**DV01-neutral hedge ratio:**

$$
h = \frac{DV01_{30Y}}{DV01_{10Y}} \approx 2.5
$$

---

