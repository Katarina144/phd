# SHAP Analysis for Hydrogen Prediction from Waste Gasification

This notebook applies SHAP (SHapley Additive exPlanations) to interpret the predictions made by a trained neural network model estimating annual hydrogen yields from waste gasification.

The model was trained on a Monte Carlo dataset simulating realistic process configurations for the West Midlands Combined Authority (WMCA). SHAP is used here to understand which input features have the greatest influence on model predictions — both globally and for each feedstock type individually.

---

##  📂 Dataset

This repo assumes access to the Monte Carlo simulation results used to train the model. You can download the input dataset here:

🔗 [monte_carlo_results.csv](https://drive.google.com/file/d/1QC4NEzxX6meGtlOzFXlOSM6yGl36gKOc/view?usp=drive_link)

---

## ⚠️ Note on Runtime

Due to restricted GPU access on the university's HPC, this analysis runs using the slower CPU-based `KernelExplainer`. That means:

- **Global SHAP analysis** takes a few minutes  
- **Per-feedstock SHAP analysis** takes significantly longer (especially for full-feature plots across all 5 feedstocks)

If you're running the full analysis, it's best to let it run in the background or overnight.

---

## About the Model

The model being explained was trained to predict `ANNUALENERGY_H2_kwh` from a wide range of process, feedstock, and system-level features (53 in total). Input data was scaled using MinMaxScaler, and missing values were median-imputed. SHAP was computed using 500 representative samples across the dataset to balance runtime and fidelity.

---

## 🖼️ Visual Outputs

- 6 global summary plots (top 10, top 20, full — in dot and bar styles)
- 30 per-feedstock summary plots (top 5, top 10, full × 5 feedstocks)
- Plots saved in high-resolution PNG for publication or presentation use.

---

Feel free to adapt or reuse the SHAP workflow for your own models — the variable mapping and plotting functions are designed to be flexible.

