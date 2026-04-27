# The Compliance Trap
### Measuring Performance, Not Outcomes

> *When the score becomes the goal, the goal stops being care.*

A quantitative capstone study analyzing whether CMS hospital quality penalty programs — HRRP, HAC, and VBP — improve genuine patient outcomes or incentivize metric management. Built on 2,833 U.S. acute care hospitals across 11 merged CMS public-use datasets.

**[View Live Site](https://ajayvarmaramineni.github.io/CMS-Compliance-Trap/)** &nbsp;·&nbsp; WPI BUS596 Capstone &nbsp;·&nbsp; Spring 2026

---

## The Problem

CMS operates three simultaneous penalty programs designed to drive hospital quality:

- **HRRP** — penalizes 30-day readmissions
- **HAC** — penalizes hospital-acquired conditions (infections, falls, pressure ulcers)
- **VBP** — rewards total performance scores

Each program was designed independently. We tested whether they work together — or against each other.

---

## Key Findings

### RQ1 — The Infection Illusion (HAC Program)
Hospitals can score well on HAI metrics while posting above-median mortality. The HAC program's detection failure is statistically non-random.

| Metric | Value |
|--------|-------|
| HAI–Mortality correlation | r = 0.015, p = 0.46 (not significant) |
| HAI variance explained in mortality | R² = 0.0002 |
| Blind-spot hospitals (low HAI, high mortality) | **550** |
| HAC detection rate of blind-spot hospitals | 9.8% |
| Detection failure (chi-square test) | χ² = 62.75, p < 0.001 |

> Hospitals can be penalized and safe, or penalty-free and dangerous. The metric doesn't distinguish.

---

### RQ2 — Readmission Displacement (HRRP Program)
HRRP-penalized hospitals show a persistent EDAC (Excess Days in Acute Care) gap for heart failure patients — even after controlling for hospital quality. Attenuation analysis identifies this as behavioral response, not selection bias.

| Metric | Value |
|--------|-------|
| EDAC gap (heart failure) | **+17.9 days** per penalized hospital |
| M1→M3 attenuation | 22.5% — behavioral signal, not selection artifact |
| SNF discharge share (non-penalized) | 39.0% vs. 38.0% |
| Statistical significance | p < 0.001 |

> Hospitals aren't reducing readmissions. They're routing patients differently.

---

### RQ3 — Multi-Program Convergence
47.4% of U.S. acute care hospitals face 2+ simultaneous CMS penalty programs. The compounding effect is measurable and consistent across all three quality dimensions.

| Metric | Value |
|--------|-------|
| Hospitals in 2+ programs | **47.4%** (1,342 hospitals) |
| Hospitals in 3 programs simultaneously | **155** |
| HCAHPS impact per additional penalty | −1.41 pts (p < 0.001) |
| CMS Star Rating impact per additional penalty | −0.48 stars (p < 0.001) |
| PSI-90 impact per additional penalty | +0.065 composite (p < 0.001) |
| Convergent hospitals in the South | **56.8%** |

> More penalties predict worse scores on every dimension — not because these hospitals are worse, but because they are operating under compounding incentive structures.

---

## Methodology

**Design:** Cross-sectional OLS regression, hospital-level unit of analysis, FY2026 CMS data

**Sample:** 2,833 U.S. acute care hospitals after exclusion criteria

**Analytical Framework:** Three-model attenuation design per research question
- **M1** — Unadjusted (baseline effect)
- **M2** — + Hospital ownership type & geographic region
- **M3** — + CMS Overall Star Rating (quality proxy)

Attenuation < 30%: behavioral signal. Attenuation > 40%: quality-selection artifact.

**Standard Errors:** HC3 heteroskedasticity-robust throughout

**Data Sources (11 CMS files merged via Provider ID):**
- HRRP Penalties & Readmission Rates
- HAC Composite & Penalty Status
- VBP Total Performance Score
- HCAHPS Patient Satisfaction
- CMS Star Ratings (Overall)
- PSI-90 Patient Safety Composite
- EDAC — Heart Failure & Pneumonia
- SNF & Home Health Spending Share
- 30-Day Mortality (4 conditions)
- HAI Composite (CLABSI, CAUTI, MRSA, C. diff)

---

## Policy Implications

**1. Co-monitor mortality alongside HAI metrics** — HAC compliance should require both low HAI scores and mortality within expected range. Meeting the infection threshold while posting above-median mortality is not quality.

**2. Make EDAC a co-primary HRRP metric** — Weight EDAC at 50% of the readmission score. This eliminates the financial incentive to discharge patients to SNFs to game the 30-day window.

**3. Cap penalties for convergent hospitals & create improvement grants** — Hospitals in 2+ programs face a penalty cap. A share of penalty revenue redirected as grants targeting the 155 convergent hospitals, 56.8% of which are in the South.

---

## Repository Structure

```
CMS-Compliance-Trap/
├── index.html              # Interactive site (self-contained)
├── assets/
│   └── poster/             # BUS596 conference poster (PDF)
├── charts/
│   ├── rq1_chart.png       # HAI vs. mortality quadrant analysis
│   ├── rq2_chart.png       # EDAC displacement visualization
│   └── rq3_chart.png       # Multi-program convergence
└── images/
    └── WPI-logo.png
```

---

## Stack

| Layer | Tool |
|-------|------|
| Analysis | Python (pandas, statsmodels, scipy, matplotlib, seaborn) |
| Regression | OLS with HC3 robust standard errors (statsmodels) |
| Visualization | matplotlib + seaborn (static), Chart.js (interactive) |
| Site | Vanilla HTML/CSS/JS — no framework, no build step |
| Data | 11 CMS Hospital Quality Reporting public-use files |

---

## About

**Course:** WPI BUS596 — Healthcare Analytics Capstone  
**Author:** Ajay Varma Ramineni  
**Institution:** Worcester Polytechnic Institute  
**Semester:** Spring 2026

This study applies Goodhart's Law to healthcare measurement: *when a measure becomes a target, it ceases to be a good measure.* The three-model attenuation framework used here is designed to distinguish genuine behavioral response from quality-selection artifact — a distinction that matters for whether policy reform should target incentive design or hospital selection.
