# B2B FinTech Unit Economics & Revenue Retention Analytics

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange)
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Visualization-teal)
![License](https://img.shields.io/badge/License-MIT-green)

An end-to-end commercial analytics framework built to diagnose customer unit economics, expansion velocity, involuntary churn leakage, and cohort decay across 1,000 enterprise accounts in a B2B FinTech / SaaS environment.

---

## Executive Summary

In high-growth FinTech platforms, top-line monthly recurring revenue (MRR) often conceals balance-sheet decay. This project diagnoses customer lifetime value, capital efficiency, operational payment failures, and account retention using an assumed **78% Gross Margin** baseline.

Rather than treating churn as a simple aggregate percentage, this framework deconstructs revenue attrition into actionable business drivers: contract lock-in periods, Net Promoter Score (NPS) sentiment thresholds, payment infrastructure friction, and customer acquisition channel ROI.

---

## Key Business Objectives & Achievements

* **Unit Economic Auditing:** Calculates CAC payback duration and LTV:CAC multiples across SMB, Mid-Market, and Enterprise tiers to identify capital-dilutive acquisition segments.
* **Negative Churn Quantification:** Evaluates Net Revenue Retention (NRR) benchmarks across segments to isolate ARR expansion engines from leaky-bucket tiers.
* **Involuntary Churn Isolation:** Measures revenue loss driven by recurring payment failures (expired corporate cards, bank API rejections) versus deliberate cancellations.
* **Capital Allocation Optimization:** Analyzes Customer Acquisition Cost (CAC) efficiency across Outbound, Paid Ads, Inbound, and Partner channels to guide marketing budget reallocations.
* **Revenue Concentration Diagnostics:** Maps Pareto revenue concentration (Lorenz Curve) to quantify key-account margin risk and contract vulnerability.

---

## Analytical Architecture & 10 Core Frameworks

| # | Analytical Framework | Statistical / Visual Technique | Strategic Business Objective |
|---|----------------------|--------------------------------|------------------------------|
| **1** | **Unit Economics & CAC Payback** | Grouped Bar Chart | Isolates SMB capital inefficiency vs. high-performing Enterprise LTV:CAC ratios (>5.5x). |
| **2** | **Net Revenue Retention (NRR)** | Diverging Bar Chart (100% baseline) | Identifies expansion velocity across segments; pinpoints SMB underperformance (<85% NRR). |
| **3** | **Channel Capital Efficiency** | Multi-Variable Bubble Plot | Benchmarks acquisition ROI across Paid Ads, Outbound, Organic, and Partner Referrals. |
| **4** | **Macro Cohort Retention Matrix** | Chronological Decay Curve | Tracks account longevity and identifies the front-loaded month 3–9 onboarding drop-off cliff. |
| **5** | **Contract Durability Analysis** | Lollipop / Stem Plot | Contrasts 3x churn exposure in monthly flexible terms against multi-year enterprise lock-ins. |
| **6** | **NPS Sentiment Inflection** | Segmented Stacked Bar | Directly connects Detractor scores (NPS 0–6) to >65% of total lost recurring revenue. |
| **7** | **Involuntary Payment Friction** | Split Violin Distribution | Measures ARR loss from failed billing retries, proving friction causes passive account leakage. |
| **8** | **Pareto Revenue Concentration** | Lorenz Cumulative Curve | Diagnoses enterprise vulnerability by calculating top-decile account revenue contribution (~40%). |
| **9** | **Industry Vertical Matrix** | Normalized Heatmap | Prioritizes Ideal Customer Profiles (ICPs) by comparing FinTech, Logistics, and EdTech margins. |
| **10** | **Executive ARR Leakage Summary** | Donut Chart with KPI Ring | Quantifies platform ARR lost to churn against potential enterprise valuation multiples. |

---

## Dataset Schema

The synthetic dataset (`fintech_b2b_unit_economics.csv`) contains 1,000 accounts with zero missing or null values, modeled using realistic behavioral distributions:

* `account_id`: Unique enterprise identifier (`ACC-10000` to `ACC-10999`)
* `segment`: Business scale classification (`SMB`, `Mid-Market`, `Enterprise`)
* `industry`: Market vertical (`Fintech`, `E-Commerce`, `HealthTech`, `EdTech`, `Logistics`)
* `channel`: Acquisition source (`Outbound Sales`, `Paid Ads`, `Organic/Inbound`, `Partner Referral`)
* `cohort`: Acquisition vintage quarter (`2022-Q1` through `2024-Q2`)
* `tenure_months`: Active platform lifetime (3 to 48 months)
* `contract_type`: Billing commitment structure (`Monthly`, `Annual`, `Multi-Year`)
* `cac`: Customer Acquisition Cost in USD
* `initial_mrr`: Starting Monthly Recurring Revenue in USD
* `current_mrr`: Active Monthly Recurring Revenue (reflects account-level expansion/contraction)
* `failed_payment_events`: Historical count of billing retry/failure incidents
* `nps_score`: Net Promoter Score rating (0 to 10)
* `is_churned`: Binary account retention status (`0` = Retained, `1` = Churned)

---

## Key Executive Takeaways & Recommendations

1. **Re-Architect the SMB Acquisition Funnel:** High-touch sales motions on SMBs generate an unsustainable 18+ month payback period. Transition SMBs into a self-serve, automated Product-Led Growth (PLG) pipeline to bring CAC below $800.
2. **Automate Dunning & Card Account Updaters:** Accounts with ≥2 payment failure events show churn rates exceeding 40%. Deploy automated card updaters (Visa VAU / Mastercard ABU) and smart retry timing around corporate payroll cycles to recover passive revenue.
3. **Reallocate Paid Marketing to Partner Channels:** Paid digital advertising demonstrates the highest CAC and shortest account lifespans. Shifting 30% of paid ad budget into integration partnerships with ERP and accounting software providers yields higher-retention customers.
4. **Enforce Onboarding Milestones:** Because cohort decay is concentrated in months 3 through 9, establish an SLA-driven 60-day Time-to-First-Value (TTFV) target for solutions engineering to secure long-term platform integration.

---

## Repository Structure

```text
├── data/
│   └── fintech_b2b_unit_economics.csv      # Generated 1,000-account clean dataset
├── scripts/
│   ├── generate_data.py                    # Script to build synthetic dataset
│   └── run_analytics.py                    # Complete analytics suite and visualizations
├── notebooks/
│   └── b2b_fintech_revenue_analysis.ipynb  # Interactive walkthrough of all 10 analyses
├── docs/
│   └── executive_brief.md                  # Comprehensive business findings and inferences
└── README.md                               # Project documentation