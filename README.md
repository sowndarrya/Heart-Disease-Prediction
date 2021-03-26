# Heart Disease Prediction
# Dataset Description:
This dataset was taken from kaggle.
*Columns:
age: The person's age in years
sex: The person's sex (1 = male, 0 = female)
cp: The chest pain experienced (Value 1: typical angina, Value 2: atypical angina, Value 3: non-anginal pain, Value 4: asymptomatic)
trestbps: The person's resting blood pressure (mm Hg on admission to the hospital)
chol: The person's cholesterol measurement in mg/dl
fbs: The person's fasting blood sugar (> 120 mg/dl, 1 = true; 0 = false)
restecg: Resting electrocardiographic measurement (0 = normal, 1 = having ST-T wave abnormality, 2 = showing probable or definite left ventricular hypertrophy by Estes' criteria)
thalach: The person's maximum heart rate achieved
exang: Exercise induced angina (1 = yes; 0 = no)
oldpeak: ST depression induced by exercise relative to rest ('ST' relates to positions on the ECG plot.)
slope: the slope of the peak exercise ST segment (Value 1: upsloping, Value 2: flat, Value 3: downsloping)
ca: The number of major vessels (0-3)
thal: A blood disorder called thalassemia (3 = normal; 6 = fixed defect; 7 = reversable defect) ( values 1,2,3 in the dataset)
target: Heart disease (0 = no, 1 = yes)

# Project Overview
* This database contains 76 attributes, but all published experiments refer to using a subset of 14 of them. By performing the necessary Exploratory Data Analysis and cleaning the data, models are built. Logistic, Decision Tree, Random Forest are built with necessary hyperparameters which are choosen through GridSearchCv and the model is evaluvated
# EDA
* Records- 93, 139, 164, 165 and 252 have ca=4 which is incorrect. In the original Cleveland dataset they are NaNs so they should be removed and the records
  49 and 282 have thal = 0, also incorrect. They are also NaNs in the original dataset so they are also removed.
  ![hd pairplot](https://user-images.githubusercontent.com/25876186/112320795-5d874180-8cd5-11eb-9846-ca61cd665940.png)

* At age 35, we can see a unique inference where it has both the targets at equal level
* For cp-2 Atypical angina, we can see that both male and female ages are almose equal
* we can see a negative corr between thalach (max heart rate and age)
* when comp with the target the count is high for those who have heart disease and they also have exang= exercise induced angina
* Patients who have Heart Disease have downsloping (ST Depression slope in ECG)
* 0  (MAJOR VESSELS) is high wrt to those who have HD
* Those who have HD HAVE had Thalessima as shown from the graph.
* Male have high count compared to female in having HD
* Type 2 cp count is high for those who have HD
# Models
* Logistic Regression f1 score - 0.89
* Decision Tree f1 score - 0.80
* Random Forest f1 score - 0.85
* Decision Tree tuned f1 score - 0.84
* Random Forest tuned f1 score - 0.86
  models were built and analysed.
 # Evaluvation Metric
   F1- Score is choosen as the evaluvation metric for this model
 # Conclusion
 * By comparing all the f1 scores and also checking the percentage of overfitting in each model, we can say that logistic regression is performing well
 * ![Screenshot 2021-03-25 012547](https://user-images.githubusercontent.com/25876186/112375279-1dda4d00-8d09-11eb-9069-8cb643bf8adf.png)
