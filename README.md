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

