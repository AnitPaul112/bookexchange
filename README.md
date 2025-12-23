# 📚 Book Rating Prediction & Bestseller Analysis

This project explores a book dataset to understand patterns behind **bestseller status** and to **predict book ratings** using machine learning.

The main goal is to apply **EDA, feature engineering, and regression models** and analyze their performance honestly.

---

## 📊 Dataset

- Source: Kaggle  
- Dataset name: *The Most Popular Books for Exchanging*
- Total records: **990 books**
- Features include:
  - Title, Author, Genre, Language
  - Publication Year, Page Count
  - Tags, Description
  - Movie Adaptation info
  - Average Rating
  - Bestseller Status

---

## 🔍 Exploratory Data Analysis (EDA)

Key observations from EDA:

- Ratings mostly lie between **3.8 – 4.5**
- `bestseller_status` is **highly imbalanced**  
  - ~99.6% True  
  - ~0.4% False  
- Some missing values:
  - `awards`
  - `movie_release_year`
- Presence of outliers in `publicationYear` (e.g., -750)

Because of extreme class imbalance, **bestseller classification is unreliable**.

---

## ❌ Bestseller Classification (Not Suitable)

- Tried Random Forest classification
- Very high accuracy (~99%) but:
  - Balanced Accuracy = **0.5**
  - Model predicts only one class

### Conclusion:
> Bestseller prediction is not suitable due to extreme class imbalance in the dataset.

---

## ⭐ Rating Prediction (Regression)

### Target Variable
- `rating_average`

### Models Used
1. **Linear Regression**
2. **Random Forest Regressor**
3. **Random Forest + TF-IDF (tags)**
4. **LightGBM Regressor**

---

## 📈 Model Performance Summary

| Model | R² | MAE | RMSE |
|-----|----|----|-----|
| Linear Regression | -0.71 | 0.22 | 0.30 |
| Random Forest | 0.25 | 0.15 | 0.20 |
| RF + TF-IDF (tags) | **0.30** | **0.15** | **0.196** |
| LightGBM | 0.04 | 0.18 | 0.23 |

---

## 🏆 Best Model

✅ **Random Forest with TF-IDF features from `tags`**

Why?
- Lowest error (MAE & RMSE)
- More stable on small dataset
- Boosting models underperformed due to:
  - Small data size
  - High-dimensional sparse text features

---

## 🧠 Key Learnings

- High accuracy does not always mean a good model
- Rating prediction is a **hard problem** due to subjectivity
- Feature engineering (text features) improves performance
- Cross-validation gives more realistic performance estimates
- More complex models do not always perform better

---

## ⚠️ Important Note on R²

Achieving **80%+ R² is unrealistic** for this dataset because:
- Ratings are subjective
- No user-level or interaction data
- Limited dataset size

An R² of **0.30–0.40** is acceptable for this type of problem.

---

## 🛠️ Technologies Used

- Python
- Pandas, NumPy
- Scikit-learn
- Random Forest
- LightGBM
- TF-IDF (Text Feature Extraction)
- Matplotlib, Seaborn

---

## ✅ Final Conclusion

This project demonstrates a complete machine learning workflow:
- Data cleaning & EDA
- Model comparison
- Feature engineering
- Honest evaluation & limitations

The final model provides **reasonable predictions** with low error, while also highlighting real-world ML challenges.

---

## 📌 Author

**Anit Paul**  
Machine Learning / Data Science Practice Project
