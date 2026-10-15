# Financess — Financial Status Prediction Using Machine Learning

## 📌 Project Overview

**Financess** is a machine learning project that analyzes financial survey data to predict whether an individual's financial situation will **improve, stay the same, or worsen**.

The project applies data cleaning, exploratory data analysis (EDA), statistical hypothesis testing, and supervised machine learning to identify patterns in financial well-being and develop a model that predicts financial outcomes.

The project demonstrates how data science can transform raw financial data into meaningful insights and predictive solutions.

## 🎯 Objectives

- Clean and preprocess financial survey data.
- Explore relationships between demographic characteristics and financial status.
- Perform statistical hypothesis testing to investigate associations between variables.
- Train and evaluate multiple machine learning classification models.
- Identify a suitable model for predicting financial status.
- Save the trained model for potential reuse in a prediction application.

## 📊 Dataset

The project uses financial survey data containing demographic, household, and financial characteristics.

The target variable is `financial_status`, which contains three classes:

- **Improved** — The respondent's financial situation improved.
- **Stayed the same** — The respondent's financial situation remained unchanged.
- **Worsened** — The respondent's financial situation deteriorated.

Features explored in the notebook include:

- Age
- Education level
- Sex
- County
- Location type
- Household size
- Monthly income
- Disability status
- Financial product usage (`prodsum1`)

*Note: The original dataset is not included in this repository. Add its source and access instructions here if you are permitted to share them.*

## 🛠️ Technologies Used

- **Python** — Main programming language
- **Pandas & NumPy** — Data manipulation and numerical operations
- **Matplotlib & Seaborn** — Data visualization
- **SciPy** — Statistical hypothesis testing
- **Scikit-learn** — Data preprocessing, model training, and evaluation
- **Joblib** — Saving and loading trained machine learning models
- **Jupyter Notebook** — Interactive analysis and experimentation

## 🔍 Project Workflow

### 1. Data Cleaning and Preprocessing

The notebook prepares the dataset for analysis and machine learning by:

- Removing duplicate records.
- Standardizing inconsistent categorical values.
- Cleaning education and marital status categories.
- Removing invalid or non-informative survey responses.
- Handling missing values.
- Encoding categorical variables.
- Scaling numerical features where appropriate.

### 2. Exploratory Data Analysis (EDA)

EDA was conducted to understand the distribution of financial status and explore its relationship with demographic and financial characteristics.

Visualizations examined:

- Financial status distribution.
- Financial status by age.
- Financial status by education level.
- Financial status by disability status.
- Monthly income and savings-related characteristics.

### 3. Statistical Hypothesis Testing

Statistical tests were used to investigate relationships and differences in the dataset.

- **Chi-square test of independence:** Examined associations between categorical variables and financial status.
- **Kruskal–Wallis test:** Examined differences in the distributions of numerical variables across financial-status groups.

These tests helped identify variables that may be associated with financial outcomes.

### 4. Model Development

The project trained and evaluated several supervised machine learning classifiers, including:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Random Forest
- Gradient Boosting

The models were evaluated using classification reports containing precision, recall, F1-score, and accuracy.

## 📈 Model Evaluation

The following accuracy results were observed in the notebook:

| Model | Accuracy |
|---|---:|
| Logistic Regression | 57% |
| K-Nearest Neighbors (KNN) | 46% |
| Random Forest | 56% |
| Gradient Boosting | 57% |

**Best-performing models:** Logistic Regression and Gradient Boosting, both achieving approximately 57% accuracy in the recorded evaluation.

Accuracy alone does not tell the whole story. The classification reports show that the models performed better at predicting the *Worsened* class than the *Improved* and *Stayed the same* classes. This suggests that class imbalance and performance on minority classes need further investigation.

The results are an initial baseline rather than evidence of a production-ready predictive system.

## 💾 Model Persistence

The notebook demonstrates saving and loading a trained model using Joblib.

The saved model package contains the trained estimator and label encoder, allowing the model to be reloaded for further experiments or integration into a prediction application.

Example:

```python
import joblib

saved_model = joblib.load("financial_health_best_model.pkl")

model = saved_model["model"]
label_encoder = saved_model["label_encoder"]
```

The example assumes the saved model file is available in the current working directory.

## 🚀 Getting Started

### Prerequisites

Install Python and the required libraries.

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn joblib jupyter
```

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/samuel-mwai/Financess.git
   ```

2. Navigate to the project directory:

   ```bash
   cd Financess
   ```

3. Install the dependencies using the command above.

4. Launch Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open the Financess ML project notebook and run the cells in sequence.

6. Make the dataset available at the path expected by the notebook before running the analysis.

Replace `YOUR-USERNAME` and the repository name with your actual GitHub details.

## 🔮 Future Improvements

Potential next steps include:

- Addressing class imbalance using appropriate techniques.
- Improving recall and F1-scores for the *Improved* and *Stayed the same* classes.
- Using stratified cross-validation and hyperparameter tuning.
- Comparing additional classification algorithms.
- Evaluating the model with a confusion matrix and macro-averaged metrics.
- Preventing data leakage by fitting preprocessing steps only on training data.
- Building a Streamlit dashboard for interactive financial-status predictions.
- Documenting the dataset source, limitations, and reproducibility requirements.

## ⚠️ Limitations

- The current models achieve moderate accuracy and require further improvement.
- Performance varies across the three financial-status classes.
- Predictions depend on the quality and representativeness of the survey data.
- Statistical associations do not necessarily imply causation.
- Predictions should not be treated as definitive financial advice.

## 👨‍💻 Author

**Samuel Mwai**

Data Science & Analytics | Machine Learning | Data Analysis | Data Visualization

GitHub:(https://github.com/samuel-mwai)

## 📄 License

A license has not yet been specified. Add an appropriate license before allowing others to reuse or redistribute the project.

---

*Financess explores how machine learning and statistical analysis can be applied to financial survey data to better understand and predict financial outcomes.*
