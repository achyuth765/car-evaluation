# Car Evaluation Classification

## Project Overview

This project focuses on predicting the **acceptability of cars** using the Car Evaluation dataset.

The project explores different machine learning classification models and compares their performance using accuracy, precision, recall, F1-score, and confusion matrices.

## Dataset

The dataset contains **1,728 observations** with six input features:

- `buying` – Buying price
- `maint` – Maintenance price
- `doors` – Number of doors
- `persons` – Passenger capacity
- `lug_boot` – Luggage boot size
- `safety` – Safety level

The original target contains four classes:

- `unacc` – Unacceptable
- `acc` – Acceptable
- `good` – Good
- `vgood` – Very Good

For this project, `good` and `vgood` are combined into a single **Good** class, resulting in three target classes:

- **Unacceptable**
- **Acceptable**
- **Good**

## Machine Learning Models

The following classification models are implemented and compared:

1. Decision Tree
2. Pruned Decision Tree
3. Random Forest
4. AdaBoost

Hyperparameter tuning is performed using **GridSearchCV** with **5-fold Stratified Cross-Validation**.

## Data Preprocessing

The categorical features are converted into ordinal numerical values.

The dataset is split into:

- **80% Training data**
- **20% Testing data**

A stratified split is used to preserve the class distribution.

Because the dataset is imbalanced, especially with the **Unacceptable** class being dominant, macro-averaged precision, recall, and F1-score are used in addition to accuracy.

## Key Findings

- The full Decision Tree achieves approximately **98% accuracy**.
- A moderately pruned Decision Tree provides strong generalisation with lower model complexity.
- The tuned Random Forest performs approximately on par with the best pruned Decision Tree.
- AdaBoost with depth-1 decision stumps performs worse than the tree-based models.
- The **Acceptable** class is the most difficult class to predict.
- `safety` and `persons` show particularly strong relationships with the target.
- Random Forest is more suitable than AdaBoost for this particular dataset under the tested configurations.

## Project Structure

```text
car-evaluation/
│
├── Untitled(8).ipynb
├── car.data
├── car.names
├── car.c45-names
└── README.md
```

## Libraries Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## How to Run

1. Clone or download this repository.
2. Make sure Python is installed.
3. Install the required libraries:

```bash
pip
