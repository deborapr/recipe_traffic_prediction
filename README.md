# Recipe Traffic Prediction

A machine learning project developed as part of the DataCamp Data Scientist Professional Certification.

![Python](https://img.shields.io/badge/Python_3.11-3776AB?style=flat&logo=python&logoColor=white) ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white) ![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white) ![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat&logo=python&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logo=python&logoColor=white)


## Business Context

A recipe website found that featuring a popular recipe on the homepage can increase overall site traffic by up to 40%. The business goal is to predict which recipes will drive high traffic and to do so correctly at least 80% of the time.

## Project Overview

This project covers the full data science workflow:

- Data validation and cleaning
- Exploratory data analysis (EDA)
- Feature engineering and preprocessing
- Model fitting and evaluation
- Business recommendations

## Dataset

947 recipes with the following features:

| Feature        | Description                                             |
| -------------- | ------------------------------------------------------- |
| `calories`     | Calorie count                                           |
| `carbohydrate` | Carbohydrate content (g)                                |
| `sugar`        | Sugar content (g)                                       |
| `protein`      | Protein content (g)                                     |
| `category`     | Recipe category (11 categories)                         |
| `servings`     | Number of servings                                      |
| `high_traffic` | Target variable — whether the recipe drove high traffic |

## Key Findings

- **Category is the strongest predictor of traffic.** Vegetable (99%), Potato (94%), and Pork (92%) consistently drive high traffic, while Beverages (5%) is a strong negative signal.
- **Nutritional variables show weak but statistically significant associations** with traffic, with all four right-skewed and high variability.
- **Servings shows little variation** in traffic rates across groups and is a weak predictor on its own.

## Modeling

<!-- \<p align="center">
    <img src="workspace/recipe_traffic_ml_pipeline.png" alt="Modeling pipeline" width="300"> 
</p> -->



![Modeling pipeline](workspace/recipe_traffic_ml_pipeline.png "Modeling pipeline")

Two models were compared:

| Model                        | Accuracy | Precision | Recall |
| ---------------------------- | -------- | --------- | ------ |
| Logistic Regression (scaled) | 77.9%    | 84.8%     | 77.4%  |
| Decision Tree (max_depth=4)  | 78.4%    | 84.9%     | 78.3%  |

**Logistic Regression was selected as the final model**, given near-identical performance, its simplicity and interpretability make it the preferable choice for a business context.

Cross-validation confirmed results are consistent and the model generalizes well (precision: 79.3% ± 3.6%, recall: 81.0% ± 4.1%).

## Results

The final model achieves **85% precision**, exceeding the 80% business target. When the model predicts a recipe will be popular, it is correct 85% of the time.

## Recommendations

**Prioritize:**

- Vegetable (99% high traffic)
- Potato (94% high traffic)
- Pork (92% high traffic)

**Avoid :**

- Beverages (5% high traffic)
- Breakfast (31% high traffic)
- Chicken (36% high traffic)

## Project Structure

```
├── notebook.ipynb             # Full analysis notebook
├── recipe_site_traffic.csv    # Dataset
├── requirements.txt           # Project dependencies
├── presentation.pdf           # Business presentation slides
└── README.md
```

## Tools & Libraries

- Python (pandas, numpy)
- scikit-learn
- seaborn, matplotlib
