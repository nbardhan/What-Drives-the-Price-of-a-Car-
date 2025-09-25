🚗 Car Price Prediction Project

📌 Problem Statement

Online car marketplaces often list vehicles with a mix of structured and unstructured information (year, odometer, fuel type, transmission, etc.). Buyers and sellers want to estimate a fair market price based on these attributes, but missing data, categorical variables, and inconsistent formatting make this a challenge.

The goal of this project is to predict car prices from available features using regression models.

⸻

📊 Dataset

	•	Source: Used car listings (≈ 426k rows)

	•	Target Variable: price

	•	Features:

	•	year (int)

	•	manufacturer (categorical)

	•	condition (categorical, e.g. “good”, “excellent”)

	•	cylinders (categorical/numeric mix)

	•	fuel (categorical)

	•	odometer (numeric)

	•	title_status (categorical)

	•	transmission (categorical)

	•	drive (categorical)

	•	type (categorical)

	•	paint_color (categorical)

	•	state (categorical)

⸻

⚙️ Data Preparation
	1.	Dropped irrelevant columns
	•	id, VIN, and other identifiers with no predictive power.
	2.	Handled missing data
	•	Kept missing rows but filled categorical NAs with "unknown".
	•	Left year and odometer missing values minimal (<1% of dataset).
	3.	Encoded categorical variables
	•	Used one-hot encoding (pd.get_dummies) to transform text labels into numeric features.
	4.	Defined features/target
	•	X = all features (encoded)
	•	y = price

⸻

🤖 Modeling

	•	Train/Test Split

	•	80% training / 20% testing

	•	Baseline Model

	•	Predicts mean training price for all cars.

	•	Linear Regression & Lasso Regression (feature selection)

	•	Cross-Validation & Hyperparameter Tuning

	•	Used GridSearchCV to tune regularization parameter (alpha).

⸻

📏 Evaluation

	•	Metrics:

	•	MSE (Mean Squared Error)

	•	RMSE (Root Mean Squared Error)

	•	R² (Coefficient of Determination)

	•	Compared all models against the baseline.

	•	Ridge and Lasso were used to reduce overfitting and identify most important predictors.


⸻

🔑 Key Findings

	•	Odometer and year are among the strongest continuous predictors of price.

	•	Certain categorical features (manufacturer, fuel type, title status) also have strong influence.
    
	•	Lasso regression helped shrink unimportant categorical dummy variables close to 0.

⸻
