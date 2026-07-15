# Vehicle CO2 Emissions Prediction 🚗

Predicting vehicle CO2 emissions (g/km) from Vehicle specifications, using a regression model.

## Problem Statement

Given a vehicle's engine size, cylinder count, transmission, and fuel type, predict its CO2 emissions in grams per kilometre. This is a **regression** problem.


## Dataset

- Source: [Vehicle CO2 Emissions Dataset, Kaggle](https://www.kaggle.com/datasets/brsahan/vehicle-co2-emissions-dataset)
- **7,385 rows, 12 columns**, no missing values
- Target column: `CO2 Emissions(g/km)`
- Features:
  - `Make`, `Model`, `Vehicle Class` — categorical
  - `Engine Size(L)`, `Cylinders` — numeric
  - `Transmission`, `Fuel Type` — categorical
  - `Fuel Consumption City (L/100 km)`, `Fuel Consumption Hwy (L/100 km)`, `Fuel Consumption Comb (L/100 km)`, `Fuel Consumption Comb (mpg)` — numeric

## Approach

- Exploratory data analysis (EDA) — distributions, correlation with target, categorical value counts
- Train/test split (before any preprocessing decisions, to avoid data leakage)
- Preprocessing — encode categorical features (`Make`, `Model`, `Vehicle Class`, `Transmission`, `Fuel Type`); consider whether `Model` has too many unique values for one-hot encoding
- Modelling using Random Forest Regressor
- Hyperparameter tuning on the best-performing baseline using RandomizedSearchCV and GridSearchCV
- Evaluation using MAE, RMSE, and R²

## Results

| Metric | Score |
|--------|-------|
| MAE | 7.171619598980079 |
| RMSE | 10.818936377071273 |
| R² | 0.9659703304385401 |

## Tools & Libraries

- Python
- pandas, NumPy
- scikit-learn (regression models)
- Matplotlib / Seaborn (visualisation)
- Jupyter Notebook

## Project Structure

```
.
├── README.md
├── .gitignore
├── vehicle-co2-emissions-regression.ipynb   # main notebook
└── data/                                     # (not tracked in git — download separately)
    └── co2.csv
```

## Setup & Installation

This project uses **Miniconda** for dependency management.

```bash
# Clone the repository
git clone https://github.com/yourusername/vehicle-co2-emissions-regression.git
cd vehicle-co2-emissions-regression

# Create and activate a conda environment
conda create -n vehicle-co2-emissions-regression python=3.10
conda activate vehicle-co2-emissions-regression

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook
```

<!-- TODO: generate a requirements.txt with: conda list -e > requirements.txt (or pip freeze > requirements.txt) -->
