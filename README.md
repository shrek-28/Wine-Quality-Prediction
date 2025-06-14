# Is the Wine Fraud or Legit?

## Introduction 
This project leverages the Wine Quality dataset to perform a binary classification of wine samples as either **"fraud"** or **"legit"** based on their physicochemical properties. Features such as acidity, sugar content, sulfur dioxide levels, pH, and alcohol concentration are used to train a **Support Vector Machine (SVM)** classifier that detects potentially fraudulent or substandard wine entries with high accuracy. The model was explained using ```SHAP```.

## Dataset Features.
The dataset was obtained from this link: https://archive.ics.uci.edu/dataset/186/wine+quality

The dataset's features are explained below:
| Variable Name         | Role     | Type        | Description                                            | Units               | Missing Values |
|-----------------------|----------|-------------|--------------------------------------------------------|---------------------|----------------|
| fixed_acidity         | Feature  | Continuous  | Non-volatile acids that do not evaporate easily       | g/dm³               | No             |
| volatile_acidity      | Feature  | Continuous  | Volatile acids (mainly acetic acid) affecting flavor  | g/dm³               | No             |
| citric_acid           | Feature  | Continuous  | Adds freshness and flavor to the wine                 | g/dm³               | No             |
| residual_sugar        | Feature  | Continuous  | Sugar remaining after fermentation                    | g/dm³               | No             |
| chlorides             | Feature  | Continuous  | Amount of salt in the wine                            | g/dm³               | No             |
| free_sulfur_dioxide   | Feature  | Continuous  | SO₂ not bound to other molecules, prevents spoilage   | mg/dm³              | No             |
| total_sulfur_dioxide  | Feature  | Continuous  | Total SO₂, including both free and bound forms        | mg/dm³              | No             |
| density               | Feature  | Continuous  | Mass per unit volume; influenced by sugar/alcohol     | g/cm³               | No             |
| pH                    | Feature  | Continuous  | Acidity level of the wine (logarithmic scale)         | —                   | No             |
| sulphates             | Feature  | Continuous  | Sulfur compounds that act as wine preservatives       | g/dm³               | No             |
| alcohol               | Feature  | Continuous  | Ethanol content by volume                             | % vol.              | No             |
| quality               | Target   | Integer     | Wine quality score assigned by tasters (0–10 scale)   | —                   | No             |
| color                 | Other    | Categorical | Type of wine: red or white                            | red / white         | No             |

## Methodology:
1. Basic data exploration was done, using ```df.head()``` and ```df.info()```.
2. Data was visualized, including the classes and their balance, and their distribution in the red wines and white wines, and percentage of frauds in red wine and white wine were calculated.
3. Correlation was calculated of the ```fraud``` and ```legit``` values, with the different variables.
4. Clustermap was utilized for visualization.
5. The categorical variables were encoded; and feature-target and train-test splits were utilized with ```StandardScaler()``` to prepare the data for ML.
6. Support Vector Classifiers were utilized, first with the complete training data. GridSearchCV was used, to identify the best possible model.
7. Bad parameters were observed for the ```fraud``` class, likely due to class imbalance.
8. The dataset underwent random sampling, to ensure that both target values were represented equally, and the complete process of SVC with GridSearchCV was repeated.
9. The model was explained using SHAP.

## Results:
| Class   | Precision | Recall | F1-Score | Support |
|---------|-----------|--------|----------|---------|
| Fraud   | 0.71      | 0.68   | 0.69     | 25      |
| Legit   | 0.69      | 0.72   | 0.71     | 25      |
|         |           |        |          |         |
| **Accuracy**       |         |          | 0.70     | 50      |
| **Macro Avg**      | 0.70    | 0.70     | 0.70     | 50      |
| **Weighted Avg**   | 0.70    | 0.70     | 0.70     | 50      |

With the reduced data, the SVC model showed the following results.
The SHAP summary plot revealed that features such as free sulfur dioxide, type, and volatile acidity had the greatest impact on the model's predictions, with free sulfur dioxide being the most influential. High values of type and free sulfur dioxide tended to push the predictions toward the positive class, while low values of volatile acidity contributed negatively. The color gradient represented the feature values, showing how higher (red) or lower (blue) values influenced the SHAP values. This analysis provided insights into not only the importance of each feature but also the direction and nature of their effects, enhancing the interpretability of the model's decision-making process.
