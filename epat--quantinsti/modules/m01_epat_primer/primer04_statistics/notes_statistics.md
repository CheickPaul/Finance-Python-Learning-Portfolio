TABLE OF CONTENTS

1 An Introduction to Probability & Statistics
2 Descriptive Statistics I: Visualizing the Data
3 Descriptive Statistics II: Summarizing the Data
4 Basics of Probability Theory
5 Probability Distributions of Random Variables
6 Standard Statistical Distributions
7 Basics of Inferential Statistics
8 Hypothesis Testing
9 Covariance & Correlation
10 Linear Regression
11 Other Resources & Reference Material
Appendix 1
Appendix 2

---

####  An Introduction to Probability & Statistics


we encounter data everywhere in our society. Org takes decision based on data. (better judgment under uncertainty)


**<ins>What is Statistics?</ins>**

Science which deals with collection, organisation, analysing, interpretion and presentation of data to support decision making. It helps decision makers in making informed decision 

could be split in 2 main field **Descriptif stat (summarizing and visualisation of data)** and **Inferential statistics (draw conclusion about a population from a sample)**


**<ins>Probability vs. Statistics (clear contrast)</ins>**

Also study together it remains a difference between both of them.

***Probability*** :Start with a model → ask “**what is the chance this event happens?**” 
Concerned with calculating the likelihood of an event to occuring ang it. "
Ex: “What is the probability daily return < −2% if returns are normal?”
Generally calculated before the even takes place.


***Statistic*** : start with data → ask “**what does the data say about the model/parameters?”**
Comes into play once the event has taken place.
Ex: “Using 3 years of returns, what is the volatility (σ) and its confidence interval?”


| **Topic**     | **Before/After**         | **Typical Question**                     | **Example (markets)**                         |
|---------------|---------------------------|-------------------------------------------|-----------------------------------------------|
| Probability   | Before seeing outcome     | How likely is event **E**?                | Chance of **stop-loss** being hit tomorrow    |
| Statistics    | After observing data      | What are the parameters? Is **alpha** real? | Estimated **Sharpe**, test if **alpha ≠ 0** |



**<ins>4.practical application of statistic</ins>**

we see stat accross many field such as medicine( predict the presence of a disease in a patient) ; **economy ( analyze relationship between economic measures such as GDP and unemployement rate)** ; business (to study past trends of customer behaviour; A/B test) ; insurance ( to calculate the risk presented by the insured client or property- insurance premium is directly proportional to the risk posed by the insured) ; 

**Finance (sell-side & buy-side)** : to evaluate risks and returns for stocks ; portfolio optimisation, risk management, credit modeling, trading strategy formulation.

- **Risk management:** estimate VaR (Value at Risk) and ES (Expected Shortfall).

- **Portfolio:** optimize mean–variance; estimate beta (market sensitivity).

- **Credit:** model PD/LGD/EAD (probability of default, loss given default, exposure).

- **Trading:** build & test signals; measure alpha (excess return) vs noise.



**<ins>Statistics in Quant Finance & Algorithmic Trading (desk-friendly)</ins>**

- **Signal discovery:** is a pattern real or just **noise**? (use p-values, out-of-sample tests).

- **Parameter estimation:** mean return, **volatility, autocorrelation, cross-correlation** (lead/lag).

- **Backtesting:** **in-sample** fit vs **out-of-sample** performance; avoid **overfitting**.

- **Execution:** estimate **slippage** (execution shortfall), **market impact, fill probability.**

- **Risk:** scenario & **stress tests** (2008, 2020), regime shifts.

- **Monitoring:** production **drift** (live stats ≠ backtest stats), breaks in correlation.

**<ins>Trader vocab (with short hints)</ins>**

**Alpha** (excess return), **beta** (market sensitivity), **vol** (volatility), **drawdown** (peak-to-trough loss), **Sharpe** (return per unit risk), **VaR/ES** (tail risk), **slippage** (execution shortfall), **fill rate** (execution probability).


**<ins>Common Pitfalls (to avoid early)</ins>**

Look-ahead bias (using future info), survivorship bias (dropping failed firms), data-snooping/p-hacking (testing too many ideas), non-stationarity (market regimes change), overfitting (model glued to past).

**<ins>Mini Example (simple & concrete)</ins>**

You have 1,000 daily returns for Stock X.

Descriptive: plot histogram; compute mean, vol, skew, kurtosis.

Inferential: 95% CI for mean return; test H₀: mean = 0 (is there alpha?).

Decision: if alpha is statistically significant and economically meaningful (after costs/slippage), proceed to paper-trade.


**<ins>Tiny Glossary (one-liners)</ins>**

Population: the full set you care about (all possible returns).

Sample: the data you actually have (historical window).

Estimator: formula to estimate a parameter (e.g., sample mean).

Bias/Variance: accuracy vs stability of an estimator.

Confidence Interval (CI): plausible range for a parameter.

p-value: probability of seeing your result (or more extreme) if the null hypothesis were true.

---

#### Descriptive Statistics I: Visualizing the Data

---

#### Descriptive Statistics II: Summarizing the Data


---


#### Basics of Probability Theory

---

#### Probability Distributions of Random Variables

---

#### 6 Standard Statistical Distributions

---

#### 7 Basics of Inferential Statistics
---
#### 8 Hypothesis Testing
---
#### 9 Covariance & Correlation

#### 10 Linear Regression
---
#### 11 Other Resources & Reference Material




