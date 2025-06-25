# Generating-time-series-data-using-TimeGAN
This project demonstrates how to **generate synthetic multivariate time series data using TimeGAN** and how to **evaluate its quality** through downstream forecasting using a Random Forest model.

---

## 📁 Project Overview

This project is divided into two major parts:

1. `TimeGAN.ipynb` – Generates synthetic time series data using the TimeGAN architecture.
2. `Comparision of performance using random forest.ipynb` – Evaluates the quality of the synthetic data in predictive tasks against real-world financial data.

---
## 📦 Directory Contents

| File/Folder                                     | Description                                                 |
|------------------------------------------------|-------------------------------------------------------------|
| `TimeGAN.ipynb`                                 | Trains TimeGAN and generates synthetic stock price data     |
| `Comparision of performance using random forest.ipynb` | Compares predictive performance using synthetic, real, and mixed datasets |
| `adj_close_subset.xls`                          | Optional Excel export of a subset of stock data             |
| `assets.h5`                                     | HDF5 file containing preprocessed real stock data           |
| `time_gan/TimeSeriesGAN.h5`                     | Trained TimeGAN model checkpoint                            |
| `time_gan/synthetic_timeseries.xls`             | Generated synthetic data in Excel format                    |

---
## ✅ Requirements

Install Python (3.8–3.11 recommended), then install required packages:
Here are the essential packages:

```bash
pip install tensorflow pandas numpy matplotlib seaborn scikit-learn openpyxl
```

---
## 🚀 How to Run

### Step 1: Open the Notebook

You can open this in **Jupyter Notebook**, **JupyterLab**, or **Google Colab**.

#### Option A – Jupyter
```bash
jupyter notebook
```
Then open `TimeGAN.ipynb`

#### Option B – VS Code
Use the Jupyter extension to open and run the notebooks inside VS Code.

---
### Step 2: Run `TimeGAN.ipynb`

This notebook:
- Loads the `assets.h5` file (real stock prices)
- Trains a TimeGAN model
- Generates synthetic time series
- Saves it in `.npy`, `.h5`, and `.xls` formats

---

### Step 3: Run `Comparision of performance using random forest.ipynb`

This notebook:
- Loads the real and synthetic data
- Trains Random Forest models on:
  - Real data
  - Synthetic data
  - Real + Synthetic data
- Compares them using:
  - Mean Absolute Error (MAE)
  - Root Mean Square Error (RMSE)
  - R² score
  - PCA and feature importance plots

---
## 📊 Output Files

- `synthetic_timeseries.xls`: Viewable synthetic data
- `TimeSeriesGAN.h5`: Trained model checkpoint
- Evaluation plots in the notebook outputs (e.g., MAE bar plot, PCA plots)

---

## 📌 Notes

- If you don’t have a GPU, training might take ~5–10 minutes on CPU.
- You can regenerate the `.h5` file using `yfinance`, but the provided `assets.h5` is ready to use.
- The synthetic data is not an exact copy but statistically similar to the original.

---
## 📚 References
- [Orignal Github repo used for reference](https://github.com/stefan-jansen/machine-learning-for-trading/tree/main/21_gans_for_synthetic_time_series)
- [TimeGAN: Time-series Generative Adversarial Networks (NeurIPS 2019)](https://arxiv.org/abs/1907.05321)
- [TensorFlow](https://www.tensorflow.org/)
- [scikit-learn](https://scikit-learn.org/)
- [yfinance](https://pypi.org/project/yfinance/)
