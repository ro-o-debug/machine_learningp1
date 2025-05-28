# Machine Learning Sprint 9 Project

### **By Rodrigo Ochoa**

### **Introduction:**
Megaline aims to improve the efficiency of its plan offerings by migrating customers from old plans. This project develops a machine learning model to predict the optimal plan ('Smart' or 'Ultra') for each customer based on their usage behavior. The goal is to provide Megaline with a tool that maximizes customer satisfaction and revenue.

### **Data:**
The project uses a dataset containing customer behavior data, including `calls`, `minutes`, `messages`, `mb_used`, and the target column `is_ultra`, which indicates whether the customer uses the 'Ultra' plan (1) or 'Smart' plan (0).

### **Methodology and Analysis:**

1.  **Initialization and Data Loading:**
    * Necessary libraries were imported: `pandas` for data manipulation, and `sklearn` modules for classification models (`RandomForestClassifier`, `DecisionTreeClassifier`, `LogisticRegression`), metrics (`accuracy_score`), data splitting (`train_test_split`), and sanity checks (`DummyClassifier`).
    * The `users_behavior.csv` file was loaded into a pandas DataFrame for initial inspection.

2.  **Data Preparation:**
    * Data types were checked, and the presence of null values was verified.
    * The dataset was split into three parts: training (60%), validation (20%), and test (20%) to ensure robust model evaluation. The split was performed with `random_state=42` for reproducibility and appropriate `test_size` for partitions.

3.  **Model Training and Evaluation (Validation Set):**
    * Features were separated from the target variable (`is_ultra`) for the training and validation sets.
    * **Random Forest:** Several models were trained by varying the number of estimators (`n_estimators` from 10 to 50 in steps of 10) and maximum depth (`max_depth` from 1 to 10). The model with the highest accuracy on the validation set was selected, achieving approximately **0.8134** accuracy.
    * **Decision Tree:** Models with different maximum depths (`max_depth` from 1 to 10) were evaluated. The best Decision Tree model achieved approximately **0.7963** accuracy on the validation set.
    * **Logistic Regression:** A Logistic Regression model was also trained. This model achieved an accuracy of approximately **0.8134** on the validation set.
    * Among the evaluated models, **RandomForestClassifier** and **LogisticRegression** were the most effective on the validation set.

4.  **Model Quality Check (Test Set):**
    * The best-selected model (RandomForestClassifier, as it tied in validation and is a robust algorithm) was evaluated on the test set.
    * The accuracy on the test set was approximately **0.8196** (around 82%).

5.  **Sanity Check:**
    * The final model's accuracy was compared with a `DummyClassifier` (a baseline model that predicts the most frequent class) on the test set.
    * The `DummyClassifier`'s accuracy was approximately **0.6967** (around 70%).
    * The developed model significantly outperforms the baseline model, confirming its validity and usefulness.

### **Key Results and Conclusions:**

* The developed machine learning model, particularly the **RandomForestClassifier**, is capable of predicting the optimal plan ('Smart' or 'Ultra') for Megaline customers with high accuracy (approximately 82%).
* The model's accuracy considerably surpasses that of a random or baseline model (70%), indicating its ability to accurately identify user behavior patterns.
* Implementing this model could enable Megaline to automate plan recommendations, leading to more efficient resource allocation, a potential reduction in customer churn, and increased revenue.

### **Technologies Used:**
* `pandas`
* `sklearn.ensemble.RandomForestClassifier`
* `sklearn.tree.DecisionTreeClassifier`
* `sklearn.metrics.accuracy_score`
* `sklearn.model_selection.train_test_split`
* `sklearn.dummy.DummyClassifier`
* `sklearn.linear_model.LogisticRegression`
