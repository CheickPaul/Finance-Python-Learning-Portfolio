# [High Frequency Trading (HFT)]

## Key Points

* **Automation & speed**: algorithms execute trades in milliseconds or microseconds.
* **Colocation**: servers placed next to exchanges to minimize latency.
* **Ephemeral orders**: quotes that appear and disappear in the blink of an eye, invisible to humans.

---

## Advantages

* **Increased liquidity**: more quotes in the order book, tighter spreads.
* **Micro-time efficiency**: prices adjust instantly to new information (but only visible to machines).

---

## Disadvantages

* **Hidden cost**: billions of dollars per year are “siphoned” away from traditional investors by HFT firms.
* **Limited social utility**: a costly technological arms race with little benefit to the real economy.
* **Higher volatility**: can amplify market stress (e.g., Flash Crash 2010).

---

## Proposed Regulation

* **Batch Auctions**:

  * Aggregate orders and execute them every 1 to 10 seconds.
  * Turns the market into frequent mini-auctions.
  * Eliminates the millisecond advantage, making ultra-fast connections pointless.

---

## (Reflection)

* HFT makes the market “efficient at the millisecond level,” but this efficiency has **no real value** for most investors.
* The **hidden cost** is the most problematic aspect: HFT captures a slice of value from nearly every order. Repeated at scale, this represents **billions siphoned** from traditional portfolios each year.
* The link with **market makers** is central: HFT has largely replaced traditional market makers by becoming **electronic liquidity providers** (e.g., Citadel Securities, Virtu).

  * **Positive side**: tighter spreads, abundant liquidity.
  * **Negative side**: liquidity can be **phantom-like**, as quotes vanish within milliseconds, making execution harder for large institutional trades.
* Importantly, **not all market making is HFT**. In **fixed income markets**, two realities coexist:

  * **Government bonds (Treasuries, Bunds, Gilts, etc.)** → highly liquid, HFT-style quoting dominates.
  * **Corporate and municipal bonds, exotic credit derivatives** → liquidity is provided by banks and dealers through **RFQ systems** (MarketAxess, Tradeweb) or bilateral quotes. Here, **latency matters less**; the challenge is inventory risk and pricing models, not microseconds.
* In short:

  * HFT is the **modern face of market making** in liquid equities, futures, and government bonds.
  * In less liquid segments like corporates, munis, and exotics, **non-HFT market making** still plays a critical role, relying more on client relationships, credit analysis, and inventory management than on speed.
* Solutions like **batch auctions** directly target the imbalance in liquid markets by neutralizing the millisecond speed race, but they don’t erase the fundamental need for slower, relationship-driven market makers in fixed income.

