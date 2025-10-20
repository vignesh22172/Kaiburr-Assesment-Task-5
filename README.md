# 🧠 Consumer Complaint Text Classification

## 📘 Overview
This project performs **text classification** on the [Consumer Complaint Database](https://catalog.data.gov/dataset/consumer-complaint-database) using machine learning.  
The goal is to classify consumer complaints into the following **four categories**:

| Label | Product Category |
|--------|------------------|
| 0 | Credit reporting, repair, or other |
| 1 | Debt collection |
| 2 | Consumer Loan |
| 3 | Mortgage |

---

## 🎯 Objective
To build and evaluate multiple machine learning models that can automatically predict the type of financial product based on a customer complaint description.

---

## ⚙️ Steps Performed

### 1. Data Loading & Cleaning
- Dataset loaded from `rows.csv` (Consumer Complaint Database)  
- Only relevant columns used: `Product` and `Consumer complaint narrative`  
- Missing values removed

### 2. Data Filtering
Only the following categories were kept:
- Credit reporting, repair, or other  
- Debt collection  
- Consumer Loan  
- Mortgage

### 3. Text Preprocessing
- Converted text to lowercase  
- Removed punctuation and non-alphabetic characters  
- Removed stopwords using `sklearn.feature_extraction.text.ENGLISH_STOP_WORDS` (works offline)  
- Generated cleaned complaint text column

### 4. Feature Engineering
- TF-IDF Vectorization (`max_features=5000`) used to convert text into numerical form

### 5. Model Selection
Three machine learning models were trained and compared:
1. **Logistic Regression**  
2. **Multinomial Naive Bayes**  
3. **Linear SVM**

### 6. Model Evaluation
Each model was evaluated using:
- **Accuracy**  
- **Classification Report** (Precision, Recall, F1-Score)  
- **Confusion Matrix**

---

## 📊 Results & Comparison

| Model | Accuracy | Key Observation |
|--------|-----------|----------------|
| Logistic Regression | **87.6%** | Strong baseline performance |
| Naive Bayes | 83.4% | Slightly lower accuracy, fast training |
| Linear SVM | **88.2% ✅** | Best performer overall |

**✅ Best Model: Linear SVM**  
Linear SVM achieved the highest accuracy and produced the most balanced confusion matrix across all four categories.

---

## 📉 Visual Results

### 🔹 Confusion Matrix — Logistic Regression
![Confusion Matrix — Logistic Regression](https://github.com/user-attachments/assets/340c3a2d-189a-4b44-a2af-0c7e9f3e1771)

### 🔹 Confusion Matrix — Naive Bayes
![Confusion Matrix — Naive Bayes](https://github.com/user-attachments/assets/27aba1bb-6876-489b-bf88-fbd3836a85b5)

### 🔹 Confusion Matrix — Linear SVM (Best Model)
![Confusion Matrix — Linear SVM](https://github.com/user-attachments/assets/1f802a0d-43c1-42a1-bc0a-e480c5722443)

### 🔹 Model Performance Comparison
![Model Performance Comparison](https://github.com/user-attachments/assets/68301001-e73f-4df0-9568-960e71bd33c0)

### 🔹 Final Output Examples
![Final Output 1](https://github.com/user-attachments/assets/7743d8f0-3dd8-412c-a941-26c32f6067df)
![Final Output 2](https://github.com/user-attachments/assets/1d7a3d91-1271-4bef-92d7-b6f40ec037c6)

---

## 🏁 Summary of Model Comparison

| Model | Accuracy | Comments |
|--------|-----------|-----------|
| Logistic Regression | **87.6%** | Strong and stable baseline |
| Naive Bayes | **83.4%** | Simple and efficient, but lower recall |
| Linear SVM | **88.2% ✅** | Best performing model overall |

**✅ Best Model:** Linear SVM  
**Reason:** Achieved highest accuracy and best class balance across categories.

---

## 🧩 Sample Predictions

| Complaint Text | Predicted Product |
|----------------|------------------|
| "The bank closed my account without any reason." | Consumer Loan |
| "Debt collectors are calling me repeatedly about a loan I don't owe." | Debt collection |
| "My mortgage payment was not processed on time." | Mortgage |
| "My credit report contains false information." | Credit reporting, repair, or other |

---

## 💡 Insights
- Text preprocessing significantly improved accuracy  
- TF-IDF vectorization captured key complaint terms effectively  
- Linear SVM generalized best on unseen data  
- Naive Bayes was fast but less accurate  
- Logistic Regression provided interpretable feature importance

---

## 🧰 Tech Stack
- Python 3.x  
- Pandas, NumPy  
- Scikit-learn  
- Matplotlib  
- Kaggle (for dataset)

---
