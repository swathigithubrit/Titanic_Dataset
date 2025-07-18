# Titanic_Dataset
This project involves preprocessing the Titanic dataset to predict passenger survival using features such as age, class, sex, and travel status through data cleaning, feature engineering, encoding, and scaling techniques in preparation for machine learning modeling.


Titanic Dataset - Data Preprocessing, Feature Engineering, and Scaling

This project involves cleaning and preparing the Titanic Dataset for machine learning using Python libraries like `pandas`, `NumPy`, and `scikit-learn`. The dataset is commonly used for classification tasks — predicting whether a passenger survived the Titanic disaster based on features like age, gender, ticket class, and more.

---

🧩 Problem Statement

The goal of this project is to **prepare the Titanic dataset for a machine learning model** by performing the following tasks:

* Handle missing values.
* Engineer new features to improve model accuracy.
* Remove irrelevant or redundant columns.
* Encode categorical variables using one-hot encoding.
* Apply feature scaling using MinMaxScaler and StandardScaler.

This project does not train a model, but prepares the dataset for any classification algorithm such as Logistic Regression, Decision Tree, or Random Forest.

📂 Dataset Information

The dataset contains the following key columns:

* `Survived`: Target variable (0 = No, 1 = Yes)
* `Pclass`: Passenger class (1 = 1st, 2 = 2nd, 3 = 3rd)
* `Sex`: Gender of the passenger
* `Age`: Age of the passenger
* `SibSp`: Number of siblings/spouses aboard
* `Parch`: Number of parents/children aboard
* `Fare`: Ticket fare
* `Embarked`: Port of Embarkation (C = Cherbourg, Q = Queenstown, S = Southampton)
* `Cabin`, `Name`, `Ticket`: Not used in modeling


What I Did (Step-by-Step Breakdown)

1. Loaded the Dataset using `pandas`.
2. Explored the data using `head()`, `describe()`, and `info()` functions.
3. Created a new feature `Travelalone` to indicate whether a passenger was traveling alone.
4. Dropped unnecessary columns that were not helpful for modeling (`PassengerId`, `Name`, `SibSp`, `Parch`, `Ticket`, `Cabin`).
5. Handled missing values by filling missing `Age` values with the median age.
6. Encoded categorical columns like `Sex`, `Embarked`, and `Pclass` using one-hot encoding.
7. Split the dataset into features `X` and target `y` (`Survived`).
8. Applied Feature Scaling:

   * Used `MinMaxScaler` to scale features between 0 and 1.
   * Used `StandardScaler` to standardize features to mean=0 and std=1.

---

## 📌 Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn

🧠 Concepts Practiced

* Data Cleaning
* Feature Engineering
* One-Hot Encoding
* Feature Scaling
* Exploratory Data Analysis (EDA)


| **Model Type**                   | **Needs Scaling?** | **Why**                                                                                                                                                                                                |
| -------------------------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Decision Tree**                | ❌ No               | Decision Trees split data at certain feature values (like “Age ≤ 18”). They do not use distances or gradient calculations. Scaling doesn't affect the splits or performance.                           |
| **Random Forest**                | ❌ No               | Random Forest is an ensemble of Decision Trees. Since each tree operates on splits, scaling is again not required or beneficial.                                                                       |
| **XGBoost / LightGBM**           | ❌ No               | These are advanced gradient boosting algorithms based on decision trees. Like simple trees, they find optimal split points and do not rely on feature magnitudes.                                      |
| **Logistic Regression**          | ✅ Yes              | Logistic Regression uses gradient descent to minimize a cost function. If features have vastly different scales, convergence becomes slow or unstable. Scaling helps it learn efficiently.             |
| **K-Nearest Neighbors (KNN)**    | ✅ Yes              | KNN calculates the distance (e.g., Euclidean) between data points. If one feature is on a larger scale (like Fare), it will dominate the distance metric, leading to biased predictions.               |
| **Support Vector Machine (SVM)** | ✅ Yes              | SVM works by maximizing the margin between classes using a hyperplane. The position of the hyperplane is highly sensitive to the magnitude of feature values. Scaling ensures fair margin computation. |
| **Neural Networks**              | ✅ Yes              | Neural networks optimize weights via gradient descent. If input features vary in scale, gradients can explode or vanish. Scaling ensures better convergence and more stable learning.                  |


