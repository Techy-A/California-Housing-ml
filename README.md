# Housing Price Prediction 🏡

This project focuses on predicting **California housing prices** using machine learning techniques.  
The dataset contains information such as population, median income, and location, which are used to predict the median house value.

## 📂 Project Structure
- `Housing.ipynb` – Jupyter notebook containing data exploration, preprocessing, and model training.

## 📊 Dataset
The dataset comes from the **California Housing dataset** (available via `sklearn.datasets` or external source).  
It includes features like:
- `longitude`, `latitude`
- `housing_median_age`
- `total_rooms`, `total_bedrooms`
- `population`, `households`
- `median_income`
- `median_house_value` (target)

## ⚙️ Technologies Used
- **Python**
- **NumPy** & **Pandas** – data manipulation
- **Matplotlib** – visualization
- **Scikit-learn** – model building & evaluation

## 🚀 Features
- Data loading & preprocessing (handling missing values, feature scaling, categorical encoding)
- Train-test split with **Stratified Sampling**
- Model training with:
  - Linear Regression
  - Decision Trees
  - Random Forest
- Model evaluation using **cross-validation** and performance metrics

## 📈 Results
- Models are trained and compared on predictive performance.
- Random Forest achieved the best accuracy (details inside notebook).
