# Data_Analysis_Project_ColumbiaX
ColumbiaX Programming &amp; Data Structures Course


```markdown
# Data Analysis using Python

## Project Overview

This project involves analyzing and visualizing a dataset of physiochemical measurements for Portuguese "Vinho Verde" wines. The dataset includes both red and white wines, and the goal is to explore the data, build machine learning models, and gain insights into the relationships between different attributes of the wines.

The dataset is available at [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/wine_quality). It was originally collected by Paulo Cortez, Antonio Cerdeira, Fernando Almeida, Telmo Matos, and Jose Reis. The dataset is described in their paper:

    P. Cortez, A. Cerdeira, F. Almeida, T. Matos, and J. Reis.
    Modeling wine preferences by data mining from physicochemical properties.
    Decision Support Systems, Elsevier, 47(4):547-553. ISSN: 0167-9236.

## Dataset Description

The dataset consists of 13 columns:

1. **Fixed acidity**
2. **Volatile acidity** - correlated to the vinegar flavor
3. **Citric acid**
4. **Residual sugar** - affects how 'dry' or 'sweet' the wine is
5. **Chlorides**
6. **Free sulfur dioxide**
7. **Total sulfur dioxide**
8. **Density**
9. **pH**
10. **Sulphates**
11. **Alcohol**
12. **Quality** - subjective sensory score (0 to 10)
13. **Type** - 0 = Red wine, 1 = White wine

## Installation

All necessary packages have been pre-installed in this project. If you need to install them manually, you can use the following commands:

```bash
pip install pandas matplotlib numpy scikit-learn seaborn
```

## Usage

### Step 1: Reading the Data

1. Read the `winequality-red.csv` and `winequality-white.csv` files into pandas DataFrames.
2. Add a new column to distinguish between red and white wines.
3. Check for missing values and handle them if necessary.
4. Combine the datasets and shuffle them.
5. Split the data into training (90%) and test (10%) sets.

### Step 2: Data Visualization

1. **Class Distribution**: Plot the distribution of wine types using bar and pie charts.
2. **Attribute Distributions**: Plot histograms for attributes like pH, alcohol, citric acid, and residual sugar.
3. **Scatter Plots**: Create scatter plots to visualize correlations between attributes.

### Step 3: Regression Analysis

1. Perform linear regression to analyze the relationship between 'residual sugar' and 'alcohol'.
2. Plot the regression line on the scatter plot.
3. Optionally, experiment with other attribute pairs.

### Step 4: Classification

1. Prepare the data by dropping the 'type' and 'quality' columns.
2. Train different classifiers (e.g., SVC, Perceptron, DecisionTreeClassifier, RandomForestClassifier).
3. Evaluate the classifiers on the test set.

### Step 5: Regression: Predicting Wine Quality

1. Obtain the quality ratings for the training and test sets.
2. Train a linear regression model to predict wine quality from physiochemical attributes.
3. Evaluate the model using R² and mean squared error metrics.
4. Analyze the coefficients to determine the most important attributes for predicting wine quality.

## Example Code

Here is an example of how you might begin loading and visualizing the data:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Load the data
data_red = pd.read_csv('winequality-red.csv', delimiter=';')
data_white = pd.read_csv('winequality-white.csv', delimiter=';')

# Add type column
data_red['type'] = 0
data_white['type'] = 1

# Combine datasets
wines = pd.concat([data_red, data_white], ignore_index=True)

# Shuffle the dataset
shuffled_wines = wines.sample(frac=1, random_state=42).reset_index(drop=True)

# Split into training and test sets
test = shuffled_wines.sample(frac=0.1)
train = shuffled_wines.drop(test.index).sample(frac=1, random_state=42)
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgments

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/wine_quality) for the dataset.
- Paulo Cortez, Antonio Cerdeira, Fernando Almeida, Telmo Matos, and Jose Reis for collecting the data and their paper describing it.

Feel free to modify this template based on your project's requirements and updates!
```

This `README.md` provides a structured overview of your project and guides users through its various stages. Adjust the content to reflect any additional details or updates as your project progresses.
