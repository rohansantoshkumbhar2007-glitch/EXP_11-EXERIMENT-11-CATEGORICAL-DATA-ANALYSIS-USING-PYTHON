# Experiment 11: Categorical Data Analysis Using Python

## Objective
To analyze categorical data using Python and perform statistical tests and visualizations to understand relationships between categorical variables.

## Tools and Libraries Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy

## Description
Categorical Data Analysis involves analyzing variables that represent categories rather than numerical values. In this experiment, Python libraries are used to load, process, visualize, and analyze categorical datasets.

The experiment includes:
- Loading a dataset
- Identifying categorical variables
- Performing frequency analysis
- Creating visualizations (bar plots, count plots, pie charts)
- Conducting statistical tests such as the Chi-Square test

## Steps Involved

1. Import required Python libraries.
2. Load the dataset using Pandas.
3. Identify categorical columns in the dataset.
4. Perform frequency counts using `value_counts()`.
5. Visualize categorical distributions using Seaborn and Matplotlib.
6. Create contingency tables using `pd.crosstab()`.
7. Perform Chi-Square test using `scipy.stats`.
8. Interpret the results.

## Sample Code

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from scipy.stats import chi2_contingency

# Load dataset
data = pd.read_csv("data.csv")

# Display first few rows
print(data.head())

# Frequency count
print(data['Category'].value_counts())

# Visualization
sns.countplot(x='Category', data=data)
plt.title("Category Distribution")
plt.show()

# Contingency Table
table = pd.crosstab(data['Category'], data['Outcome'])

# Chi-Square Test
chi2, p, dof, expected = chi2_contingency(table)

print("Chi-Square Value:", chi2)
print("P-Value:", p)
