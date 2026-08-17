# Predicting Glider Flight Characteristics from Meteorological Data

Short description
-----------------
This repository contains Jupyter notebooks and Python code for predicting flight characteristics of sailplanes (gliders) from meteorological data. The goal is to explore how weather variables (wind, thermal activity, humidity, pressure, etc.) influence glide performance and to build models that can estimate key flight parameters (e.g., sink rate, speed-to-fly, climb rate).

Contents
--------
- Jupyter notebooks with data exploration, feature engineering, modeling, and evaluation.
- Python scripts / modules for preprocessing and model training (if present).
- Example visualizations and evaluation reports.

Key features
------------
- End-to-end workflow from raw meteorological inputs to flight parameter predictions.
- Exploratory data analysis and domain-driven feature engineering.
- Baseline and more advanced regression models (scikit-learn / optionally deep learning).
- Reproducible notebooks that show data preparation, training, and evaluation steps.

Getting started
---------------
1. Clone the repository:
   ```bash
   git clone https://github.com/estanislaomolina/Prediccion-de-caracteristicas-del-vuelo-a-vela-a-partir-de-datos-meteorologicos.git
   cd Prediccion-de-caracteristicas-del-vuelo-a-vela-a-partir-de-datos-meteorologicos
   ```

2. Create a Python environment (recommended):
   - Using conda:
     ```bash
     conda create -n glider-pred python=3.10
     conda activate glider-pred
     pip install -r requirements.txt
     ```
   - Or using pip + venv:
     ```bash
     python -m venv venv
     source venv/bin/activate    # Windows: venv\Scripts\activate
     pip install -r requirements.txt
     ```

3. If there is no requirements.txt, install typical packages used in the notebooks:
   ```bash
   pip install numpy pandas scikit-learn matplotlib seaborn jupyterlab xgboost
   ```

Data
----
- Place raw meteorological and flight data in a `data/` directory (or update paths in notebooks).
- If data is sensitive or too large for the repository, keep only metadata or example CSVs and describe how to obtain the full dataset.
- Suggested structure:
  ```
  data/
    raw/            # raw CSVs or downloaded files
    processed/      # cleaned and feature-engineered datasets used for modeling
  ```

Notebooks
---------
- Open the notebooks with Jupyter or JupyterLab:
  ```bash
  jupyter lab
  ```
- Typical notebooks (adjust names if your repo uses different filenames):
  - `01-data-exploration.ipynb` — dataset overview and visualizations
  - `02-feature-engineering.ipynb` — cleaning and new feature creation
  - `03-modeling.ipynb` — training baseline and advanced models
  - `04-evaluation-and-results.ipynb` — metrics, plots, and model comparison

Reproducing results
-------------------
- Run the notebooks in order (exploration → feature engineering → modeling → evaluation).
- For reproducibility, set random seeds in model-training cells and document package versions (pip freeze > requirements.txt or environment.yml).

Modeling approach (example)
---------------------------
- Baseline: linear regression or tree-based regressors (RandomForest, XGBoost).
- Features: wind speed/direction components, temperature, pressure, humidity, vertical velocity estimates (if available), time-of-day, and derived features (e.g., wind shear, thermal indices).
- Evaluation: MAE, RMSE, R², and visual residual analysis; cross-validation over time splits if data is temporal.

Results
-------
- Include brief summary of the best-performing models and key takeaways in the final notebook or a `results/` folder.
- Provide sample plots (predicted vs actual, residuals, feature importances).

Tips and best practices
-----------------------
- Use time-based cross-validation when data is sequential.
- Check for data leakage (do not use future meteorological observations when predicting past flight segments).
- Standardize or normalize features when using models sensitive to scale.
- Consider domain knowledge (thermal detection, local orography) to engineer informative features.

Contributing
------------
Contributions are welcome. If you plan to add code or notebooks:
1. Fork the repository.
2. Create a feature branch.
3. Open a pull request with a clear description of changes.

Contact
-------
For questions or suggestions, contact: estanislaomolina (GitHub) — estanislaomolina05@gmail.com
