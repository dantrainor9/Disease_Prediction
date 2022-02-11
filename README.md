# Disease_Prediction
This project uses data from Kaggle. Source:https://www.kaggle.com/kaushil268/disease-prediction-using-machine-learning. 
The goal for this project is to develop a classification model that can predict prognosis based on presence or absence of symptoms. Each column represents a symptom, each row represents a participant in the study. 132 features were examined with 41 possible prognoses, making this a multiclass classification problem. 

Exploratory data analysis found some anomalies in this dataset that may limit generalization in a clinical setting.

![Abdominal_pain_graph](https://user-images.githubusercontent.com/91214731/152226391-1f189cfc-422d-4c1b-89f5-55489a0c157b.png)

Abdominal pain shows up in a multitude of prognoses, this is to be expected as this is a common symptom for relatively benign prognoses as well as those that require more serious attention.

![Blood_in_sputum_graph](https://user-images.githubusercontent.com/91214731/152226708-b23a5867-366f-49f4-966b-d9d7781932fd.png)

An example of the aforementioned anomalies: this graph displays that the only prognosis investigated for which blood in sputum was present was tuberculosis. It is also possible to see blood in sputum in cases of severe pneumonia as well, which indicates that this model hay have issues with producing accurate results when run on unseen data.

XGBClassifier and LightGBM both prove to be highly effective with over 99% accuracy. LightGBM was chosen as a production model due to more efficient computation. Model retains accuracy even when run on unseen (test) data. Model has an f1 score of 1, with precision and recall also rated as 1, meaning it can perfectly predict what each prognosis is correctly.
