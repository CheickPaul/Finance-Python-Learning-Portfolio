Disclaimer These notes are my personal learning summaries based on the Python primer module I followed, supplemented by additional personal research and practice. To avoid sharing proprietary course material from QuantInsti, all examples, datasets, and diagrams have been independently created or sourced elsewhere. The definitions and explanations below reflect my understanding at the time of writing and should not be taken as gospel. Please do your own research and verification. I reserve the right to revise and update this document as my learning progresses and to correct any errors I discover.

Purpose: The notes belows are include in my repository " Finance-Python-Learning-Portfolio". The purpose is to document my learning journey and centralizes my personal notes for future revision. It is non-commercial and respects QuantInsti’s IP; the aim is transparency in learning, not redistribution of course materials.
 
 # TABLE OF CONTENTS


### SECTION 1 - Intro :
 how python is used in trading desk 
### SECTION 2 - Variables & Packages :
Store data in variables and usebasic libraries (math, spicy) for numeral work
### SECTION 3 - Time Value of Money :
 compute present value and future value of cash flows in Python
### SECTION 4 - Data Structure :
Use lists, tuples and dictionaries to organise market data
### SECTION 5 - Market Data and Charts :
Import price series and plot line charts and candlestick charts
### SECTION 6 - Functions : 
write function to automate repetitive trading calculations
### SECTION 7 - NumPy :
Use NumPy arrays for fast vectorised calculations ( returns, volatility,etc)
### SECTION 8  - Pandas :
Use DataFrames to manipulate time series ( resample, join, rolling stats)
### SECTION 9 - Controls and condition : 
Use if, for, while to code simple trading rules and signal
### Section 10 - Environment Setup :
Install Python locally and run codes for trading experiments

---

## Section 1. <ins>Intro</ins>


**Key ideas:**
- **Algorithmic trading** is about codifying a trader’s behaviour into a set of rules that can be executed automatically on the exchange (order execution logic).
- **Quant trading** is about trading strategies built on **statistics and modelling** (math-backed trading models).
- **Algo trading a subset of quant trading**; **automated trading** is when the algo places orders on behalf of the human without manual clicks.
- A typical day on an algo desk mixes **operations (reports)**, **research to improve live strategies**, and **development of new strategies**.
- **Why Python?**  
  -(1) We use it because is a rich ecosystem of **libraries** for data, stats, ML and infrastructure (we do not need to reinvent the wheel).  
  -(2) The new Machine Learning packages are released in Python first, then ported to R/others.  
  -(3) Python code is **production-ready**: you can deploy it, unlike Excel sheets.  
  -(4) There is a huge **community support** → any error or question, someone has already faced it.
  -(5) Compared to older tools (C, MATLAB, R, etc.), Python is easier to learn, faster to prototype with, and better suited to **data science / quant trading**.
-(6)To start, we learn the basics (syntax, variables, if-conditions, loops, functions) and apply them to **small trading projects.

---

## Section 2. <ins>Variables, object references and operator</ins>

 **Variable** is a **name** that points to a value stored in memory
 exemple : price = 105.5. In python, price is a variable pointing to 105.5

  **Object** could be everything : number, strings, list, function etc. An object has a **type** (int for "integer", float for " floating point number or decimal number", str for "string or sequence characters" and list "for exemple list of float, list of int, list of str"),a **value**, and a **location in memory**
  example : 
 ```python
  price = 105.50   # 105.50 is a float object in memory
  symbol = "AAPL"  # "AAPL" is a string object in memory
```

**Object reference**: A variable does not store the value directly, it store a **reference** to an an object in memory. 

Example:
  ```python
  prices = [100, 101, 102]  # list object in memory
  ref = prices              # 'ref' is another reference to the *same* object
  ref.append(103)
  print(prices)             # [100, 101, 102, 103]

Both prices and ref point to the same list object, so modifying one also changes the other.
```
