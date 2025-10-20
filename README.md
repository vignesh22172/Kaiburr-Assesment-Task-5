# Kaiburr-Assesment-Task-5
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
- Dataset loaded from `rows.csv` (Consumer Complaint Database).
- Only relevant columns used: `Product` and `Consumer complaint narrative`.
- Missing values removed.

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
- TF-IDF Vectorization (`max_features=5000`) used to convert text into numerical form.

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
| Linear SVM | **88.2%** ✅ | Best performer overall |

**✅ Best Model: Linear SVM**  
Linear SVM achieved the highest accuracy and produced the most balanced confusion matrix across all four categories.

---

## 📉 Visual Results

### 🔹 Model Accuracy Comparison
![Logistic Regression CM](screenshots/confusion_matrix_logreg.png)
<img width="814" height="651" alt="Screenshot 2025-10-20 180623" src="https://github.com/user-attachments/assets/340c3a2d-189a-4b44-a2af-0c7e9f3e1771" />


