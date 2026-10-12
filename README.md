# California Housing Price Prediction

![Python](https://img.shields.io/badge/Python-3-3776AB?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![Best CV RMSE](https://img.shields.io/badge/best%20CV%20RMSE-%2449.9k-2c9fbf?style=flat-square)

Predicts the median house value of California districts from the 1990 census: location, housing age, rooms, population, households, median income and distance to the ocean. The notebook is a complete regression project, from exploration to a tuned model with a confidence interval on its test error.

## Results

| Model | Evaluation | RMSE |
|:--|:--|:--|
| Linear Regression | 10-fold CV | $69,104 (std $2,880) |
| Decision Tree | 10-fold CV | $70,891 (std $2,246), overfits: $0 on the training set |
| Random Forest, before tuning | 10-fold CV | about $50,400 |
| **Random Forest, grid-searched** | **5-fold CV** | **$49,882** |
| Random Forest, final model | Held-out test set | 95% confidence interval: **$45,920 to $49,834** |

The best model uses 30 trees and 6 features per split. By importance, the strongest predictors are median income (0.30), being inland (0.16), population per household (0.11) and bedrooms per room (0.09).

## What the notebook does

1. **Explores the data:** 20,640 districts, histograms, a geographic scatter plot of prices, and correlations with the target.
2. **Splits the data with stratified sampling** on income category, so the test set has the same income mix as the full data.
3. **Engineers features:** rooms per household, bedrooms per room and population per household.
4. **Builds a preprocessing pipeline:** median imputation, a custom `CombinedAttributesAdder` transformer, standard scaling, and one-hot encoding of `ocean_proximity`, combined in a `ColumnTransformer`.
5. **Compares models:** Linear Regression, Decision Tree and Random Forest, each with 10-fold cross-validation.
6. **Tunes the forest:** `GridSearchCV` over the number of trees, features per split and bootstrapping.
7. **Evaluates once on the test set** and reports a 95% confidence interval for the RMSE.

## Run it

```bash
pip install -r requirements.txt
jupyter notebook Housing.ipynb
```

## Files

| File | Purpose |
|:--|:--|
| `Housing.ipynb` | Exploration, preprocessing, model comparison, tuning and evaluation |
| `requirements.txt` | Python dependencies |

---

<sub>Built by [Aryan Awasthi](https://github.com/Techy-A). ENC @ Thapar Institute of Engineering and Technology.</sub>
