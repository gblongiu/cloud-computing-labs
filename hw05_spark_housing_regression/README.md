# HW05 – Spark Housing Regression (California Dataset)

This lab recreates a homework assignment from **Cloud Computing for Data Science**  
using PySpark and the California housing dataset. The goal is to practice regression  
workflows in a distributed setting and compare several models on the same features.

The main files are:

- `spark_housing_regression.ipynb`
- `california_housing.csv`

---

## Objectives

- Configure a PySpark environment in Google Colab  
- Load a tabular housing dataset into a Spark DataFrame  
- Explore the data with summary statistics and simple plots  
- Build a feature vector with `VectorAssembler`  
- Train and evaluate three regression models  

  - Linear Regression  
  - Decision Tree Regressor  
  - Gradient Boosted Trees Regressor  

- Compare model performance using RMSE and R² on a held out test set  

---

## Dataset

`california_housing.csv` comes from `sklearn.datasets.fetch_california_housing`.  
Each row describes a California housing district.

Key columns:

- `MedInc` – median income in the district  
- `HouseAge` – median house age  
- `AveRooms`, `AveBedrms` – average rooms and bedrooms per household  
- `Population`, `AveOccup` – population and average occupants  
- `Latitude`, `Longitude` – location  
- `medv` – target variable, median house value in hundreds of thousands of dollars  

The notebook uses these eight features to predict `medv`.

---

## Notebook structure

`spark_housing_regression.ipynb` is organized into the sections below.

### 1. Environment setup

- Install OpenJDK 11 and PySpark in Colab  
- Configure `JAVA_HOME`  
- Create a `SparkSession` and confirm the context is running  

### 2. Data loading and exploration

- Read `california_housing.csv` into a Spark DataFrame  
- Inspect schema and summary statistics with `describe`  
- Compute correlations between `medv` and each numeric feature  
- Create a small scatter matrix for a subset of columns  

### 3. Feature engineering

- Select the feature columns and the label (`medv`)  
- Use `VectorAssembler` to build a single `features` column  
- Split the data into training and test sets with `randomSplit`  

### 4. Models and evaluation

**Linear Regression**

- Fit a regularized linear model  
- Inspect coefficients and intercept  
- Evaluate RMSE and R² on the test set  

**Decision Tree Regressor**

- Train a regression tree  
- Examine feature importances  
- Evaluate RMSE and R²  

**Gradient Boosted Trees**

- Train a GBT regressor  
- Evaluate RMSE and R²  

### 5. Summary

- Brief comparison of the three models and their relative performance  

---

## How to run

### Option 1 – Open in Colab

1. Open the notebook in GitHub.  
2. Use the “Open in Colab” link at the top of the file.  
3. Run all cells from top to bottom.  

The notebook installs dependencies, starts Spark, and reads  
`california_housing.csv` from the same folder.

### Option 2 – Local PySpark environment

1. Clone this repository.  
2. Create a virtual environment and install  

   - `pyspark`  
   - `findspark`  
   - `pandas`  
   - `matplotlib`  
   - `scikit-learn`  

3. Start Jupyter or VS Code and open `spark_housing_regression.ipynb`.  
4. Adjust any Colab specific paths or installs if needed, then run the cells.

---

## Possible extensions

Ideas for extending this lab:

- Add feature scaling or transformations  
- Try other regression models such as Random Forest Regressor  
- Tune hyperparameters with `CrossValidator` or `TrainValidationSplit`  
- Log metrics and parameters with an experiment tracker such as MLflow  
