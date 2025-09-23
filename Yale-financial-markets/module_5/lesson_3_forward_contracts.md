# [Forward Contracts]

## Definition
A forward contract is a private agreement between two parties (counterparties) to deliver an asset at a future date (maturity/exercise date) at a pre-agreed price.  
Historically, forwards preceded the development of futures markets.

---

## Origins
**Example: Dojima rice market (Japan, 1670s)**  
Farmers could either:  
- Wait until harvest and sell at the spot price (uncertain).  
- Or lock in a forward price with a warehouse, reducing uncertainty.  

➡ Farmers prefer forwards to reduce price risk after incurring high production costs.

---

## Hedgers vs. Speculators
- **Farmers**: usually avoid futures markets (too complex) but lock in forward prices.  
- **Warehouses / grain elevators**: act as hedgers, since storage is a low-margin business.  
  → They often hedge their own positions in futures markets.

---

## Characteristics of Forward Contracts
- **Flexible**: customized contracts (quantity, quality, delivery date, location).  
- **Illiquid**: cannot easily exit before maturity.  
- **Counterparty risk**: dependent on the creditworthiness of the other party (e.g., farmer may default).  
- **Limited scalability**: must evaluate and trust each counterparty.  

---

## Futures vs. Forwards
- **Forwards**: bilateral, customized, with counterparty risk.  
- **Futures**: standardized, exchange-traded, margin system removes counterparty risk (exchange is the counterparty).  
- **Liquidity**: futures markets are much more liquid (can enter and exit positions freely).  

---

## FX Forwards and Arbitrage
**Example: Japanese exporter selling in the US.**  

Instead of using an FX forward, they can:  
1. Borrow in USD.  
2. Convert USD at spot into JPY.  
3. Invest in Japan at JPY interest rate.  

At maturity, the no-arbitrage forward price must satisfy:  

$$
F = S \times \frac{(1 + r_{¥})}{(1 + r_{\$})}
$$

Where:  
- \( F \) = forward exchange rate  
- \( S \) = spot exchange rate  
- \( r_{¥} \) = Japanese interest rate  
- \( r_{\$} \) = US interest rate  

➡ This is called **Covered Interest Parity (CIP).**

---

## Forward Rate Agreements (FRAs)
Settlement formula (simplified):  

$$
\text{Payoff} = (R_{mkt} - R_{contract}) \times \frac{\text{days}}{B} \times \text{Notional}
$$  

Where:  
- \( R_{mkt} \) = realized market interest rate  
- \( R_{contract} \) = agreed forward rate  
- \( B \) = day-count convention (360 or 365)  

---

## Differences between **Forwards** and **Futures**

| Characteristic        | Forward Contract (OTC)                     | Futures Contract (Exchange)                 |
|-----------------------|---------------------------------------------|---------------------------------------------|
| **Nature of contract** | Private agreement (OTC – Over The Counter) | Standardized contract, traded on exchange   |
| **Customization**      | Flexible: amount, quality, date, location  | Standardized: contract sizes, maturities    |
| **Counterparty risk**  | Present: depends on partner’s solvency     | Reduced: clearinghouse acts as counterparty |
| **Liquidity**          | Low, difficult to exit before maturity     | High, easy to open/close positions          |
| **Settlement**         | At maturity (physical or cash settlement)  | Daily (mark-to-market, margin adjustments)  |
| **Typical users**      | Corporates, banks, specific needs          | Traders, investors, institutional hedgers   |
| **Usage example**      | Exporter fixing a custom FX rate           | Trader hedging oil, wheat, or interest rates|

