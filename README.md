# Water-Potability
This project focuses on determining the potability of water, whether it is safe for human consumption using machine learning classification techniques. Contaminated water can cause serious health problems, and early identification of non-potable water is critical in preventing waterborne diseases. 
💧 Water Potability Classification using Machine Learning
This project uses machine learning techniques to predict whether water is safe to drink based on chemical indicators. Below is a breakdown of the full pipeline and results:

📊 Dataset
Source: Kaggle – Water Potability Dataset

Size: 3,276 rows, 9 chemical features

Target: Potability (0 = Not Safe, 1 = Safe)

🧹 Data Preprocessing
Missing values imputed using KNN Imputer with k=5

Outliers assessed via skewness metrics

Applied square root transformation to right-skewed features (Solids, Conductivity)

🛠️ Feature Engineering
Created risk_score: average of Chloramines, Trihalomethanes, Turbidity, and Organic_carbon

Created solids_conductivity_ratio: Solids / Conductivity

Removed unnecessary categorical binning for better generalization

⚖️ Class Imbalance Handling
Only ~39% of data points labeled as potable

Applied:

Random Oversampling

SMOTE

SMOTE + Tomek Links

SMOTEENN for best results

🤖 Final Model: Random Forest
Tuned with class_weight = 'balanced' and threshold calibration

Best Performance (with SMOTEENN + Threshold tuning):

Accuracy: 71.8%

Precision (Potable): 0.66

Recall (Potable): 0.55

F1-Score (Potable): 0.45

📌 Key Takeaways
Feature interactions (e.g. pH x Chloramines) improved interpretability

Cleaning borderline samples helped reduce false positives

Final model balances safety by reducing the chance of labeling unsafe water as safe

📷 Suggested Images to Include
Confusion Matrix Plot
Shows model performance on both classes.

Feature Importance Bar Chart
Highlights which features most influence potability.

Correlation Heatmap
Visualizes relationships among water quality features.

Precision-Recall Curve
Used for threshold optimization to reduce false positives.
