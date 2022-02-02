# Disease_Prediction
This project uses data from Kaggle. Source:https://www.kaggle.com/kaushil268/disease-prediction-using-machine-learning. 
The goal for this project is to develop a classification model that can predict prognosis based on presence or absence of symptoms. Each column represents a symptom, each row represents a participant in the study. 132 features were examined with 41 possible prognoses, making this a multiclass classification problem. 

Exploratory data analysis found some anomalies in this dataset that may limit generalization in a clinical setting.

![Abdominal_pain_graph](https://user-images.githubusercontent.com/91214731/152226391-1f189cfc-422d-4c1b-89f5-55489a0c157b.png)
Abdominal pain shows up in a multitude of prognoses, this is to be expected as this is a common symptom for relatively benign prognoses as well as those that require more serious attention.

XGBClassifier and LightGBM both prove to be highly effective with over 99% accuracy. LightGBM was chosen as a production model due to more efficient computation. 
