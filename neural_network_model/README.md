# Hydrogen Yield Prediction from Waste Gasification (NN1_v9)

This notebook trains a neural network to predict **annual hydrogen output (kWh/year)** from waste gasification, based on over 130,000 Monte Carlo simulation records. It's part of a broader regional modelling study focused on hydrogen supply potential in the West Midlands, UK.

## About the Model
The script (`model_training_script.ipynb`) builds and trains multiple feedforward neural network configurations using TensorFlow and Keras. It performs:

- Preprocessing (including median imputation and MinMax scaling)
- Train/test splitting with grouped sampling
- Grid search across 5 deep architectures
- Model evaluation (R², MAE, RMSE, MAPE, MSD)
- Saving of best model and predictions
- Training and prediction visualisation

The final model architecture (NN1\_v9) is a 5-layer ReLU network with L2 regularisation and dropout, trained on all feedstocks combined.

## 📂 Dataset

Due to GitHub’s file size limits, the full training dataset (`monte_carlo_results.csv`, ~38 MB) is hosted on Google Drive:

📎 [Download the dataset](https://drive.google.com/file/d/1QC4NEzxX6meGtlOzFXlOSM6yGl36gKOc/view?usp=drive_link)

The model will not run without this file. Be sure to place it in the same directory as the notebook after downloading.

## 📊 Outputs
The notebook saves the following key files:

- `best_model_allfeedstocks_NN1_v9.keras` — trained model
- `grid_search_results_NN1_v9.csv` — grid search performance results
- `predicted_vs_actual_ANNUALENERGY_H2_kwh_NN1_v9.csv` — prediction comparison
- `model_characteristics_NN1_v9.csv` — model config summary
- `h2_prediction_plot_NN1_v9.png` — actual vs predicted plot
- `loss_curve_NN1_v9.png` — training vs validation loss

## Requirements
This project uses:
- Python 3.9+
- TensorFlow 2.13+
- Scikit-learn
- Pandas, NumPy, Matplotlib

Tested in a JupyterLab environment on HPC and local machines.

---

📬 If you’re using this for energy modelling or ML interpretability in hydrogen systems, I’d love to hear about it! Drop a message via GitHub or LinkedIn.
