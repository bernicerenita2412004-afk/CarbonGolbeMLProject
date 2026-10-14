# CarbonGlobe: Global Land Ecosystem Forecasting

## Project Overview

This project was developed for the **CarbonGlobe / IEEE BigData Cup 2026 AI Emulation Challenge**. It focuses on predicting year-40 forest height and above-ground biomass (AGB) under two climate scenarios: SSP126 and SSP585.

The project explores a baseline machine-learning model and an optimized ensemble approach using climate summaries, initial ecosystem states, forest-age information, and chronosequence-based reference predictions.

## Objectives

- Predict year-40 forest height and above-ground biomass.
- Develop machine-learning models using ecosystem simulation inputs.
- Perform climate and ecological feature engineering.
- Compare baseline and optimized models.
- Generate prediction CSV files for the challenge.

## Methodology

### 1. Data Preprocessing and Feature Engineering

The project uses monthly environmental inputs and initial ecosystem state variables. Engineered features include climate summaries, ecological ratios, site characteristics, and forest-age dynamics.

### 2. Baseline Model

The initial model uses `HistGradientBoostingRegressor` to learn relationships between input features and target predictions.

### 3. Optimized Model

The optimized pipeline uses a chronosequence anchor based on the ecosystem state at approximately forest age + 40 years, capped at age 500.

The prediction strategies described in the project report include:

- Delta/residual prediction
- Direct prediction
- Log-ratio prediction
- Random-forest-style prediction

The optimized approach combines predictions using ensemble weights and applies scenario-dependent anchor shrinkage and prediction clipping.

## Results

According to the project report:

- Initial baseline score: **0.238**
- Best recorded optimized score: **0.095**
- Latest displayed optimized score: **0.101**

The report's best recorded result represents an approximately **60.1% reduction** in score compared with the initial baseline. Lower scores are better according to the report.

See `RESULTS.md` for the comparison and calculations.

## Technologies Used

- Python
- Jupyter Notebook
- NumPy
- pandas
- scikit-learn
- LightGBM
- XGBoost

## Repository Structure

```text
CarbonGlobe/
├── README.md
├── RESULTS.md
├── code/
│   ├── initial_model.ipynb
│   └── optimized_model.ipynb
├── submissions/
│   ├── submission_1.csv
│   └── submission_2.csv
├── report/
│   └── ml_report.pdf
└── results/
    ├── rmse_comparison.png
    └── rmse_reduction.png
```

The filenames and folders shown above are examples; adjust them to match the files you actually upload.

## How to Run

1. Clone or download this repository.
2. Install the required Python libraries.
3. Obtain the competition dataset from its authorized source.
4. Update the dataset paths inside the notebooks.
5. Open the notebooks in Jupyter Notebook or JupyterLab.
6. Run the cells in order and review the generated predictions.

The original competition dataset is not included in this repository.

## Limitations

The project report identifies potential validation optimism, manually selected shrinkage and clipping parameters, and the need for additional ablation studies. The predictions are based on ecosystem simulation data and should not be interpreted as direct field measurements.

## Team Members

- Arshad Iqbaul Hussain
- Kaavyan
- Bernice Renita

**Department:** Computer Science and Engineering  
**Institution:** SSN College of Engineering, Kalavakkam, India

## Acknowledgment

Developed as part of the CarbonGlobe / IEEE BigData Cup 2026 AI Emulation Challenge. Follow the competition rules and data-use terms when publishing project materials.
