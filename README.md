Titanic Survival Prediction - Machine Learning Project
========================================================

Project Overview
-----------------
This project applies a supervised machine learning algorithm to predict whether a Titanic passenger survived, using historical passenger data from Kaggle. It was completed as part of the Artificial Intelligence (Machine Learning) coursework at the University of Energy and Natural Resources (UENR).

---

Problem Statement
-------------------
Given information about a Titanic passenger (such as age, sex, fare paid, and passenger class), predict whether that passenger survived (1) or did not survive (0). This is a binary classification problem.

---

Dataset Description
---------------------
- **Source:** Kaggle - Titanic: Machine Learning from Disaster (https://www.kaggle.com/c/titanic)
- **Size:** 792 passenger records, 16 columns (after preprocessing)
- **Target variable:** Survived (0 = did not survive, 1 = survived)
- **Key features:** Sex, Age, Fare, Pclass_1/2/3, Family_size, Title_1-4, Emb_1/2/3

---

Data Preprocessing
--------------------
- Removed the auto-generated index column
- Removed PassengerId (unique identifier, not predictive)
- Confirmed no missing values remained (dataset was pre-normalized and pre-encoded)
- Split data into a feature matrix (X, 14 columns) and target vector (y = Survived)

---

Exploratory Data Analysis
----------------------------
Basic checks were performed using .info(), .describe(), and .isnull().sum() to understand data types, distributions, and confirm data quality before modeling.

---

Feature Engineering
----------------------
The dataset used was already engineered prior to sourcing, including:
- One-hot encoded passenger class (Pclass_1, Pclass_2, Pclass_3)
- One-hot encoded embarkation port (Emb_1, Emb_2, Emb_3)
- Titles extracted from passenger names (Title_1 to Title_4)
- A derived Family_size feature combining siblings/spouses and parents/children aboard

---

Model Selection
------------------
A Random Forest Classifier was chosen for this task due to its strong performance on tabular data and its resistance to overfitting compared to a single decision tree.

---

Model Training
-----------------
- Data split: 80% training / 20% testing (random_state=42 for reproducibility)
- Model trained using scikit-learn's RandomForestClassifier with default settings (100 trees, Gini criterion)

---

Hyperparameter Tuning
-------------------------
Default hyperparameters were used for this version of the model. Hyperparameter tuning (e.g. via GridSearchCV) is noted as a potential future improvement.

---

Model Evaluation
--------------------
The model was evaluated on the unseen 20% test set using accuracy, precision, recall, and F1-score, along with a confusion matrix.

---

Final Model
---------------
Random Forest Classifier (n_estimators=100, criterion='gini', random_state=42)

---

Prediction Generation
-------------------------
Predictions were generated using model.predict(X_test) on the held-out test set.

---

Prediction File Description
-------------------------------
No separate prediction submission file was generated for this project, since evaluation was performed directly within the notebook on the train/test split.

---

Submission Format
---------------------
Not applicable - this project was submitted as a Jupyter Notebook, dataset, chart, and written report rather than a Kaggle competition submission file.

---

Project/Folder Structure
----------------------------
```
Titanic_ML-_Project_UENR/
├── README.md
├── Titanic_ML_Project.ipynb    (Full code: cleaning, training, evaluation)
├── train_data.csv              (Dataset used for training/testing)
└── feature_importance.png      (Feature importance chart)
```

---

Requirements/Dependencies
-----------------------------
- Python 3
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- Jupyter Notebook

---

How to Run the Project
--------------------------
1. Clone or download this repository
2. Ensure all dependencies above are installed (via Anaconda or pip install)
3. Place train_data.csv in the same folder as the notebook
4. Open Titanic_ML_Project.ipynb in Jupyter Notebook
5. Run all cells from top to bottom

---

Results
----------
- **Accuracy:** 81.1%
- **Top predictive features:** Fare, Age, Sex

---

Conclusion
-------------
The Random Forest model predicted Titanic passenger survival with 81.1% accuracy, confirming that fare, age, and sex were the strongest predictors - consistent with historical accounts of the disaster's "women and children first" evacuation policy.

---

Limitations
--------------
- Accuracy is not perfect; factors like exact cabin location or chance during evacuation are not captured in the dataset
- Default hyperparameters were used rather than a tuned configuration
- Only one algorithm (Random Forest) was tested, without comparison to alternatives

---

Future Improvements
-----------------------
- Hyperparameter tuning using GridSearchCV or RandomizedSearchCV
- Comparing performance against other algorithms (Logistic Regression, Gradient Boosting, SVM)
- Applying cross-validation for a more robust accuracy estimate

---

Author/Team Members
-----------------------

| Name | Index Number | GitHub Repository |
|------|--------------|--------------------|
| Evans Sarpong | UEB3517723 | https://github.com/evansshowmax/Titanic_ML-_Project_UENR |
| Boah kenneth | UEB3506023 | https://github.com/BoahKen/Titanic_Ml_project_uenr |

---

References
-------------
Kaggle. Titanic - Machine Learning from Disaster. Retrieved from https://www.kaggle.com/c/titanic
