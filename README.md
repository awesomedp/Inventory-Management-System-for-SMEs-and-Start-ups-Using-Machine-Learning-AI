# Inventory-Management-System-for-SMEs-and-Start-ups-Using-Machine-Learning-AI
This model is an AI-driven, probabilistic EOQ framework that integrates LSTM-based demand forecasting and correlation-adjusted safety stock to optimize inventory under uncertainty.

## 📦 How to Use This AI-Based Inventory Optimization Tool

This tool implements an AI-powered, probabilistic EOQ model for smarter inventory planning.  
It is designed to help small and medium-sized enterprises (SMEs) forecast demand and determine optimal order quantities under uncertainty.

### ✅ Features
- Demand forecasting using LSTM (deep learning)
- Synthetic demand simulation using Geometric Brownian Motion (GBM)
- Lead time uncertainty modeling with KDE + Monte Carlo
- Correlation-adjusted safety stock calculation
- Comparison of Classical EOQ, Probabilistic EOQ, and AI-based EOQ

---

### ⚙️ Requirements

Install Python dependencies: pip install numpy pandas matplotlib scikit-learn tensorflow scipy

---

### 📂 File Structure

├── data/
│ ├── Dataset_1_Simulated_Demand_mean_revert.csv
│ ├── ... (total 10 datasets)
│
├── lstm_forecasting.py # LSTM training and forecasting
├── eoq_comparison.py # EOQ vs Probabilistic vs AI-based comparison
├── LSTM_model_dataset_X.h5 # Saved models (auto-generated)
├── results/
│ ├── Dataset_X_Loss_Curve.png
│ ├── Dataset_X_Actual_vs_Predicted.png
│ ├── Dataset_X_Future_30_Forecast.png
│ └── LSTM_Training_Summary.csv

---

### 🧪 How to Run

#### 1. Run LSTM demand forecasting

- Input: 10 demand CSV files in `/data/`
- Output:
  - Trained models (`.h5`)
  - Forecast plots (`.png`)
  - Summary CSV of training results

If you want to use your own demand data, prepare a `.csv` file with the following format:

Simulated_Demand
123
145
136
...

- The file must contain **one column only**, named exactly `Simulated_Demand` (case-sensitive).
- Each row should represent daily demand for a product (minimum of 50–100 days recommended).
- Place your files in the `data/` folder before running the script.

You can prepare multiple CSV files for batch training (e.g., Dataset_1.csv, Dataset_2.csv, etc.)

#### 2. Compare Inventory Models

python eoq_comparison.py

- Output:
  - Bar chart comparing total cost, average inventory, and stockouts
  - Printed summary table

---

### 📈 Sample Output

| Model             | Total Cost | Avg Inventory | Stockouts |
|------------------|------------|---------------|-----------|
| Classical EOQ    | 4810.56    | 89.53         | 17        |
| Probabilistic EOQ| 5253.18    | 112.85        | 5         |
| AI-based EOQ     | **5070.12**| **96.73**     | **2**     |

---

### 📌 Notes for SMEs

- You can replace the simulated data with your own sales history.
- The input CSV files should contain one column named `Simulated_Demand`.
- No AI or coding background required — just follow the steps.
- Especially effective for businesses with seasonal or volatile demand.

---

### 📤 License

This project is licensed under the MIT License — free to use, modify, and distribute.


