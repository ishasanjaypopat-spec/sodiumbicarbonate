Sodium Bicarbonate in CKD: Biostatistics Methods Practice

A biostatistics learning exercise applying advanced clinical trial analysis methods to
synthetic patient data, generated to approximate the effect sizes reported in a
2025 World Journal of Gastroenterology (WJG) Nephrology meta-analysis on sodium
bicarbonate supplementation in chronic kidney disease (CKD).

Synthetic data — read this first

No real patient data is used anywhere in this notebook. All 2,932 "patients" are
generated using NumPy random number generators, with the random parameters chosen so
that the simulated dataset reproduces the headline effect sizes reported in the
source meta-analysis (e.g. mean difference in eGFR change, risk ratio for mortality).

This is a methods-practice exercise, not a clinical analysis or a reproduction of the
meta-analysis's underlying data. Patient characteristics, individual outcomes, and
patient-level relationships are entirely fabricated and should not be cited, reused, or
presented as findings about real patients or real treatment effects.

What it does


Generates a synthetic cohort (n=2,932) with realistic-looking baseline characteristics
(age, sex, eGFR, diabetes status, CKD stage, etc.) and a randomized treatment
assignment
Injects treatment effects calibrated to match published point estimates from the
source meta-analysis (eGFR change, bicarbonate change, blood pressure, mortality,
hospitalization, GI disorders, edema)
Runs sensitivity analysis by resampling treatment effects within the published 95%
confidence intervals
Runs subgroup / effect-modification analysis across CKD stage, sex, and diabetes
status, including interaction terms
Applies multiple-testing correction (Bonferroni and Benjamini-Hochberg FDR) across
subgroup comparisons
Compares the simulated cohort's outcomes back against the published estimates as a
self-consistency check on the data-generating process (not as external validation)
Includes a separate Henderson-Hasselbalch acid-base calculator module


Why

This is a practice exercise for learning how clinical trial statistical methods work
end-to-end — sensitivity analysis, subgroup interaction testing, multiple-comparison
correction, calibration checks — using a realistic clinical scenario as scaffolding,
without needing access to real patient-level data (which is appropriately restricted).

Tech


numpy / pandas for data generation and handling
scikit-learn for regression models and calibration utilities
scipy / statsmodels for statistical testing and multiple-comparison correction
matplotlib / seaborn for visualization


Usage

bashpip install numpy pandas matplotlib seaborn scikit-learn scipy statsmodels

Then run the notebook cells in order. The first cell runs the full synthetic-data
pipeline and statistical analysis; the second cell is a standalone Henderson-Hasselbalch
calculator unrelated to the patient simulation.

Source

Treatment effect sizes are based on a 2025 WJG Nephrology meta-analysis (20 RCTs + 2
NRCTs, n=2,932) on sodium bicarbonate supplementation in CKD. The meta-analysis itself
was not independently verified as part of this exercise — effect sizes are used purely
as plausible inputs for practicing the statistical methods above, not as a basis for
clinical claims.
