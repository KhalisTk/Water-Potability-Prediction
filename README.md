# Water-Potability-Prediction
A Machine Learning Pipeline to predict the potability of water from physical-chemical water quality data, comparing XGBoost and LSTM models (SDG 6).
Dataset : 
The dataset is not redistributed here. Download `water_potability.csv` from
[Kaggle](https://www.kaggle.com/datasets/adityakadiwal/water-potability)
and place it next to the notebook before running.
Expected: 3,276 rows, 9 features + `Potability` target.

Problem :
The access to safe drinking of water is a critical global health issue under SDG 6, and to test the water samples manually for its potability would be time-consuiming and resource heavy. Therefore, this project explores the possibility of machine learning being applied to predict the water potability directly using the physical-chemical measurements to enable a faster and more scalable water quality assestment.

Approach :
EDA: identified missing values (up to 24% in Sulfate) and skewed outliers
<img width="867" height="487" alt="image" src="https://github.com/user-attachments/assets/9930148e-e314-49da-b44a-59997b4bc962" />
<img width="802" height="593" alt="image" src="https://github.com/user-attachments/assets/a9e415f0-7a11-4f45-8553-c36019b5230c" />

Preprocessing: Outliers were handled by winsorization: for each of the nine features, values below the 1st percentile were raised to that bound and values above the 99th percentile lowered to it, capping roughly 2% of observations per feature without discarding any rows. Missing values were then imputed with the column mean. Three features contained missing data — Sulfate (781 values, 23.8%), ph (491, 15.0%) and Trihalomethanes (162, 4.9%) — affecting 1,434 of 3,276 rows in total a listwise deletion would therefore have removed around a third of the dataset, so imputation was preferred. Imputation was applied after winsorization so that extreme values could not distort the imputed mean.
<img width="730" height="202" alt="image" src="https://github.com/user-attachments/assets/4850d3dc-bbf4-4eaf-9d95-43c9edd29838" />

Models: XGBoost vs LSTM, stratified 80/20 split, train-only scaling

Results :
XGBoost: 65.85% accuracy
LSTM: 64.79% accuracy
<img width="1087" height="732" alt="image" src="https://github.com/user-attachments/assets/d5a4e132-3586-494b-8132-787ae9ae52e9" />
Class imbalance identified as main limiter on potable-class recall

Future Implementation : 
To address the class imbalace
To evaluate the model using Precision/Recall/F1 instead of just using accuracy

Tech/Library Used :  Python, Pandas, NumPy, Scikit-learn, XGBoost, TensorFlow/Keras


rFlow/Keras
