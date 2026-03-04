# Decision Trees & Random Forests – Iris Classification Benchmark  
**From Single Trees to Robust Ensembles**

## Overview

This project provides a clear, end-to-end comparison of a single **Decision Tree** and a **Random Forest** ensemble for multi-class classification using the classic Iris dataset.

It demonstrates core concepts in tree-based learning:
- How decision trees partition feature space
- Interpretability vs. overfitting trade-off
- Variance reduction through bagging and random feature subsampling
- Practical performance comparison on a clean, well-known benchmark

Both models achieve **96% test accuracy** (43/45 correct) with default hyperparameters, highlighting that even a single tree performs exceptionally well on this low-noise dataset — while the random forest offers greater robustness for more challenging problems.

## Project Structure
iris-trees-to-forest/
├── README.md                  # This file
├── iris_classification.ipynb  # Main Jupyter notebook: preprocessing → DT → RF → comparison
├── requirements.txt           # Python dependencies

## Requirements

- Python 3.8+
- Jupyter Notebook / JupyterLab
- Libraries:
  - `scikit-learn`
  - `pandas`
  - `numpy`
  - `matplotlib` / `seaborn` (for optional visualizations)

## Installation

1. Clone the repository

   ```bash
   git clone https://github.com/<your-username>/iris-trees-to-forest.git
   cd iris-trees-to-forest

## Dataset

- **Name**: Iris  
- **Source**: UCI Machine Learning Repository (available via scikit-learn or public CSV)  
- **Samples**: 150  
- **Classes**: 3 (Iris-setosa, Iris-versicolor, Iris-virginica)  
- **Features**: 4 numerical (all in cm)  
  - sepal length  
  - sepal width  
  - petal length  
  - petal width  
- **Difficulty**: Very easy  
  - *setosa* is linearly separable  
  - *versicolor* and *virginica* show mild overlap in feature space

## Key Results

- **Decision Tree** (default parameters, random_state=42)  
  - Test accuracy: **96.0%** (43/45 correct)  
  - Perfect separation of *Iris-setosa* (100% precision, recall, F1)  
  - 2 boundary errors between versicolor ↔ virginica

- **Random Forest** (100 trees, default parameters, random_state=42)  
  - Test accuracy: **96.0%** (identical on this split)  
  - Same confusion pattern:  
    - 1 versicolor misclassified as virginica  
    - 1 virginica misclassified as versicolor  
  - Expected to show more stable decision boundaries in cross-validation or noisier data

## Running the Notebook

1. Open `iris_classification.ipynb` in Jupyter Notebook or JupyterLab  
2. Run cells sequentially  
3. Follow the main sections:  
   - Data loading & preprocessing  
   - Single Decision Tree training & evaluation  
   - Random Forest training & evaluation  
   - Confusion matrices, classification reports & interpretation

## Takeaway

On this famously clean and well-separated dataset, a single decision tree already delivers near-perfect performance with excellent interpretability.  
The random forest matches this accuracy while providing variance reduction and greater robustness — making it the preferred, production-ready choice when facing noisier, larger, less balanced, or more complex real-world data.

## Next Steps & Extensions

- Hyperparameter tuning  
  (max_depth, min_samples_split, min_samples_leaf, n_estimators, max_features)  
- Cross-validated performance comparison & learning curves  
- Visualization of decision boundaries and feature importance  
- Introduce artificial noise/outliers to highlight ensemble advantage  
- Benchmark against other classifiers  
  (k-NN, SVM, logistic regression, gradient boosting, etc.)

## Resources

- [scikit-learn Decision Trees](https://scikit-learn.org/stable/modules/tree.html)  
- [scikit-learn Random Forests](https://scikit-learn.org/stable/modules/ensemble.html#forest)  
- Breiman, L. (2001). Random Forests. *Machine Learning*, 45(1), 5–32.  
- [UCI Machine Learning Repository – Iris Dataset](https://archive.ics.uci.edu/dataset/53/iris)
