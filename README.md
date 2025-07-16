# Predicting Hydrogen Yield from Waste Gasification

This repository contains two core components of a machine learning workflow designed to estimate annual hydrogen production from waste gasification in the West Midlands, UK. The models were trained and interpreted using real-world data generated via Monte Carlo simulation.

## 🔧 Repository Structure

- [`neural_network_model/`](neural_network_model/)  
  Contains a deep learning pipeline (Keras) used to predict hydrogen output (kWh/year) based on waste, reactor, and system-level features. Includes:
  - A multi-architecture grid search
  - Final model training (`NN1_v9`)
  - Performance evaluation and plots

- [`SHAP-interpretation-of-neural-network-model/`](SHAP-interpretation-of-neural-network-model/)  
  Applies SHAP (SHapley Additive exPlanations) to interpret the trained neural network model. Results include:
  - Global feature importance rankings
  - Feedstock-specific SHAP plots
  - Exported CSVs for post-analysis

## 📁 Input Dataset

All models and SHAP analyses rely on a single dataset of Monte Carlo simulation results. Due to file size limits, it is hosted externally:

📥 **Download here:**  
[monte_carlo_results.csv (Google Drive)](https://drive.google.com/file/d/1QC4NEzxX6meGtlOzFXlOSM6yGl36gKOc/view?usp=drive_link)

## ⚠️ Notes

- The SHAP analysis was performed **without GPU acceleration** due to restrictions on the university's HPC environment. As a result, runtime is longer than ideal.
- The neural network was trained using `tensorflow.keras` and optimised via early stopping and L2 regularisation.
- All feature names are mapped to human-readable labels using a dictionary in the SHAP script.

## 📊 Use Cases

- Understanding key process drivers in waste-to-hydrogen systems
- Informing gasification setup selection via model interpretation
- Exploring feature sensitivity for different feedstocks (e.g. plastics vs biomass)

---

📌 _This work was undertaken as part of a PhD project exploring machine learning applications in local hydrogen production systems._
