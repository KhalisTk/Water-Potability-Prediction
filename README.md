# Water-Potability-Prediction
A Machine Learning Pipeline to predict the potability of water from physical-chemical water quality data, comparing XGBoost and LSTM models (SDG 6).
Dataset : 

Problem :
The access to safe drinking of water is a critical global health issue under SDG 6, and to test the water samples manually for its potability would be time-consuiming and resource heavy. Therefore, this project explores the possibility of machine learning being applied to predict the water potability directly using the physical-chemical measurements to enable a faster and more scalable water quality assestment.

Approach :
EDA: identified missing values (up to 24% in Sulfate) and skewed outliers
Preprocessing: percentile clipping, mean imputation
Models: XGBoost vs LSTM, stratified 80/20 split, train-only scaling

Results :
XGBoost: 65.85% accuracy
LSTM: 64.79% accuracy
Class imbalance identified as main limiter on potable-class recall

Future Implementation : 
To address the class imbalace
To ealuate the model using Precision/Recall/F1 instead of just using accuracy

Tech/Library Used :  Python, Pandas, NumPy, Scikit-learn, XGBoost, TensorFlow/Keras


rFlow/Keras
