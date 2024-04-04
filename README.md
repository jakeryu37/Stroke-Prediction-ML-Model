# Stroke-Prediction-ML-Model

### 프로젝트 주제
환자들의 뇌졸중을 예측하는 이진 분류 모델 학습

### 프로젝트 목적
뇌졸중 고위험 환자들을 구별하여 추가적인 검사를 통해 조기에 정밀치료 및 예방

### 데이터 설명
train_strokes.csv - 43000 환자의 임상 정보
* 뇌졸중을 경험하지 않은 환자 (98.2%), 뇌졸중을 경험한 환자는 783명 (1.8%) 으로 불균형한 데이터
> id, gender, age, hypertension, heart_disease, ever_married, work_type, Residence_type, avg_glucode_level, bmi, smoking_status, stroke

### 프로젝트 정리
뇌졸중 경험 유무를 target variable로 설정 후 다양한 모델들을 사용하여 GridSearchCV를 통해 학습 및 결과 확인
* 불균형한 데이터 분포 문제를 해결하기 위해 SMOTE과 SMOTEENN resampling 방법들을 사용
> models: LogisticRegression, DecisionTreeClassifier, RandomForestClassifier, XGBClassifier, AdaboostClassifier, GaussianNB

![image](https://github.com/jakeryu37/Stroke-Prediction-ML-Model/assets/106287761/d71709e7-e8ed-4bf0-bf79-49d201e5c5f5)
< 이미지 출처: [A Comparison of Undersampling, Oversampling, and SMOTE Methods for Dealing with Imbalanced Classification in Educational Data Mining](https://www.mdpi.com/2078-2489/14/1/54) >
<br><br>

### 프로젝트 결과

* AUC 점수, 재현율(Recall), F1 점수, 정확도(Precision)를 지표로 사용하여 모델의 성능을 비교
* 뇌졸중 고위험군인 환자를 예측하는 것이 주목적이므로 재현율(Recall) 점수에 집중
* resampling을 진행한 모델의 결과 향상

| Model                        | AUC Score | Recall | F1 Score | Precision |
|------------------------------|-----------|--------|----------|-----------|
| LogisticRegression (SMOTEENN)|   0.8374  | 0.7565 |  0.4740  |   0.5233  |
| LogisticRegression (SMOTE)   |   0.8356  | 0.7554 |  0.4729  |   0.5230  |
| GaussianNB (SMOTE)           |   0.8031  | 0.7384 |  0.4543  |   0.5199  |
| GaussianNB (SMOTEENN)        |   0.8064  | 0.7365 |  0.4632  |   0.5206  |
| DecisionTree (SMOTE)         |   0.6578  | 0.6342 |  0.5459  |   0.5351  |
| GaussianNB                   |   0.8083  | 0.6183 |  0.5321  |   0.5273  |
| DecisionTree (SMOTEENN)      |   0.5785  | 0.5566 |  0.5224  |   0.5186  |
| AdaBoost (SMOTE)             |   0.7825  | 0.5423 |  0.5282  |   0.5227  |
| RandomForest (SMOTEENN)      |   0.7827  | 0.5406 |  0.5218  |   0.5176  |
| AdaBoost (SMOTEENN)          |   0.8003  | 0.5344 |  0.5291  |   0.5257  |
| XGBoost (SMOTEENN)           |   0.7761  | 0.5280 |  0.5146  |   0.5124  |
| XGBoost (SMOTE)              |   0.7655  | 0.5141 |  0.5122  |   0.5110  |
| RandomForest (SMOTE)         |   0.7652  | 0.5125 |  0.5068  |   0.5063  |
| AdaBoost                     |   0.8372  | 0.5000 |  0.4954  |   0.4910  |
| DecisionTree                 |   0.8329  | 0.5000 |  0.4954  |   0.4910  |
| RandomForest                 |   0.8349  | 0.5000 |  0.4954  |   0.4910  |
| LogisticRegression           |   0.8371  | 0.5000 |  0.4954  |   0.4910  |
| XGBoost                      |   0.8380  | 0.5000 |  0.4954  |   0.4910  |

<br>

---
<br>

### Project Topic
Training a binary classification model to predict strokes in patients

### Project Objective
Differentiating high-risk patients for stroke to enable early treatment and prevention through additional testing

### Data Description
train_strokes.csv - Clinical information of 43,000 patients
* Imbalanced data with 98.2% of patients not experiencing a stroke and 1.8% having experienced a stroke.
> id, gender, age, hypertension, heart_disease, ever_married, work_type, Residence_type, avg_glucose_level, bmi, smoking_status, stroke

### Project Summary
Setting stroke experience as the target variable, various models were trained using GridSearchCV
* Resampling methods such as SMOTE and SMOTEENN were used to adjust the imbalanced data distribution
> Models: Logistic Regression, Decision Tree Classifier, RandomForest Classifier, XGB Classifier, AdaBoost Classifier, GaussianNB

![image](https://github.com/jakeryu37/Stroke-Prediction-ML-Model/assets/106287761/d71709e7-e8ed-4bf0-bf79-49d201e5c5f5)
< Image Source: [A Comparison of Undersampling, Oversampling, and SMOTE Methods for Dealing with Imbalanced Classification in Educational Data Mining](https://www.mdpi.com/2078-2489/14/1/54) >
<br><br>

### Project Results

* Compared model performance using AUC score, Recall, F1 score, and Precision as metrics.
* Focused on the Recall score as the main objective for the purpose of the model is to predict high-risk stroke patients(True Positives).
* Shown improved results with resampling techniques applied to the models.

| Model                        | AUC Score | Recall | F1 Score | Precision |
|------------------------------|-----------|--------|----------|-----------|
| LogisticRegression (SMOTEENN)|   0.8374  | 0.7565 |  0.4740  |   0.5233  |
| LogisticRegression (SMOTE)   |   0.8356  | 0.7554 |  0.4729  |   0.5230  |
| GaussianNB (SMOTE)           |   0.8031  | 0.7384 |  0.4543  |   0.5199  |
| GaussianNB (SMOTEENN)        |   0.8064  | 0.7365 |  0.4632  |   0.5206  |
| DecisionTree (SMOTE)         |   0.6578  | 0.6342 |  0.5459  |   0.5351  |
| GaussianNB                   |   0.8083  | 0.6183 |  0.5321  |   0.5273  |
| DecisionTree (SMOTEENN)      |   0.5785  | 0.5566 |  0.5224  |   0.5186  |
| AdaBoost (SMOTE)             |   0.7825  | 0.5423 |  0.5282  |   0.5227  |
| RandomForest (SMOTEENN)      |   0.7827  | 0.5406 |  0.5218  |   0.5176  |
| AdaBoost (SMOTEENN)          |   0.8003  | 0.5344 |  0.5291  |   0.5257  |
| XGBoost (SMOTEENN)           |   0.7761  | 0.5280 |  0.5146  |   0.5124  |
| XGBoost (SMOTE)              |   0.7655  | 0.5141 |  0.5122  |   0.5110  |
| RandomForest (SMOTE)         |   0.7652  | 0.5125 |  0.5068  |   0.5063  |
| AdaBoost                     |   0.8372  | 0.5000 |  0.4954  |   0.4910  |
| DecisionTree                 |   0.8329  | 0.5000 |  0.4954  |   0.4910  |
| RandomForest                 |   0.8349  | 0.5000 |  0.4954  |   0.4910  |
| LogisticRegression           |   0.8371  | 0.5000 |  0.4954  |   0.4910  |
| XGBoost                      |   0.8380  | 0.5000 |  0.4954  |   0.4910  |
