# Data Access

This project uses the **MIMIC-IV Clinical Database Demo (v2.2)**, a freely available 100-patient subset of the MIMIC-IV database.

Raw data files are not included in this repository due to PhysioNet's data use agreement. To reproduce this analysis:

1. Create a free account at [physionet.org](https://physionet.org)
2. Go to the [MIMIC-IV Clinical Database Demo](https://physionet.org/content/mimic-iv-demo/2.2/) page
3. Accept the data use agreement
4. Download the following files and place them in this `data/` folder:
   - `admissions.csv`
   - `patients.csv`
   - `diagnoses_icd.csv`
   - `d_icd_diagnoses.csv`
   - `labevents.csv`
   - `d_labitems.csv`
   - `icustays.csv`

Once downloaded, run the notebook in `notebook/icu_analysis.ipynb` from the top to reproduce the full pipeline.
