# Lesson 13 – Limit Order Book (LOB)

## Key Concepts
- **Historical Context**:  
  - Example: Island ECN (Electronic Communications Network), ~20 years ago.  
  - SEC allowed ECNs as a separate category to encourage innovation.  
  - Unique feature: any investor (not only dealers) could place visible orders in the book.  

- **Book Structure**:  
  - **Bid** = buy order (price you want to pay).  
  - **Ask** = sell order (price you want to sell at).  
  - Orders sorted automatically from best to worst price.  
  - Example:  
    - Buy 100 shares at $35.62.  
    - Sell 500 shares at $35.63.  
  - Mostly small orders → “amateur” market, but some dealers participated.  

- **Execution Mechanics**:  
  - For immediate execution → place order at the top of the book.  
  - Orders further down wait until larger trades clear them.  
  - Orders constantly appear/disappear within seconds (dynamic flow).  

- **Transition to NASDAQ**:  
  - NASDAQ adopted the same principle.  
  - Different market depth levels available, subscription costly → designed for professionals.  
  - Larger order sizes and dealer names (e.g., arcx) displayed.  

- **Key Concept**:  
  - **Inside spread** = best bid – best ask.  
  - Spread can vanish in fractions of a second, showing intense competition.  
  - Highlights **market microstructure**:  
    - Transparency via order book.  
    - Importance of queue position in execution.  
    - Speed and intensity of electronic trading.  

## My Notes
- The order book reflects real-time interaction of supply (asks) and demand (bids).  
- Depth of book determines liquidity and resilience to large trades.  
- Order flow activity (orders appearing/disappearing) provides signals about momentum and pressure.  
- Execution strategy (e.g., limit orders near inside market) helps minimize slippage.  

## Illustration
Example of **NASDAQ Level II – MSFT** (Order Book Snapshot):

<img width="617" height="378" alt="Capture d’écran 2025-09-18 à 22 21 04" src="https://github.com/user-attachments/assets/10b19ac5-727a-4e0f-8a73-3a9fb5cadd04" />


The figure shows bid (left) and ask (right) sides, with order quantities and prices.  
- Best bid = 26.23 (arcx, 100 shares).  
- Best ask = 26.23 (NSDQ, 2667 shares).  
- Spread = 0.00 → highly liquid.  
- Market depth = number of shares available at multiple levels beyond the inside market.  

## Reflection
Limit Order Book (LOB)  
The order book is the electronic list of buy (bids) and sell (asks) orders for a financial asset, ranked by price and quantity.  

- **Bid** → price buyers are willing to pay.  
- **Ask** → price sellers are willing to accept.  
- The book reflects the real-time interaction of supply and demand.  

### Structure of the Book  
Example (NASDAQ Level II – MSFT):  

**Bid side (buyers):**  
- arcx: 100 shares @ 26.23  
- NSDQ: 9192 shares @ 26.22  
- cinn: 6600 shares @ 26.22  
➝ Total available at 26.22 = 15,792 shares  

**Ask side (sellers):**  
- NSDQ: 2667 shares @ 26.23  
- cinn: 8400 shares @ 26.24  
- arcx: 4200 shares @ 26.24  

### Inside Market and Spread  
- Inside bid = best buy price (26.23).  
- Inside ask = best sell price (26.23).  
- Spread = difference between bid and ask → can be zero in liquid markets.  

### Market Depth  
- Depth = volume available beyond the inside market.  
- Deep market = large orders stacked at several levels → high liquidity.  
- Shallow market = few orders → volatile, sharp moves possible.  

### Uses of Market Depth  
- Measure liquidity.  
- Detect buy/sell pressure (order “walls”).  
- Anticipate volatility.  
- Manage slippage from large orders.  

### Trading Applications  
- Scalping/intraday: enter/exit quickly at inside prices.  
- Support/resistance: spot large order clusters.  
- Timing: track order flow speed.  
- Risk: avoid oversized orders in shallow books.  

**In summary**:  
The order book is a **real-time snapshot of supply and demand**. It helps traders assess liquidity, identify pressure zones, and optimize execution to reduce slippage.  
