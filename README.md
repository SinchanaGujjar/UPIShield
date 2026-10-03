# UPIShield — UPI Fraud Detection System

UPIShield is a machine-learning project for detecting potentially fraudulent financial transactions using the PaySim transaction dataset.

## Overview

The project implements and compares two classification models:

- Random Forest
- XGBoost

The notebook performs data exploration, preprocessing, categorical encoding, class-imbalance handling through upsampling, train-test splitting, feature scaling, model training, and performance evaluation.

## Workflow

1. Load the PaySim transaction dataset.
2. Explore the data and check for missing values.
3. Remove `nameOrig`, `nameDest`, and `isFlaggedFraud`.
4. Convert the categorical `type` feature into numerical features using one-hot encoding.
5. Handle class imbalance by upsampling the minority (`isFraud = 1`) class.
6. Split the data into training and testing sets.
7. Standardize the features using `StandardScaler`.
8. Train Random Forest and XGBoost classifiers.
9. Evaluate the models using accuracy, precision, recall, F1-score, classification reports, and confusion matrices.
10. Analyze Random Forest feature importance and compare model performance.

## Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Matplotlib
- Google Colab

## Dataset

The project uses the **PaySim** synthetic financial transaction dataset.

The raw dataset is intentionally **not included in this repository** because of its large size. Download/obtain the dataset separately and update the path in the notebook as needed.

The original notebook currently expects:

```text
/content/drive/MyDrive/Colab Notebooks/paysim.csv
```

If you use a different location, change the `pd.read_csv(...)` path in the notebook.

## Running the Project

### Option 1 — Google Colab

1. Open `upi_fraud_detection.ipynb` in Google Colab.
2. Make the PaySim dataset available at the path expected by the notebook, or update the path.
3. Run the notebook cells from top to bottom.

### Option 2 — Local Python environment

Install the required packages:

```bash
pip install -r requirements.txt
```

Then open the notebook using Jupyter:

```bash
jupyter notebook
```

For local execution, the Google Drive mounting cell is specific to Colab and should be replaced/removed, and the dataset path should be changed to your local `paysim.csv` location.

## Model Evaluation

The notebook evaluates Random Forest and XGBoost using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

It also includes:

- Random Forest feature-importance analysis
- Model accuracy comparison
- Classification-metric comparison
- Type I and Type II error comparison

## Notes and Limitations

- The experiment uses a subset of 100,000 transactions from the PaySim dataset.
- The dataset is synthetic and should not be treated as real-world UPI transaction data.
- The notebook handles class imbalance through upsampling before the train-test split.
- Reported results therefore describe this particular notebook experiment and should not be interpreted as real-world fraud-detection performance.
- The notebook is an academic machine-learning project, not a production fraud-detection system.

## Repository Structure

```text
UPIShield/
├── upi_fraud_detection.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Project Type

Academic Machine Learning Mini Project.
