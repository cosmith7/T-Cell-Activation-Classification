# T-Cell Activation Classification

## Background
This project develops a machine-learning model to predict whether a T-cell is **active** or **quiescent** using quantitative features extracted from fluorescence microscopy images.  

Using classification modeling, data cleaning, feature analysis, standardization, SGD-based training, and evaluation, the project identifies which features most strongly predict T-cell activation in human immune cells.  

This project demonstrates:

- Data cleaning & preprocessing  
- Exploratory data analysis  
- Correlation-based feature selection  
- Train/validation/test splitting  
- Standardization  
- Logistic regression (and other classifiers) with stochastic gradient descent  
- Model evaluation (accuracy, confusion matrix, ROC curve, residual analysis)  
- Model interpretation with standardized & unstandardized coefficients  

## References
- Walsh, A. J., et al. (2021). Classification of T-cell activation via autofluorescence lifetime imaging. *Nature Biomedical Engineering*, 5(1), 77–88. [DOI](https://doi.org/10.1038/s41551-020-0592-z)  
- Wang, Z. J., et al. (2020). Classifying T cell activity in autofluorescence intensity images with convolutional neural networks. *Journal of Biophotonics*, 13(3), e201960050. [DOI](https://doi.org/10.1002/jbio.201960050)  

## Repository Structure
```
t-cell-classification/
│
├── README.md
├── t_cell_classification.ipynb
├── size_intensity_feature.csv
│
├── results/
│ ├── class_distribution.png
│ ├── logistic_regression_plot.png
│ ├── knn_elbow_plot.png
│ └── decision_tree.png
```


## Requirements
To run this project, the following Python libraries are required:

* ``pandas``
* ``numpy``  
* ``matplotlib``
* ``seaborn``
* ``scikit-learn``
* ``graphviz``

Install via pip if needed:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn graphviz
```

## Methodology
Data Preparation
* Removed missing values
* Selected features: cell_size and total_intensity

Train/Validation/Test Split
* 70% training
* 30% testing

Feature Scaling
* Standardized predictors using StandardScaler to ensure stable training and comparable coefficient magnitudes

Models
* Logistic Regression (SGD-based)
* K-Nearest Neighbors (KNN)
* Decision Tree

Evaluation Metrics
* Accuracy
* Confusion Matrix
* ROC curve (optional)
*  Residual analysis

Key Results
Logistic Regression
* Accuracy: ~82%
* Coefficient interpretation:
  * cell_size: positive influence on activation
  * total_intensity: negative influence on activation

K-Nearest Neighbors
* Optimal K: 30
* Test accuracy: ~80%

Decision Tree
* Max depth: 4
* Test accuracy: ~86%
* Most important feature: ``total_intensity``

## Conclusion
* Decision Tree achieves the highest accuracy (~86%) and is the most suitable model for this task.
* ``cell_size`` and ``total_intensity`` are both important, with total_intensity dominating in the tree model.
* Such models can assist in identifying active T-cells for immunotherapy, speeding up research and therapy design.

## License

This project is for educational purposes as part of the UMD Machine Learning for the Life Sciences course (BSCI238I).
