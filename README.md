# Healthcare Data Analytics & AI-Assisted Business Intelligence Dashboard

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458.svg?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.24%2B-013243.svg?logo=numpy&logoColor=white)](https://numpy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7%2B-11557c.svg)](https://matplotlib.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.0-38B2AC.svg?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)
[![Chart.js](https://img.shields.io/badge/Chart.js-4.0-FF6384.svg?logo=chartdotjs&logoColor=white)](https://www.chartjs.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

An enterprise-grade healthcare analytics project combining rigorous **Python exploratory data analysis** with an **interactive, AI-assisted Business Intelligence dashboard** designed for hospital executives, clinical directors, and revenue cycle managers.

---

## 🔗 Live Interactive Dashboard

Access the client-side executive BI dashboard deployed directly via GitHub Pages:

👉 **[View Interactive Dashboard]((https://github.com/ansh-yadav-1/HealthcareCaseStudy))**


---

## 📊 Dashboard Preview

![Healthcare Executive Dashboard Preview](screenshots/dashboard-preview.png)

---

## 📋 Executive Overview & Business Problem

Hospital administrators, chief medical officers, and financial planners operate in high-stakes environments balancing clinical outcomes, bed availability, emergency preparedness, and revenue predictability. Without granular analytical visibility into encounter-level records, healthcare organizations face:
- Operational bottlenecks in patient turnover and bed availability.
- Payer concentration risks and unexpected financial leakage.
- Inefficient emergency department triage during acute volume surges.
- Data integrity anomalies in electronic health record (EHR) billing ledgers.

This project delivers an end-to-end analytical workflow: starting from data quality auditing, exploratory analysis, and hypothesis validation in Python (`pandas`, `numpy`, `matplotlib`, `seaborn`), culminating in a responsive, standalone executive BI dashboard with real-time multi-dimensional cohort slicing and data export capabilities.

---

## 🎯 Project Objectives

1. **Patient Demographic & Diagnostic Profiling:** Quantify encounter volume across chronic conditions (Arthritis, Asthma, Cancer, Diabetes, Hypertension, Obesity) and evaluate age dispersion.
2. **Bed Capacity & Inpatient Length of Stay (LOS):** Measure inpatient stay duration across admission urgencies (Elective, Urgent, Emergency) to benchmark hospital bed turnover.
3. **Billing Consistency & Payer Diversification:** Examine longitudinal billing trends over 61 months (May 2019 – May 2024), calculate age-to-billing correlation, and analyze payer market share across commercial and public insurers.
4. **Data Integrity & Financial Auditing:** Identify and investigate data anomalies—including duplicate records and negative billing amounts—without silently altering source ledgers.
5. **Emergency Department Surge Planning & Acuity Analysis:** Pinpoint historical peak emergency admission months and identify which diagnoses present highest diagnostic acuity (abnormal lab results).

---

## 🛠️ Tech Stack

| Layer | Technologies | Purpose |
| :--- | :--- | :--- |
| **Data Analytics & Statistics** | Python 3.9+, Pandas, NumPy | Data cleaning, deduplication, feature engineering, statistical correlation |
| **Exploratory Visualizations** | Matplotlib, Seaborn | Distribution plots, boxplots, correlation scatterplots, time-series analysis |
| **Interactive Computing** | Jupyter Notebook, IPykernel | Reproducible analytical documentation and computational reporting |
| **BI Executive Dashboard** | HTML5, JavaScript (ES6+), Chart.js | Responsive, standalone, zero-dependency client-side analytics interface |
| **Styling & UI Components** | Tailwind CSS (CDN), Font Awesome 6 | Power BI / Tableau-inspired clean enterprise executive layout |
| **AI-Assisted Acceleration** | Antigravity AI Assisted Workflows | Rapid prototyping of dashboard structure, multidimensional data cube modeling |

---

## 🔬 Analytical Workflow (Python)

The core analytical pipeline is maintained in [`analysis/Healthcare_Case_Study.ipynb`](analysis/Healthcare_Case_Study.ipynb), organized into 11 structured sections:

```mermaid
flowchart LR
    A["Raw Data (55,500 Encounters)"] --> B["Data Auditing & Cleaning"]
    B --> C["Deduplication (54,966 Clean)"]
    C --> D["Feature Engineering (LOS, Time)"]
    D --> E["Exploratory & Clinical Analysis"]
    D --> F["Financial & Payer Analysis"]
    D --> G["Emergency & Acuity Deep Dives"]
    E & F & G --> H["Executive BI Dashboard (dashboard/index.html)"]
```

1. **Business Problem & Objectives:** Executive framing and operational questions.
2. **Dataset Overview:** Environment setup and flexible path resolution.
3. **Data Quality & Auditing:**
   - Evaluated missing data: 0 null values across all 15 columns.
   - Identified and removed **534 exact duplicate rows** ($54,966$ unique encounters retained).
   - Standardized text casing on patient names.
   - Audited **106 negative billing records**; preserved them for auditing rather than silently dropping them.
   - Feature-engineered **Length of Stay (LOS)** (`Discharge Date - Date of Admission`).
4. **Demographic Analysis:** Evaluated patient age distribution (mean $51.5$ years, median $52$ years).
5. **Admission & Clinical Analysis:** Breakdown of 6 medical conditions and 3 admission urgency categories.
6. **Billing & Financial Performance:** Computed overall summary statistics and monthly trendlines across 61 months.
7. **Insurance Provider Analysis:** Market share distribution across 5 major payers.
8. **Length of Stay Dynamics:** Inpatient duration distribution and acute-care capacity comparisons.
9. **Statistical Relationships:** Correlation between patient age and billing charges ($r = -0.0034$).
10. **Ad-Hoc Business Deep Dives:** Emergency surges, high-cost patient groups (>95th percentile), and abnormal diagnostic test presentations.
11. **Strategic Recommendations:** Actionable operational and financial guidance for health system leadership.

---

## 📈 Key Empirical Findings

All reported numbers are strictly calculated from the underlying dataset:

* **Cleaned Encounter Volume:** **54,966 encounters** analyzed following the elimination of 534 exact duplicate rows from 55,500 raw entries.
* **Financial Anomaly Identified:** Exactly **106 encounters** exhibit negative billing values ranging from **-$23.87** to **-$2,008.49** (mean: **-$502.47**). These records are deliberately preserved as financial audit flags rather than arbitrarily deleted.
* **Average Billing Stability:** Overall encounter billing averages **$25,544.31** (standard deviation: **$14,208.41**; median: **$25,542.75**; range: -$2,008.49 to $52,764.28). Monthly averages across all 61 months fluctuate tightly between $24,800 and $26,300 with no seasonal degradation.
* **Age vs. Billing Independence:** Pearson correlation between patient age and billing amount is **$r = -0.0034$** (statistically zero), proving age does not drive higher billing amounts in this encounter model.
* **Balanced Clinical Spread:** Diagnoses are distributed evenly across the 6 tracked conditions:
  - Arthritis: 9,218 (16.8%)
  - Diabetes: 9,216 (16.8%)
  - Hypertension: 9,151 (16.6%)
  - Obesity: 9,146 (16.6%)
  - Cancer: 9,140 (16.6%)
  - Asthma: 9,095 (16.5%)
* **Payer Market Share Diversification:** Encounters are split across 5 major insurance carriers: Cigna (20.3%), Medicare (20.1%), UnitedHealthcare (20.0%), Blue Cross (19.9%), and Aetna (19.7%).
* **Elevated Length of Stay (ALOS):** Average inpatient stay is **15.50 days** (range: 1 to 30 days) uniformly across Elective, Urgent, and Emergency admissions, indicating a major bed turnover bottleneck compared to typical acute-care norms (4.5–5.5 days).
* **Emergency Department Peak Surge:** Monthly emergency volume peaked in **July 2020** with **355 admissions** (compared to a monthly average of ~297).
* **High-Cost Encounter Exposure:** The 95th percentile billing threshold is **$47,638.27**. The top 5% cohort comprises **2,749 encounters** accounting for over **$137 Million** in cumulative charges.
* **Diagnostic Acuity in Emergency Department:** Exactly **33.36%** of all emergency encounters (6,038 out of 18,102) present with **Abnormal** lab/test results, led clinically by **Obesity (1,058 cases)** and **Cancer (1,057 cases)**.

---

## 🖥️ Executive BI Dashboard Features

The dashboard at [`dashboard/index.html`](dashboard/index.html) is built as a self-contained, client-side business intelligence interface:

* **Interactive Multi-Dimensional Filters:**
  - **Medical Condition:** All, Arthritis, Asthma, Cancer, Diabetes, Hypertension, Obesity.
  - **Admission Type:** All, Elective, Emergency, Urgent.
  - **Insurance Provider:** All, Aetna, Blue Cross, Cigna, Medicare, UnitedHealthcare.
  - **Gender:** All, Female, Male.
  - **Admission Year:** All Years, 2019, 2020, 2021, 2022, 2023, 2024.
  - **One-Click Reset:** Clears all active filters instantly.
* **Dynamic Recalculation Engine:** Powered by a pre-aggregated 1,080-node multidimensional data cube embedded directly in the JavaScript runtime. Any combination of filters recalculates KPIs, condition bars, payer distributions, and abnormal acuity counts in sub-millisecond real time.
* **Responsive KPI Scorecards:** Total Encounters, Average Billing Amount, Average Length of Stay, Abnormal Emergency Test Rate.
* **Interactive Visualizations:**
  - Horizontal bar chart of condition distribution with hover tooltips.
  - Doughnut chart of payer market share.
  - 61-month longitudinal billing trendline with 5-year average reference benchmark.
  - High-acuity emergency condition breakdown.
* **Client-Side CSV Export:** "Export CSV" button allows executives to download a structured CSV summary of whatever filtered cohort is currently active on screen.
* **Executive Action Plan & Takeaways:** Formatted management cards explaining operational equilibrium, financial forecasting stability, and immediate clinical priorities.

---

## 💡 Strategic Business Recommendations

Based on the empirical findings, hospital management and clinical operations directors should execute the following 4 initiatives:

1. **Revenue Cycle Management: Negative Billing Audit**
   - **Finding:** 106 encounters exhibit negative billing amounts ($-\$502.47$ average).
   - **Action:** Launch an immediate internal audit across patient accounting and billing software. Validate whether these entries reflect legitimate refund disbursements, payer reconciliations, or unhandled software credit exceptions. Implement automated input validation in the electronic health record system to prevent unverified negative charge posting.
2. **Inpatient Flow: ALOS & Bed Turnover Optimization**
   - **Finding:** The average length of stay is 15.50 days across all admission types, significantly higher than acute care benchmarks (4.5–5.5 days).
   - **Action:** Establish multidisciplinary early discharge planning teams (physicians, case managers, social workers) initiated on Day 1 of admission. Reducing average stay by even 2.5 days would expand functional bed capacity by ~16% without capital construction expenditure.
3. **Emergency Care: High-Acuity Diagnostic Fast-Track Pathways**
   - **Finding:** 33.36% of emergency visits return abnormal test results, with Obesity (1,058 cases) and Cancer (1,057 cases) representing the largest clinical subgroups.
   - **Action:** Create specialized clinical fast-track protocols in the emergency department for patients presenting with oncology history or complex metabolic conditions to expedite lab panel turnarounds and targeted triage.
4. **Capital Planning: Long-Term Revenue Predictability**
   - **Finding:** Billing per encounter remains remarkably stable (~$25,500/encounter) across 61 consecutive months with zero correlation to patient age ($r = -0.0034$), and insurance payer exposure is evenly divided among 5 major carriers (~20% each).
   - **Action:** Hospital financial officers can model long-term debt servicing and multi-year facility improvements with high certainty, free from single-payer dependency or sharp seasonal revenue dips.

---

## ⚠️ Analytical Scope & Limitations

* **Synthetic Data Source:** The underlying dataset is synthetically generated (encounter-level simulation). Observations such as uniform age distributions (13–89), equal payer proportions (~20%), and zero age-to-billing correlation reflect generative characteristics of the dataset.
* **Encounter vs. Longitudinal Patient Level:** Each row represents a single healthcare admission encounter. The dataset does not contain longitudinal patient identifiers; therefore, metrics must not be interpreted as unique patient lifetime counts, nor can 30-day readmission rates be calculated without longitudinal patient tracking.
* **Gross Billed Charges vs. Net Hospital Margin:** The `Billing Amount` metric captures gross billed charges. In actual hospital accounting, billed charges do not equal contractual reimbursement, cash collections, net patient revenue, or actual hospital treatment cost.

---

## 🤖 AI-Assisted Development Disclosure

This repository represents a **Python Data Analytics project**. Artificial intelligence (Antigravity AI) was utilized strictly as an acceleration tool to:
- Assist in structuring and formatting the comprehensive Jupyter Notebook markdown narrative.
- Formulate the multidimensional aggregation data cube for the interactive JavaScript dashboard.
- Generate responsive Tailwind CSS layout scaffolding.

**No machine learning models, automated clinical diagnosis algorithms, or predictive analytics were fabricated.** All descriptive statistics, metrics, correlations, and findings are directly calculated from the empirical dataset using Python.

---

## 👤 Author & Contact

**Ansh Yadav**  
- **GitHub:** [@ansh-yadav-1](https://github.com/ansh-yadav-1)  
- **LinkedIn:** [Ansh Yadav]((https://www.linkedin.com/in/anshyadav1/)) 
- **Project Repository:** [HealthcareCaseStudy](https://github.com/ansh-yadav-1/HealthcareCaseStudy)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE) for all original code, notebooks, dashboard designs, and written documentation. The underlying synthetic healthcare dataset is published under [CC0: Public Domain](https://creativecommons.org/publicdomain/zero/1.0/).
