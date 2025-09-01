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




