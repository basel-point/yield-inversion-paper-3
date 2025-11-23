# Basel Point — Paper 3: Supervised Logistic Model with Macro Variables

This repository provides the public companion materials for **Basel Point — Paper 3**:

**“Why the Yield Curve Lost Its Signal — And How to Recover It”**  
Substack: https://thebaselpoint.substack.com/p/why-the-yield-curve-lost-its-signal

It includes a **redacted preview notebook** and **static figures** illustrating the model’s key outputs.  
The full modeling pipeline (data engineering, full notebook, internal diagnostics) is maintained in a **private research repository**.

---

## Repository Contents

### ** Redacted Notebook**
**[paper3_macro_supervise_redacted.ipynb](notebooks/paper3_macro_supervise_redacted.ipynb)**  
A preview notebook showing:

- feature set overview (yield spreads + macro indicators)  
- model structure (12-month-ahead recession probability using logistic regression)  
- selected figures  
- explanatory commentary  

All sensitive components (data loading, feature engineering code, validation loops, and scenario procedures) have been intentionally removed.

---

### ** Figures**
Static PNGs used in the Substack article:

- **[ROC_curves_macro_extended_models.png](figures/ROC_curves_macro_extended_models.png)**  
- **[scenario-based_conditional_recession_probabilities.png](figures/scenario-based_conditional_recession_probabilities.png)**  

These illustrate the predictive lift from macro-supervised models and the recession probability bands under different macro-economic scenarios.

---

## Method (High-Level Overview)

This paper extends yield-curve recession modeling by incorporating **macro-supervised features**, including:

- **Yield curve signals**  
  - 10Y–3M spread  
  - 10Y–2Y spread  

- **Macro indicators**  
  - ISM-style business cycle measures  
  - Labor market dynamics (initial claims, unemployment deltas)  
  - Credit spreads (BBB, TED)  
  - Stress & volatility proxies (e.g., MOVE, VIX)

- **Target variable**  
  - NBER recession indicator, shifted 12 months ahead  
  - Output: probability of recession one year into the future  

Model training uses a **walk-forward expanding window** to mimic real-time forecasting.

---

## Scenario-Based Probability Bands (Explained)

The probability bands shown in:

- **scenario-based_conditional_recession_probabilities.png**

represent **conditional recession probabilities under different macro-economic paths**, not Monte Carlo simulation.

Specifically:

1. **Yield curve variables are held at their historical/observed values.**
2. **Macro inputs are set to different “scenarios”**—
   - *Soft landing path* (strong labor market + improving credit spreads)  
   - *Baseline path*  
   - *Downside path* (weaker ISM, rising claims, widening credit spreads)

3. The logistic model is re-evaluated under each scenario to generate:
   - upper/lower probability bands  
   - scenario-conditional trajectories  
   - insights into when the yield curve signal strengthens or weakens  

This allows the model to answer:
> “What is the recession probability if macro conditions stay strong?  
> What if they deteriorate?  
> How wide is the uncertainty band?”

It is **scenario conditioning**, not Monte Carlo.

---

## What Is *Not* Included Here

To protect intellectual property and avoid trivial duplication, the following are **omitted**:

- raw or processed data  
- feature engineering code  
- full model-training pipelines  
- expanding-window validation logic  
- configuration files  
- model artifacts  

The full implementation is stored in a **private repo** and available only for professional review.

---

## Access & Contact

For collaboration, code review, or discussion of the full modeling framework:

**Email:** thebaselpoint@gmail.com  
**Substack:** https://thebaselpoint.substack.com  

© 2025 The Basel Point Research. All rights reserved.  
Prepared by S.Y. Kim.
