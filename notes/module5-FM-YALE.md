[Salon - Student Loans]

# Student Loans – Yale Financial Markets

## Overview

This module from Yale University’s *Financial Markets* course explores the structure of student loans, the risks of rising debt, and possible alternatives such as income-contingent repayment models.

---

## Key Concepts

### 1. Student Loan as a Bond

* A student loan can be viewed as a **bond issued by the student** to finance higher education.

### 2. Equity Model & Income-Contingent Loans

* Proposal: **Income-contingent repayment contracts** instead of fixed loans.
* Protects students who fail to secure high-paying jobs.
* Historical example: **Yale experiment in the 1970s (with James Tobin)**.
* Challenges:

  * **Moral hazard** – incentives to underreport income.
  * **Unintended cases** – e.g., marrying a wealthy spouse increased repayment obligations.

### 3. The Student Loan Bubble

* Indications of a **bubble in the U.S.**:

  * Rising anxiety about automation and AI drives young people to pursue costly education for status.
  * In the U.S., education serves as a **status symbol** (no aristocracy, prestige through degrees).
  * High willingness to borrow despite soaring tuition.

### 4. Post-2008 Context

* Government support for universities declined after the financial crisis.
* Even **public universities became expensive**.
* Students increasingly rely on **debt to finance higher education**.

### 5. Bankruptcy Constraint

* Student loans are **not dischargeable in bankruptcy** in the U.S.
* Exception: some **international MBA loans** permit bankruptcy, though discouraged.

---

## Takeaway

The U.S. student loan system combines **high tuition costs**, **social pressure**, and **strict repayment rules**, making it financially risky.

* **Income-contingent loans** may reduce risks but require careful design.
* The market exhibits **bubble-like characteristics**: rising costs, high borrowing, and uncertain returns.

## [Forwards and Futures Introduction ]

# Forwards and Futures – Introduction (Yale University)

## Overview

Forwards and futures are **derivative contracts** that involve transactions for **future delivery**, as opposed to the spot market which settles immediately. They are fundamental to modern financial markets because they allow us to **incorporate time into pricing**, producing an entire curve of prices for different delivery dates rather than a single spot price.

---

## Key Points

### 1. Function vs. Perception

* Public often misperceives futures as **gambling arenas** for the rich.
* In reality, they serve a **critical economic function**, linking financial contracts to real business activities (e.g., grain, pork bellies).
* Gambling is entertainment; futures exist to manage **real risks in production and consumption**.

### 2. Speculation and Storage

* **Public perception:** many believe speculation creates shortages. In a 1990 survey, most Americans thought storing grain makes shortages **more frequent**.
* **Economic reality:** production (e.g., grain harvest) is seasonal, so storage is essential to smooth consumption across the year. Without storage, food would need to be consumed immediately after harvest.
* **Role of speculators:**

  * Buy when prices are low (after harvest), store the commodity.
  * Sell when prices are higher (later in the year), releasing supply to the market.
* This process:

  * Prevents severe shortages during off-season.
  * Stabilizes prices over time.
  * Ensures continuous availability of essential goods like bread or cereals.
* **Conclusion:** far from causing scarcity, speculation and storage provide **market stability** and guarantee that resources are available when needed.

### 3. Futures Market Development

* Success of a futures market is unpredictable → the **“spaghetti rule”**: throw it against the wall and see if it sticks.
* Example: Shiller & Karl Case helped launch the **Home Price Futures** (Chicago Mercantile Exchange).

  * Conceptually relevant (housing risk is huge).
  * Limited adoption → shows that **social dynamics and user base** matter as much as economic rationale.

### 4. Why Some Markets Succeed, Others Fail

* Successful futures markets usually emerge where:

  * Risk is **large, concentrated, and felt by professional risk managers**.
  * Market participants have incentives to **hedge actively**.
* Less success in areas like single-family homes → owners are **long-term holders**, not active hedgers.

---

## Insights

* Futures markets reflect **risk management needs** more than pure speculation.
* Their existence is a **social and economic phenomenon**, not purely technical.
* Futures transform the way economies deal with **time, uncertainty, and storage**.

## [ Forward Contracts ]

## Definition

A **forward contract** is a private agreement between two parties (counterparties) to deliver an asset at a future date (maturity/exercise date) at a pre-agreed price.
Historically, forwards preceded the development of futures markets.

## Origins

* Example: **Dojima rice market (Japan, 1670s)**.
  Farmers could either:

  * Wait until harvest and sell at the spot price (uncertain).
  * Or lock in a forward price with a warehouse, reducing uncertainty.
* Farmers prefer forwards to reduce price risk after incurring high production costs.

## Hedgers vs. Speculators

* **Farmers:** usually avoid futures markets (too complex) but lock in forward prices.
* **Warehouses / grain elevators:** act as **hedgers**, since storage is a low-margin business. They often hedge their own positions in futures markets.

## Characteristics of Forward Contracts

* Flexible: customized contracts (quantity, quality, delivery date, location).
* Illiquid: cannot easily exit before maturity.
* Counterparty risk: dependent on the creditworthiness of the other party (e.g., farmer may default).
* Limited scalability: must evaluate and trust each counterparty.

## Futures vs. Forwards

* **Forwards:** bilateral, customized, with counterparty risk.
* **Futures:** standardized, exchange-traded, margin system removes counterparty risk (exchange is the counterparty).
* **Liquidity:** futures markets are much more liquid (can enter and exit positions freely).

## FX Forwards and Arbitrage

* Example: Japanese exporter selling in the US.

* Instead of using an FX forward, they can:

  1. Borrow in USD.
  2. Convert USD at spot into JPY.
  3. Invest in Japan at JPY interest rate.

* At maturity, payoff equals:

  $$
  F = S \times \frac{(1 + r_{¥})}{(1 + r_{\$})}
  $$

  where:

  * $F$ = forward exchange rate
  * $S$ = spot exchange rate
  * $r_{¥}$ = Japanese interest rate
  * $$r_{\$}$$ = US interest rate

* By **arbitrage**, the forward exchange rate must equal this ratio.

* This is called **Covered Interest Parity (CIP)**.

## Forward Rate Agreements (FRAs)

* Settlement formula (simplified):

  $$
  \text{Payoff} = (R_{mkt} - R_{contract}) \times \frac{\text{days}}{B} \times \text{Notional}
  $$

  where:

  * $R_{mkt}$ = realized market interest rate
  * $R_{contract}$ = agreed forward rate
  * $B$ = day-count convention (360 or 365)

Ah, je vois le souci : parfois GitHub ne rend pas bien les tableaux si l’alignement ou les espaces ne sont pas corrects.
Voici une version **Markdown propre et compatible GitHub** :

```markdown
# Differences between **Forwards** and **Futures**

| Characteristic        | Forward Contract (OTC)                     | Futures Contract (Exchange)                 |
|-----------------------|---------------------------------------------|---------------------------------------------|
| Nature of contract    | Private agreement (OTC – Over The Counter) | Standardized contract, traded on exchange   |
| Customization         | Flexible: amount, quality, date, location  | Standardized: contract sizes, maturities    |
| Counterparty risk     | Present: depends on partner’s solvency     | Reduced: clearinghouse acts as counterparty |
| Liquidity             | Low, difficult to exit before maturity     | High, easy to open/close positions          |
| Settlement            | At maturity (physical or cash settlement)  | Daily (mark-to-market, margin adjustments)  |
| Typical users         | Corporates, banks, specific needs          | Traders, investors, institutional hedgers   |
| Usage example         | Exporter fixing a custom FX rate           | Trader hedging oil, wheat, or interest rates|
```

---
## [Futures Contract]

```markdown
# Forward Contracts

## Definition
A **forward contract** is a private agreement between two parties (counterparties) to deliver an asset at a future date (maturity date) at a pre-agreed price.  
Historically, forward contracts preceded the development of standardized futures markets.

---

## Historical Origins
- Example: **Dojima Rice Market (Japan, 1670s)**.  
  Farmers could either:  
  - Wait until harvest and sell at the spot price (uncertain), or  
  - Lock in a forward price with a warehouse to reduce price risk.  
- Farmers preferred forwards to limit the risk of low prices after investing heavily in production.  
- Warehouses/grain elevators, operating on thin margins, acted as **hedgers** and often hedged themselves in futures markets.

---

## Key Characteristics of Forwards
- **Flexible**: customized contracts (amount, quality, delivery date, location).  
- **Illiquid**: cannot easily exit before maturity.  
- **Counterparty risk**: performance depends on the partner’s creditworthiness.  
- **Limited scalability**: each contract requires trust and credit evaluation.

---

## Forwards vs. Futures

| Characteristic        | Forward Contract (OTC)                     | Futures Contract (Exchange)                 |
|-----------------------|---------------------------------------------|---------------------------------------------|
| Nature of contract    | Private agreement (OTC – Over The Counter) | Standardized contract, traded on exchange   |
| Customization         | Flexible: amount, quality, date, location  | Standardized: contract sizes, maturities    |
| Counterparty risk     | Present: depends on partner’s solvency     | Reduced: clearinghouse acts as counterparty |
| Liquidity             | Low, difficult to exit before maturity     | High, easy to open/close positions          |
| Settlement            | At maturity (physical or cash settlement)  | Daily (mark-to-market, margin adjustments)  |
| Typical users         | Corporates, banks, specific needs          | Traders, investors, institutional hedgers   |
| Usage example         | Exporter fixing a custom FX rate           | Trader hedging oil, wheat, or interest rates|

👉 **Summary:** Forwards are customized but riskier and less liquid. Futures are standardized, safer, and more liquid.

---

## FX Forwards and Covered Interest Parity (CIP)
Forward contracts are widely used in currency markets.  
Example: A Japanese exporter selling goods in the US receives USD but wants to repatriate yen.  

Instead of taking FX risk, the exporter can lock in a **forward exchange rate**.  
Alternatively, the position can be **replicated in the money market**:

1. Borrow USD.  
2. Convert USD into JPY at the spot rate.  
3. Invest JPY at the Japanese interest rate.  
4. Repay the USD loan at maturity.  

This leads to the **CIP formula**:

\[
F_{DC/FC} = S_{DC/FC} \times \frac{1+r_{DC}\,\tau}{1+r_{FC}\,\tau}
\]

where:  
- \(F_{DC/FC}\) = forward exchange rate (domestic currency per 1 unit of foreign currency)  
- \(S_{DC/FC}\) = spot exchange rate  
- \(r_{DC}\) = domestic interest rate  
- \(r_{FC}\) = foreign interest rate  
- \(\tau\) = time to maturity (in years, day-count adjusted)  

👉 This ensures **no-arbitrage** between forward contracts and money market replication.

---

## Forward Rate Agreements (FRAs)
Another form of forward contract applies to **interest rates**.  
Settlement formula (simplified):

\[
\text{Payoff} = (R_{mkt} - R_{contract}) \times \frac{\text{days}}{B} \times \text{Notional}
\]

where:  
- \(R_{mkt}\) = realized market rate at maturity  
- \(R_{contract}\) = forward rate agreed in the contract  
- \(B\) = day-count basis (360 or 365 days)  

---

## How Banks Hedge and Profit on FX Forwards

### 1. Money Market Replication
Banks do not stay exposed to FX risk. They replicate the forward contract using money market operations:  

- **If client BUYS foreign currency forward (long FC):**  
  - Bank borrows domestic currency (DC)  
  - Converts to foreign currency (FC) at spot  
  - Invests FC at the foreign rate  
  - At maturity: delivers FC to the client, repays DC loan  

- **If client SELLS foreign currency forward (short FC):**  
  - Bank borrows FC  
  - Sells FC for DC at spot  
  - Invests DC at the domestic rate  
  - At maturity: delivers DC proceeds, repays FC loan  

This hedging leaves the bank **currency-neutral**.

---

### 2. Profit Mechanism
- The **theoretical forward rate** is given by CIP.  
- Banks quote a slightly less favorable rate to clients (bid-ask spread).  
- Example:  
  - CIP forward = 110.00 ¥/$  
  - Bank quotes 110.10 for clients buying USD, 109.90 for clients selling USD  
  - The **0.20 spread** is the bank’s margin.  

---

### 3. Why Banks Have an Advantage
- **Lower funding costs** on interbank markets.  
- **Better liquidity access** via swaps and deposits.  
- **Convenience for clients**: companies prefer a simple forward instead of juggling multiple loans and deposits.  

👉 **Conclusion:** Banks hedge FX forwards through replication in the money market and profit from the **spread between CIP and client quotes**, plus possible service or credit premiums.

## [Rice Futures]

# Rice Futures – Historical Origins and Hedging Strategies

## 1. Origins of Futures Markets

* The first organized **futures market** appeared in **Osaka, Japan (Dojima)** during the **1670s**.
* Dojima served as Japan’s main rice storage hub, with **91 warehouses recorded in 1673**.
* Traders began using contracts for **future delivery of rice**, called *rice bills*.
* Standardization emerged with **delivery dates, quality definitions, and locations**, forming the foundation of modern futures contracts.

---

## 2. Dojima Rice Exchange

* Specialists assessed the **quality of rice** to enforce contracts.
* Farmers could **sell contracts to offset obligations** if their crop changed, creating **liquidity**.
* The market became not just about physical delivery, but about **hedging and price discovery**.

---

## 3. Evolution to Modern Markets

* Rice futures remained central in Japan until **World War II**, after which Chicago became the hub.
* The **Chicago Board of Trade (CBOT)** later merged into the **CME Group (2007)**.
* Today, rice futures still trade, but delivery occurs in the U.S., not in Dojima.

---

## 4. Standardized Contracts

* Example: **1 rice futures contract = 2,000 hundredweights (\~91 metric tons)**.
* Contracts define:

  * Type/quality of rice (e.g., *U.S. #2 or better, long grain*).
  * Delivery standards.
  * Tick size for price movements.
* Standardization ensures **clarity and liquidity**.

---

## 5. Hedging with Futures

* **Futures = lock in a price.**
* Example:

  * A farmer sells futures to **protect against price drops**.
  * An airline buys futures to **protect against fuel price increases**.
* **Key advantage:**

  * No upfront cost (only margin).
  * Provides **certainty and stable cash flow**.
* **Limitation:**

  * Gains from favorable price moves are lost → you only secure stability.

---

## 6. Hedging with Options

* **Options = flexible insurance.**
* A **put** protects against price falls (producers).
* A **call** protects against price rises (consumers).
* **Key advantage:**

  * Protection against adverse moves while keeping upside potential.
  * Loss limited to the option premium (no margin calls).
* **Limitation:**

  * More expensive (option premium).
  * Less liquid than futures in some markets.

---

## 7. Futures vs Options in Hedging

| Aspect      | Futures                         | Options                               |
| ----------- | ------------------------------- | ------------------------------------- |
| Cost        | No premium, only margin         | Premium required upfront              |
| Risk        | Locks in a fixed price          | Loss limited to premium               |
| Flexibility | No benefit from favorable moves | Benefit if market moves in your favor |
| Best for    | Pure stability, budget planning | Asymmetric protection, flexibility    |

---

## 8. Roles in Markets

* **Hedgers** → Seek **stability, not profit** (farmers, airlines, manufacturers).
* **Speculators** → Take risk, provide **liquidity** to hedgers.
* **Arbitrageurs** → Exploit price differences between spot and futures.

---

## 9. Key Takeaways

* Futures markets started with **rice in Dojima (1670s)**.
* Modern rice futures are traded at the **CBOT/CME Group**.
* **Futures** = insurance with fixed certainty (but no upside).
* **Options** = insurance with flexibility (but more costly).
* Hedgers and speculators are **complementary**, making markets function.

---

## [Wheat Futures ]

## Overview

This note summarizes the main concepts from the lecture on **wheat futures**. Futures markets are often criticized for volatility, but they play a fundamental role in **risk management (hedging)** and **price discovery**.

## Speculators vs. Hedgers

* **Hedgers**: Producers or consumers of commodities who use futures to protect against price risk.
  *Example*: A farmer who stores wheat and wants to lock in a price before selling after the harvest.

* **Speculators**: Traders who take positions without owning the underlying commodity.
  *Key role*:

  * They think broadly about international politics, technology, and supply/demand shifts.
  * They provide liquidity and contribute to accurate pricing.
  * Unlike gamblers (who seek entertainment), speculators act on informed beliefs about mispriced markets.

Shiller emphasizes that speculation is not gambling but rather a **noble profession**, necessary for efficient markets.

## Wheat Futures Contract

* Underlying: **Soft Red Winter Wheat** (commonly used for cakes, cookies, cereals).
* Pricing: Quoted in **cents per bushel**.
* Contract size: **1,000 bushels**.
* Tick size: **1/8 cent per bushel = \$1.25 per contract**.

### Agricultural cycle

* **Winter wheat** is planted in fall, lies dormant in winter, and is harvested in spring (around May).
* This seasonal structure creates predictable patterns in the futures curve.

## Futures Curve Dynamics

* **Contango**: Futures price above spot price, often linked to storage costs.
* **Backwardation**: Futures below spot price, often around harvest periods when supply surges.
* Example (2016–2018 data):

  * Futures often decline around May (harvest time).
  * Before harvest: risk of shortages pushes prices up.
  * After harvest: abundance pushes prices down.

This illustrates how futures markets smooth supply shocks and provide **price discovery**.

## Price Discovery & Market Function

* Futures allow producers and consumers to anticipate shortages or surpluses.
* Example: If futures show a sharp drop in May, it signals expected harvest abundance.
* The system reduces volatility by letting the market adjust before shocks occur.

## Analogy – Squirrels & Acorns

Shiller compares wheat futures to squirrels managing acorn storage:

* In bad years, squirrels face scarcity during winter.
* If squirrels had a futures market for acorns, they could hedge against shortages.
* This analogy highlights the **universal logic of storage, scarcity, and forward planning** in futures markets.

---

[Buying, Selling, and Settlement ]
## 1. Historical Origins – Dojima Exchange

* The first futures market dates back to **Dojima (Japan, 18th century)**.
* Traders used **hand signals** (“pit trading”) to communicate buy/sell orders.
* Trading sessions were timed with a **burning fuse**; “water men” stopped late trades with buckets of water.
* These practices inspired modern futures markets such as the CME (Chicago Mercantile Exchange).

## 2. Daily Settlement and Margin Accounts

* Futures contracts are marked-to-market **daily**.
* A **margin account** is adjusted each day by the change in settlement price × contract size.
* The **settlement price** is not always the last trade of the day (to avoid manipulation). It is chosen by a settlement committee.

## 3. Physical Delivery Futures

* If a futures contract is not closed before expiration:

  * **Seller (short)** must **deliver** the underlying commodity/asset.
  * **Buyer (long)** must **receive** the commodity/asset.
* Most financial traders avoid physical delivery and close their positions before expiration.
* Only **hedgers** (farmers, refiners, bond dealers) typically go to delivery.

### Practical Examples

* **Corn Futures**: A farmer short contracts delivers bushels; a food processor long contracts receives them.
* **Oil Futures (WTI, Brent)**:

  * Standard contract size = **1,000 barrels**.
  * Delivery point for WTI = **Cushing, Oklahoma**.
  * Financial traders exit before the **First Notice Day (FND)** to avoid delivery.
* **Ultra Bond Futures (UB30)**:

  * Physically settled in a **basket of U.S. Treasury Bonds** with ≥ 25 years maturity.
  * The seller (short) chooses which bond to deliver (*cheapest-to-deliver*).
  * This delivery option and the **conversion factor** are central to pricing in fixed income futures.

## 4. Arbitrage and Convergence

* Futures prices tend to converge with the **spot price** at expiration.
* Example: if futures < spot, arbitrageurs buy futures, take delivery, and sell spot.
* This **enforces efficiency** and keeps futures aligned with underlying market prices.

## 5. Cash-Settled Futures

* Introduced in the late 20th century, cash settlement enables futures on assets that cannot be delivered physically.
* **Examples**:

  * **S\&P 500 Futures**: Standard (\$250 × index) and E-mini (\$50 × index). Settled in cash based on index value.
  * **Housing Price Futures**: Cannot deliver physical homes, so only cash settlement applies.
* **Advantages**:

  * Simpler arbitrage (automatic cash adjustment).
  * Broader scope: indices, housing, volatility, etc.

## 6. Key Takeaways

* Futures markets evolved from physical commodity trade to **cash-settled financial instruments**.
* **Daily settlement and margins** reduce counterparty risk.
* **Physical delivery** is real (oil, bonds, grains) but avoided by most financial traders.
* **Cash settlement** expanded derivatives to indices and non-standardized assets.
* For traders:

  * **Oil Futures and UB30 Futures are physically settled**.
  * Brokers typically require positions to be closed before delivery deadlines.
  * Industrial participants (refiners, bond dealers) are the ones who actually take/make delivery.

[Fair Value in Futures Contracts]
Parfait 👌 voici la version complète de ton **README en anglais** intégrant le concept de **Fair Value**, **Contango**, **Backwardation**, le rôle du **Convenience Yield**, et l’exemple du **pétrole pendant le Covid** :

---

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

If **y > (r + s)** → the futures curve goes into **backwardation**.

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

## [Oil Futures] 

## 1. Market Structure

* **Light Sweet Crude Oil** is the flagship futures contract, traded at **NYMEX (now part of CME Group)**.
* **Contract size**: 1,000 barrels.
* Global benchmarks:

  * **WTI (West Texas Intermediate)** → NYMEX.
  * **Brent Crude** → ICE (London).
* Contracts are **physically delivered**, but most traders offset their positions before expiration.

## 2. Futures Curve and Contango

* Example (March 2016): the oil futures curve was in **contango** (upward sloping).
* The slope reflects:

  * **Interest rates**.
  * **Storage costs**.
  * **Market expectations** about future oil prices.

## 3. Oil Market Specificities

* Most oil is kept **in the ground** (natural storage).
* Limited above-ground storage capacity makes carrying costs special.
* **Refineries** usually purchase through **long-term contracts**; the spot market is small but serves as a reference for volatility.

## 4. Price History

* In **real terms**, oil is **cheaper today than in 1871**, unlike equities which trended upwards.
* Prices were **artificially stabilized** by the **Texas Railroad Commission** (1917–1970).
* After 1973 → end of control, start of high volatility.

## 5. OPEC and Oil Shocks

* **OPEC founded in 1960** to act as a price-fixing cartel.
* **First oil shock (1973)**: Arab embargo during the Yom-Kippur war.
* **Second oil shock (1979–80)**: Iranian Revolution + Gulf War.
* Result: **worldwide recessions** and US stock market crashes.

## 6. Strategic Reserves

* **US Strategic Petroleum Reserve (SPR)**: \~60 days of supply.
* Purpose: national security in case of war or severe crisis, not to smooth prices.
* Example: **Heating Oil Reserve** (New York/New England).

## 7. Volatility and Technology

* 2000s: extreme volatility (from \$113/barrel in 2008 down to <\$30 in 2016).
* **Fracking** boosted supply, putting downward pressure on prices.
* Oil remains highly sensitive to **political events** (wars, embargoes, OPEC actions).

## 8. Speculation and Manipulation

* **Speculators** provide liquidity and forecasting, but also create **excess volatility**.
* **Market manipulation** exists, but is limited by **exchange surveillance**.
* Without speculators, markets would be **less efficient**.

---

Parfait 👌 voici un **récapitulatif clair et structuré** que tu peux mettre en **README ou note GitHub**.

---

# 📒 Notes – Arbitrage & Relative Value (Fixed Income & Commodities)

## 1. Arbitrage pur (Cash-and-Carry)

* **Formule de non-arbitrage (commodities)** :

  $$
  F_t = S_t \cdot e^{(r + c - y)T}
  $$

  * $S_t$ = prix spot
  * $F_t$ = prix future
  * $r$ = taux sans risque
  * $c$ = coût de stockage
  * $y$ = convenience yield

* **Détection** :

  * Si $F_t > F_{theo}$ → Cash-and-Carry (long spot, short future).
  * Si $F_t < F_{theo}$ → Reverse Cash-and-Carry (short spot, long future).

* **PnL** : convergence spot/future → profit risk-free (hors coûts).

👉 En pratique : sur Treasuries et indices, ces écarts disparaissent très vite (HFT, C++).
👉 Bon pour projets académiques et GitHub (ex. Oil, Gold).

---

## 2. Arbitrage sur Treasuries futures (CTD & Basis)

* **Cheapest To Deliver (CTD)** = obligation la moins chère à livrer sur un future.

* **Basis** :

  $$
  Basis = P_{CTD} - (F \cdot CF)
  $$

  où $CF$ = conversion factor.

* **Implied Repo Rate (IRR)** :

  $$
  IRR = \frac{(Coupons + P_{CTD} - (F \cdot CF))}{F \cdot CF} \cdot \frac{360}{Jours}
  $$

* Arbitrage : comparer IRR au repo de marché.

* Pas toujours risk-free car : CTD peut changer, repo varie, liquidité CTD limitée.

---

## 3. Relative Value (pas risk-free mais “desk-friendly”)

### 🔹 Bond vs Bond

* **Spread Bund–OAT** :

  $$
  Spread = YTM_{OAT} - YTM_{Bund}
  $$
* **Spread 10Y–30Y US** :

  $$
  Spread = YTM_{30Y} - YTM_{10Y}
  $$
* Stratégie : parier sur convergence/divergence (steepener/flattener).

⚠️ Risques : macro, politique, corrélation imparfaite.

---

### 🔹 Swap vs Bond (Swap Spread)

* **Formule** :

  $$
  SwapSpread = SwapRate_{T} - YTM_{Gov,T}
  $$
* Stratégie : long bond / short swap (ou inverse) si le spread s’écarte trop.

⚠️ Risques : liquidité, différence collateral, risque crédit souverain.

---

## 4. Points clés retenus

* **Arbitrage pur** (commodities, futures) → théorique, très rare en pratique.
* **Relative Value trades** → quotidien des desks Fixed Income :

  * Bond vs Futures (basis, CTD).
  * Bond vs Bond (yield spreads, curve trades).
  * Swap vs Bond (swap spreads).
* **Mémo** : *“On vend toujours la partie la plus chère et on achète la moins chère.”*
* **Profit** : garanti à maturité en théorie, mais en pratique on peut sortir plus tôt dès que l’écart se referme.
* **Tech** : Python = parfait pour recherche/projets GitHub ; C++/Rust = requis pour HFT ultra-low-latency.

---


# [ Financial Futures: S\&P 500 Index & Federal Funds Rate ]

## 1. S\&P 500 Futures (Index Futures)

* **Type**: Cash-settled (no physical delivery).
* **Settlement Formula**:

  $$
  \text{Settlement Value} = 250 \times (\text{Index Level on Last Day} - \text{Futures Price on Previous Day})
  $$
* **Fair Value Formula**:

  $$
  F = S \times (1 + r - y)
  $$

  where:

  * $S$ = Spot price of the index.
  * $r$ = Risk-free rate.
  * $y$ = Dividend yield (acts like a *negative storage cost*).

👉 Intuition: Holding stocks pays dividends, so the cost of carry is adjusted downward by the dividend yield.

---

## 2. Federal Funds Rate (FFR) Futures

* **Launched**: Chicago Board of Trade (1988).
* **Underlying**: The overnight **federal funds rate** (interbank lending rate targeted by the Fed).
* **Settlement**: Cash-settled.

  $$
  \text{Price} = 100 - \text{Annualized FFR (average over contract month)}
  $$
* **Usage**:

  * Barometer of **market expectations** for upcoming **Federal Open Market Committee (FOMC)** decisions.
  * Example: If FFR futures trade at 97.75 → implied FFR = **2.25%**.

👉 Different from commodities or index futures: no arbitrage pricing model, because an **interest rate cannot be stored**.

---

## 3. Predictive Value of FFR Futures

### Why They Are Predictive

* The Fed’s decision (target rate) is **clear and binary**.
* FFR futures prices directly encode what the market expects that decision to be.

### Why They Work Well

* **Clear outcome** → Fed announces a target rate.
* **Near-term horizon** → contracts focus on the next few months.
* **High attention** → speculators and analysts study the Fed intensively.

### Comparison with Stock Market Predictions

| Aspect                | FFR Futures                        | Stock Market (Equities)                  |
| --------------------- | ---------------------------------- | ---------------------------------------- |
| **Prediction target** | Next Fed decision (rate level)     | Long-term dividends/earnings             |
| **Time horizon**      | Weeks / months                     | Many years / indefinite                  |
| **Uncertainty**       | Low (binary, well-defined outcome) | High (economic cycles, innovation, etc.) |
| **Efficiency**        | High – strong short-term predictor | Weaker – noisy long-term predictor       |

---

## 📌 Key Takeaways

* **Index futures** follow a cost-of-carry model adjusted for dividends.
* **FFR futures** are pure prediction markets for Fed policy.
* Prediction markets work best when the outcome is:

  * Short-term
  * Clear
  * Widely studied

---


## [Options Overview ]

## 1. Definition

* **Option = Contract** between two parties:

  * **Buyer (Holder)** → has the right (not the obligation).
  * **Seller (Writer)** → has the obligation if the buyer exercises.
* Two types:

  * **Call Option** → right to buy.
  * **Put Option** → right to sell.

## 2. Difference vs Forward Contract

* **Forward**: binding obligation → both buyer and seller must transact at the future date/price.
* **Option**: gives the buyer **choice**:

  * Exercise only if it is profitable.
  * Seller receives a **premium** as compensation for taking on that risk.

## 3. Economic Logic

* Buyer will exercise **only if beneficial**:

  * Call → exercised if *market price > strike price*.
  * Put → exercised if *market price < strike price*.
* If not, option expires worthless.

## 4. Contract Terms

* **Expiration (Exercise Date)**: last day option can be used.
* **Strike Price (Exercise Price)**: fixed price at which transaction occurs.
* **Underlying Asset**: stock, bond, commodity, land, etc.
* **Quantity**: specifies how many units (e.g., 100 shares).

## 5. Conceptual View

* **Options are truncated claims**:

  * Call → claim on upside *above strike*.
  * Put → claim on downside *below strike*.
* They allow participation in favorable movements while limiting exposure.

---

## 6. Real Estate Options (Applied Example)

Options are not limited to financial markets. In the **U.S. real estate sector**, they are widely used in development projects:

### How it works

* A **developer** identifies land (e.g., farmland near a city) as a potential site for a shopping mall, office complex, or housing project.
* Instead of committing millions upfront, the developer signs an **option contract** with the landowner:

  * Pays a **premium** today (non-refundable).
  * Gains the **right (not obligation)** to purchase the land later at an agreed strike price.
* If the project receives approvals and financing → developer exercises the option.
* If the project is canceled → the landowner keeps the premium, and the developer loses only this cost.

### Why developers use real estate options

* **Risk management**: limits exposure while awaiting zoning, permits, or financing.
* **Flexibility**: allows developers to secure strategic land without immediate purchase.
* **Leverage**: developer can negotiate financing or attract investors while holding the option.
* **Win-win**: landowner earns immediate premium even if the sale never happens.

### Examples in the U.S.

* **Urban development**: City agencies (e.g., CRA/LA in Los Angeles) use land options to manage long-term property development without binding commitments.
* **Agriculture**: Farmers grant land options to developers or neighbors for future consolidation or succession planning.
* **Residential real estate**: Lease-option agreements let tenants rent with the right to purchase later (part of rent sometimes credited to purchase price).
* **Private projects**: Companies such as Gold Energy, LLC have signed option agreements with community development corporations to acquire land for future expansion.

### Legal considerations

* Courts in states like **Texas and New York** require precise drafting: the property, price, and option terms must be clearly stated.
* In bankruptcy cases, option rights can sometimes survive, giving the option holder strong legal protection.

---

## 7. Key Takeaways

* Options provide **choice + flexibility** versus forwards (which are obligations).
* In finance, they allow exposure to upside/downside with limited risk.
* In real estate, they are powerful tools for **developers, cities, and investors** to secure opportunities while managing uncertainty.

---

## [Reading Options Pricing] 

## 1. Historical Origins

* The **first documented options** come from Holland (1600s – 1730).
* Example: option on shares of the Dutch East India Company (VOC).
* Even then: **printed contracts** with handwritten blanks → early standardization → a step toward the information age.

---

## 2. Modern Example: Intel Options (CBOE)

* **Underlying**: Intel stock (INTC), price \~31.63 USD (previous Friday close).
* **Dividend**: 0.26 USD per share quarterly.
* **Ticker**: INTC (4 letters → Nasdaq-listed).

### Strike Prices

* 27, 30, 32, 35 USD.
* Current price = 31 USD → some options are **in the money (ITM)**, others **out of the money (OTM)**.

---

## 3. Why Buy an OTM Option?

* Example: **Call strike 35 USD**, premium = 2.36 USD.
* Not rational if compared directly to the stock (31 < 35).
* But it has **speculative value**: if the stock rises above 35, the option gains value.
* Advantage: **limited loss** (max = premium 2.36) vs potential total loss if buying stock at 31.

---

## 4. Example of ITM Option

* **Call strike 27 USD**, premium = 7 USD.
* Immediate exercise profit = 31.63 – 27 = 4.63 USD.
* But since premium paid = 7 > 4.63, **early exercise = loss**.
* ➝ Usually you **do not exercise early**: keep the **time value** (option value).

---

## 5. Bid-Ask Spread and Market Makers

* Quoted price = **last traded price**.
* Actual market:

  * **Bid** = price dealers pay to buy.
  * **Ask** = price dealers charge to sell.
* Example: bid = 6.05, ask = 6.20 → spread = 0.15.
* This spread = **market maker’s profit margin**.
* More liquid strikes (e.g., 35) → **narrower spreads**.

---

## 6. Option Moneyness (ITM / OTM / ATM)

### Call Options (right to buy)

* **In the Money (ITM)**: Stock price **> Strike** → profitable to exercise.
* **At the Money (ATM)**: Stock price **≈ Strike** → mostly time value.
* **Out of the Money (OTM)**: Stock price **< Strike** → no intrinsic value, only time value.

### Put Options (right to sell)

* **In the Money (ITM)**: Stock price **< Strike** → profitable to exercise.
* **At the Money (ATM)**: Stock price **≈ Strike** → mostly time value.
* **Out of the Money (OTM)**: Stock price **> Strike** → no intrinsic value, only time value.

---

## ✅ Key Takeaways

1. Options combine **intrinsic value** (strike vs spot) and **time value** (future potential).
2. Do not exercise early: keep the **option value**.
3. **Bid-ask spreads** compensate market makers.
4. **Liquidity** reduces spreads (most traded strikes = most competitive).
5. **Moneyness** (ITM/OTM/ATM) determines intrinsic vs time value.

---

Here’s a clean README-style note in English based on the lecture *Why Options Exist* (Yale, Robert Shiller):

---

##  [Why Options Exist]

## 1. Theoretical Justification

* **Kenneth Arrow**: argued that economic efficiency requires that *all risks are tradable*.

  * A stock is not just “one risk,” but a bundle of risks (different strike levels, maturities).
  * Options allow the market to **dissect risk** into finer components.
* **Stephen Ross (1976 – *Options and Efficiency*)**:

  * A complete set of options helps *complete the market*.
  * By introducing options with different strikes and maturities, investors can trade specific risk slices.

**Conclusion:** Options exist to improve economic efficiency by enabling risk sharing and completing markets.

---

## 2. Behavioral Justification

* People do not always act rationally or consider their portfolio as a whole.
* **Salience & Overreaction**: After disasters, people suddenly buy insurance (e.g., flood insurance), even though the risk was always there.
* **Put Options = Insurance**:

  * Example: An investor buys a put option to protect against a stock drop.
  * Creates a **“floor”** on losses.
* **Silver Lining Theory (Shefrin & Statman)**:

  * Investors focus on partial outcomes rather than the full portfolio.
  * Even if overall losses occur, having puts provides a “silver lining” → emotional comfort.

---

## 3. Sales & Misuse of Options

* Options can also be **used by salesmen to manipulate investors**.
* Example from *The Art of Selling Intangibles*:

  * A stockbroker convinces a client to write (sell) calls on their stock.
  * Presents it as having **“three sources of profit”**:

    1. Premium from selling the call.
    2. Dividends from stock ownership.
    3. Gain up to the strike price.
  * The downside (loss of unlimited upside) is minimized or hidden.
* **Key Issue:** Investors should look at the **total expected return**, not be misled by “three separate sources.”

---

## 4. Summary

* **Theory**: Options complete markets by making all risks tradable.
* **Behavior**: Options cater to psychological biases (insurance, silver lining, emotional comfort).
* **Sales Practices**: Options can be exploited to mislead uninformed investors.

---

Parfait, voici la traduction en anglais de ton README :

---

## [Ubiquity of Options]

### 1. Options are not limited to stocks

* An **option** is a right (but not an obligation).
* Example: **mortgages** actually contain an embedded option.

  * In some **“recourse” states** (e.g., Connecticut):
    → If you stop paying your mortgage, the bank can **sue you**, garnish your wages, or seize other assets.
    → There is **no real option** here: you must pay no matter what.
  * In **“non-recourse” states** (e.g., California):
    → If you default, the bank can only **take back the house**, but cannot touch your salary or other assets.
    → Therefore, you have an **implicit option**: you can “walk away” if the house value drops below your mortgage.
    → This is called *“jingle mail”*: people used to mail their house keys to the bank saying “I’m leaving, take the house.”

Here, the **house is like the underlying asset**, the **loan is like the strike**, and the **right to walk away** resembles a put option.

---

### 2. History of options

* Options have existed for centuries (e.g., Dutch options in the 1730s).
* But they were **not standardized**:

  * Each contract had its own conditions (date, price, etc.).
  * No organized market, no transparency.
* In **1973**, the **Chicago Board Options Exchange (CBOE)** was created.

  * For the first time, options became **standardized** (strike, maturity, contract size).
  * This created **true liquidity** and an **organized market**.

---

### 3. Derivatives in everyday finance

* Many financial products accessible to retail investors (**ETFs, structured funds**) embed **options** or other derivatives.
* Sometimes, investors **think they are buying a simple product**, but they are actually exposed to **complex derivative instruments**.

---

### 4. Risks of derivatives

* Warren Buffett called derivatives **“weapons of mass destruction.”**
* Example: **2008 subprime crisis**:

  * Banks used **swaps and CDOs** (derivatives tied to mortgage debt).
  * When counterparties were close to bankruptcy, the whole system was threatened → domino effect.
* Regulators’ response:

  * **USA (Dodd-Frank Act)**: created the Office of Financial Research to monitor systemic risks.
  * **Global (Financial Stability Board, Switzerland)**: monitoring derivative markets worldwide.

---

### 5. Social usefulness of derivatives

* A derivative is like **insurance**.

  * Example: you insure your house against fire → if it burns, you’re protected.
  * In finance: you can buy a **put** on a real estate index → protection if the market crashes.
* Insurance and options help **reduce inequality**:

  * Without insurance, a disaster (illness, fire, bankruptcy) can ruin someone.
  * With insurance/derivatives, shocks are **less catastrophic** → society becomes more stable.

---

✅ In summary:

* Options are **everywhere** (not only in stock markets).
* They provide **flexibility** (the right to exit an obligation, like walking away from a mortgage).
* They are **very old**, but modern option markets only started in 1973.
* They are **useful but dangerous** if poorly regulated.
* Properly used, they act like **insurance**, reducing risks and even inequalities.

---

Here’s a clean README-style note in English summarizing the key ideas from the Yale lecture on **Put–Call Parity**:

---

## [Put–Call Parity]

## 1. Intrinsic Value at Expiration

* **Call Option (right to buy):**
  On the last day, its value = `max(S − K, 0)`
  If stock price (S) < strike price (K), the call is worthless.
  If S > K, the value = difference between stock price and strike.

* **Put Option (right to sell):**
  On the last day, its value = `max(K − S, 0)`
  You exercise only if strike > stock price.

At expiration, options only have **intrinsic value**. Before expiration, they also include **time value**.

---

## 2. Put–Call Parity Relation

For European options with the same strike (K) and expiration (T):

$$
C + PV(K) + PV(\text{Dividends}) - P = S
$$

Where:

* **C** = Call price
* **P** = Put price
* **S** = Current stock price
* **PV(K)** = Present value of strike (discounted at risk-free rate)
* **PV(Dividends)** = Present value of dividends to be paid before expiration

This relation is enforced by **arbitrage**: if violated, traders exploit the price difference until equilibrium is restored.

---

## 3. Market Example (Intel case study)

* Strike = 27
* Call midpoint price ≈ 6.125
* Put midpoint price ≈ (value observed)
* Dividends between now and expiry ≈ 2.08
* Ignoring interest rates for simplicity, computed parity was **close** to actual stock price (\~31.63).
* Small differences explained by:

  * Not discounting for interest rates
  * Market timing mismatches (bid/ask vs last price)
  * Imperfect synchrony

---

## 4. Why Out-of-the-Money (OTM) Options Still Have Value

* Even if **S < K** (call OTM), the option is not worthless before expiry.
* Reason: there is still **time** for the stock to move above strike.
* Investors pay for this potential → that’s the **time value**.

---

## 5. No Arbitrage Principle

* Arbitrage = risk-free profit.
* Markets quickly eliminate such opportunities:

  * If put–call parity is violated, arbitrageurs exploit it instantly.
  * Example: if stock is mispriced relative to call + put + PV(K), traders create risk-free positions.
* Result: **put–call parity holds in practice**.

---

## 6. Takeaway

* **Put–Call Parity** links the prices of calls, puts, and the underlying.
* You don’t need both puts and calls — knowing one lets you deduce the other.
* Fundamental principle of option pricing, used by traders to detect mispricings and enforce market efficiency.

---

Parfait 👍 Je vais enrichir ton README **Using Options to Hedge** avec une section dédiée à **VIX vs SKEW** pour compléter l’explication. Voici la version mise à jour :

```markdown
# Lesson – Using Options to Hedge

## Hedging with Options vs Stop-Loss Orders

- **Put Option**  
  - Acts as insurance by setting a **floor on losses**.  
  - If stock price falls below strike, you exercise the put.  
  - Cost: upfront **premium**.  

- **Stop-Loss Order**  
  - Instruction to broker: sell if stock falls below a certain level.  
  - Appears free (only transaction costs).  
  - Risk: execution at worse prices (slippage), whipsaw trades (sell low, buy high).  

---

## Intel Case Example

- Stock price = **\$31.63**  
- Investor sets stop-loss at **\$20**  
- Scenario:  
  - Price dips to \$19 → broker sells (below target).  
  - Price rebounds to \$21 → investor may re-enter.  
  - Next day, falls again → repeated losses (sell low / buy high).  

**Contrast**: a put at strike 20 locks in insurance without repeated trading.  

---

## Why Put Protection May Be Superior

- **Stop-Loss Limitations**  
  - No guarantee of execution at chosen price.  
  - Exposes investor to whipsaws in volatile markets.  

- **Put Advantage**  
  - Certainty of payoff if strike breached.  
  - Cleaner hedge, though requires premium.  

**Decision** = trade-off between **premium cost** and **potential trading losses**.  

---

## Market Fear & the CBOE SKEW Index

- **Definition**: SKEW measures perceived tail risk using **out-of-the-money put prices**.  
- High SKEW = crash protection expensive → market is worried.  
- Historical notes:  
  - Spikes around events like 1987 crash, 1998 Russian debt crisis.  
  - Useful for **30-day risk forecasting**, not for multi-year crashes (e.g., 1929).  

---

## VIX vs SKEW: Interpreting Market Sentiment

- **VIX** = “Fear Gauge” → reflects **expected average volatility** (nervousness of daily market).  
- **SKEW** = “Tail Risk Gauge” → reflects **fear of extreme crashes** (black swans).  

### Combined Interpretation
- **VIX high + SKEW low** → market panics in short term, but no fear of a crash.  
- **VIX low + SKEW high** → market looks calm, but investors quietly fear a **big shock**.  

---

## Takeaway

- Hedging can be done with **stop-loss orders (cheap but unreliable)** or **put options (costly but certain)**.  
- Option markets provide **risk sentiment signals** through indices like VIX and SKEW.  
- **Insurance in markets is never free** → balance option premium vs. potential stop-loss inefficiencies.  
- **VIX = volatility fear / SKEW = crash fear** → together they give a fuller picture of market sentiment.  
```


```markdown
# Personal Reflections on Hedging

### Stop-Loss Inefficiency and Option Hedge
I have already experienced situations where my stop-loss was ineffective due to **slippage during major economic announcements**.  
For a long time, I thought the solution was simply **not to trade on days of high-impact releases**.  
Now I realize that to cancel this risk, the right approach is to **hedge with options on expected announcement days**.  
This way, even if the market gaps, the option acts as insurance and sets a floor to my loss.  

Sometimes my setups required a **large stop-loss**, and I used to avoid taking these trades.  
With an option hedge, I can now take them and reduce my risk — it is as if I **lower the theoretical loss** I am willing to accept.  

### Hedging by Volatility
On days of expected **high volatility**, the main challenge is that we **cannot know the direction** of the market move.  
Using **straddles or strangles** can be effective in such cases:  
- They benefit if the market makes a large move in either direction.  
- They reduce exposure to “directional uncertainty”.  
- The cost is the option premium, but it buys protection against both tails.  

### Idea of a Scenario-Based Hedging Dashboard
It is not enough to test a single path when comparing Stop-Loss vs Put.  
Monte Carlo allows me to simulate thousands of possible scenarios and see the full **PnL distribution**.  
This makes the analysis more realistic, since it shows how each strategy behaves under many outcomes, not just one.  

It would also be interesting to build a **dashboard** that groups all these PnL simulations:  
- Inputs: lot sizes, chosen coverage products (puts, calls, straddles, etc.), market scenarios.  
- Output: simulated PnL distributions and risk metrics.  
Such a tool would make hedging decisions more objective and systematic.  

### Interest Rate Risk and Vega Risk
In fixed income trading, **interest rate risk** is central: when rates rise, bond prices fall.  
Options like swaptions or puts on Treasury futures can be used to hedge this exposure.  

Another important dimension is **Vega risk**: the value of an option depends on implied volatility.  
If implied volatility decreases, the time value of the option shrinks, and its price can drop even if the underlying does not move.  
This means that holding a long option is not only a bet on direction, but also a bet on volatility staying high or increasing.  
```










