# Diamond Price Estimator - ML Pipeline Project

This project was developed for the **Machine Learning** module during the 5th semester at **SUPSI DTI** (University of Applied Sciences and Arts of Southern Switzerland).

## Project Overview
The primary goal of this project is to build an end-to-end Machine Learning pipeline to predict the price of diamonds based on their physical characteristics. The project covers the entire workflow, from data acquisition and cleaning to model evaluation and hyperparameter tuning.

## Dataset
The dataset used in this project is the **Diamond Price Prediction** dataset (available on Kaggle). It contains information on 53,940 diamonds with 10 features:
- **Numerical features**: carat, depth, table, x, y, z.
- **Categorical features**: cut, color, clarity.
- **Target variable**: price (in US dollars).

## Pipeline Architecture

### 1. Data Preprocessing
- **Cleaning**: Removal of invalid observations where dimensions (x, y, z) were zero.
- **Feature Engineering**: Exploration of synthetic features like "volume" to reduce multicollinearity.
- **Encoding**: Manual **Ordinal Encoding** was applied to categorical variables (`cut`, `color`, `clarity`) to preserve their intrinsic hierarchical order.
- **Scaling**: Standardization was performed using `StandardScaler` to ensure all numerical features are on the same scale.
- **Data Splitting**: The dataset was divided into an **80% training set** and a **20% test set**.

### 2. Modeling
The project explores both linear and ensemble non-linear models:
-  **Lasso Regression**: Used primarily for feature importance analysis.
-  **Ridge Regression**: Implemented with 10-fold Cross-Validation to find the optimal regularization parameter ($\alpha$).
- **Random Forest Regressor**: An ensemble method (Bagging) used to capture non-linear relationships.  Hyperparameters were optimized using `RandomizedSearchCV`.

### 3. Evaluation Metrics
Models were evaluated using the following regression metrics:
- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **$R^2$ Score** (Coefficient of Determination)

## Results
The **Random Forest** model significantly outperformed the linear models, achieving the following results on the unseen test set:
- **RMSE**: 513.73
- **MAE**: 260.11
-  **$R^2$ Score**: 0.9835

These results demonstrate that non-linear ensemble methods are highly effective at capturing the complex pricing structures of the diamond market.

## Requirements
To run this project, you will need the following Python libraries:
- `numpy`
- `pandas`
- `scikit-learn`
- `matplotlib`

## How to Run
1. Ensure `diamonds.csv` is in the same directory as the notebook.
2. Open `project_diamonds.ipynb` in Jupyter Notebook or VS Code.
3. Run all cells to execute the pipeline.

*Project developed for SUPSI DTI - 5th Semester*

