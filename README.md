# Disease_Prediction
This project uses data from Kaggle. Source:https://www.kaggle.com/kaushil268/disease-prediction-using-machine-learning. 
The goal for this project is to develop a classification model that can predict prognosis based on presence or absence of symptoms. Each column represents a symptom, each row represents a participant in the study. 132 features were examined with 41 possible prognoses, making this a multiclass classification problem. 

Exploratory data analysis found some anomalies in this dataset that may limit generalization in a clinical setting.

![image](https://user-images.githubusercontent.com/91214731/155022881-b789a203-d85d-4543-9a10-d998f0cb13fd.png)

Abdominal pain shows up in a multitude of prognoses, this is to be expected as this is a common symptom for relatively benign prognoses as well as those that require more serious attention.

![image](https://user-images.githubusercontent.com/91214731/155023149-0b6a6fa7-2c2a-4dd2-b297-e4ec8bbb8cee.png)

An example of the aforementioned anomalies: this graph displays that the only prognosis investigated for which blood in sputum was present was tuberculosis. It is also possible to see blood in sputum in cases of severe pneumonia as well, which indicates that this model hay have issues with producing accurate results when run on unseen data.

XGBClassifier and LightGBM both prove to be highly effective with over 99% accuracy. LightGBM was chosen as a production model due to more efficient computation. Model retains accuracy even when run on unseen (test) data. Model has an f1 score of 1, with precision and recall also rated as 1, meaning it can perfectly predict what each prognosis is correctly.
