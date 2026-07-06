# ICU Length of Stay & 30-Day Readmission Analysis

## Overview

This project analyzes admission-level factors, diagnosis category, admission lab values, and prior visit history, to explore their relationship with ICU length of stay and 30-day hospital readmission. The analysis uses the MIMIC-IV Clinical Database Demo, a 100-patient, freely available subset of the MIMIC-IV electronic health record database from Beth Israel Deaconess Medical Center.

Data was extracted and joined using SQL, cleaned and statistically tested using Python (pandas, scipy), and visualized in a 4-view Tableau dashboard.

## Key Findings

This is a demo-scale analysis (140 ICU stays), so most tests are reported alongside their statistical significance rather than presented as confirmed conclusions:

- **ICU length of stay is heavily right-skewed**: most stays last 1-3 days, with a small number of outlier patients staying 15-20+ days. Medians were used throughout instead of means to account for this.
- **Diagnosis category and admission lab values (creatinine, BUN, glucose, hemoglobin, sodium, WBC) were not statistically significantly associated with ICU length of stay** in this sample (Kruskal-Wallis p = 0.26; lab correlations all under 0.15).
- **Prior visit count showed a directional but not statistically significant relationship with 30-day readmission** (Mann-Whitney U p = 0.19), with readmitted patients having a higher median number of prior visits (1 vs. 0).
- **Diagnosis category showed a suggestive relationship with 30-day readmission**, with Respiratory admissions readmitting at ~46% versus ~12-21% for other categories. This result did not meet the standard reliability threshold for a chi-square test at this sample size (several cells had fewer than 5 expected patients) and should be treated as a pattern worth investigating with a larger sample, not a confirmed finding.

## Charts

| Chart | Description |
|---|---|
| ICU LOS Distribution | Histogram showing the right-skewed shape of ICU length of stay |
| LOS by Diagnosis Category | Box plot comparing ICU length of stay across the 6 diagnosis categories with reliable sample sizes (n≥13) |
| Readmission Rate by Category | Bar chart of 30-day readmission rate per diagnosis category, with patient count labeled on each bar |
| Readmission by Prior Visit History | Bar chart of 30-day readmission rate across prior-visit history bins |

## Live Dashboard

[View on Tableau Public →](https://public.tableau.com/app/profile/kesheka.edupuganti8192/viz/ICUAnalysisKPIDashboard/ICUAnalysisKPIDashboard)

## Data Source

[MIMIC-IV Clinical Database Demo (v2.2)](https://physionet.org/content/mimic-iv-demo/2.2/), via PhysioNet. See `data/README.md` for download instructions (raw data is not included in this repository per PhysioNet's data use terms).

## Tools

Python, pandas, scipy, SQLite, Tableau

## How to Run

Clone the repo and install dependencies:

```
git clone https://github.com/KeshekaE/icu-los-readmission-analysis
cd icu-los-readmission-analysis
pip install pandas scipy matplotlib jupyter
```

Then download the MIMIC-IV demo files by following the instructions in `data/README.md`, placing them in the `data/` folder.

Finally, launch the notebook:

```
jupyter notebook notebook/icu_analysis.ipynb
```

---

*This project is part of my data analytics portfolio.*

## Portfolio

[Portfolio Link →](https://keportfolio.vercel.app)

## Author

**Kesheka Edupuganti**
Data Analyst & BI Specialist | Loma Linda, CA
ekesheka1010@gmail.com
[LinkedIn](https://www.linkedin.com/in/kesheka-edupuganti-b53a96293/)
