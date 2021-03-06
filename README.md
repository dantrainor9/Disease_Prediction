# Disease_Prediction
This project uses data from Kaggle. Source: https://www.kaggle.com/kaushil268/disease-prediction-using-machine-learning. 

The goal for this project is to develop a model that can classify prognoses based on presence or absence of symptoms. Each feature column represents a symptom, each row represents a participant in the study. 132 features were examined with 41 possible prognoses, making this a multiclass classification problem. 

![image](https://user-images.githubusercontent.com/91214731/155022881-b789a203-d85d-4543-9a10-d998f0cb13fd.png)

Abdominal pain shows up in a multitude of prognoses, this is to be expected as this is a common symptom for relatively benign prognoses as well as those that require more serious attention.

![image](https://user-images.githubusercontent.com/91214731/155023149-0b6a6fa7-2c2a-4dd2-b297-e4ec8bbb8cee.png)

Exploratory data analysis found some anomalies in this dataset that may limit generalization in a clinical setting. This graph displays that the only prognosis investigated for which blood in sputum was present was tuberculosis. It is also possible to see blood in sputum in cases of severe pneumonia as well, which indicates that this model hay have issues with producing accurate results when run on unseen data.

![image](https://user-images.githubusercontent.com/91214731/155581297-5af32544-29d8-4553-8af3-a474a6ead73d.png)

Another such anomaly, the only condition in which a patient had bruising is varicose veins. The odds of no other patients having bruising, especially with conditions correlating to bruising being considered, are extremely low.

XGBClassifier and LightGBM both prove to be highly effective with over 99% accuracy. LightGBM was chosen as a production model due to more efficient computation. Model retains accuracy even when run on unseen (test) data. Model has an f1 score of 1, with precision and recall also rated as 1, meaning it can perfectly predict what each prognosis is correctly.

Due to this model's high accuracy as determined with multiple metrics, it it ready for production. However, due to the considerations involving the dataset, incoming data will require significant preparation for this model to perform accurately. In order to build a less work-intensive model, more real-world data is needed for training.
