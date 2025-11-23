# Basel Point — Paper 3: Supervised Logistic Model with Macro Variables

This repository provides the **public companion materials** for **Basel Point — Paper 3**:

> **“Why the Yield Curve Lost Its Signal and How to Recover It”**  
> Substack: https://thebaselpoint.substack.com/p/why-the-yield-curve-lost-its-signal

It includes a **redacted preview notebook** and **static figures** that illustrate the main model outputs.  
The full implementation (data pipeline, complete notebook, and internal diagnostics) is maintained in a **separate private repository**.

Supervised Logistic Model with Macro Variables for Recession Probability
---

## Repository Contents

- `notebooks/paper3_macro_supervise_redacted.ipynb`  
  Redacted preview notebook showing:
  - high-level feature set (yield spreads + macro indicators)  
  - model framing (12-month-ahead recession probability via logistic regression)  
  - selected charts and summary outputs  

  Certain code blocks, data-loading logic, and feature-engineering details have been intentionally removed.

- `figures/`  
  Static PNGs used in the Substack article, for quick reference and citation.  
  Typical contents include:
  - `recession_probabilities_macro_supervised.png` — modeled recession probability series with NBER shading  
  - `macro_conditioned_feature_contributions.png` — illustrative macro-supervised signal view  

---

## Method (High-Level Overview)

The analysis combines:

- **Yield curve inputs**  
  - 10Y–3M and 10Y–2Y Treasury spreads

- **Macro indicators** (examples)  
  - Business cycle/ISM-type indicators  
  - Labor market measures (claims, unemployment dynamics)  
  - Credit and stress proxies  
  - Risk sentiment indices  

- **Target**  
  - NBER recession indicator shifted 12 months ahead  
  - Output: recession probability over a 12-month horizon

The model is trained and evaluated with an **expanding-window (walk-forward) setup**, producing:

- recession probability curves  
- regime-conditioned insights  
- standard classification diagnostics (ROC/AUC, calibration, etc.)

This repo focuses on **illustrative artifacts**, not full reproducibility.

---

## What Is *Not* Included Here

To preserve IP and avoid casual cloning, this repository **does not include**:

- raw or processed data files  
- full feature-engineering code  
- full training + evaluation pipelines  
- environment and infrastructure details  

Those elements exist in a **private working repo** and are available only for **professional review under appropriate conditions**.

---

## Access & Contact

For collaboration, technical review, or discussion of the full modeling pipeline:

- **Email:** thebaselpoint@gmail.com  
- **Substack:** https://thebaselpoint.substack.com  

© 2025 The Basel Point Research. All rights reserved.  
Prepared by S.Y. Kim.
