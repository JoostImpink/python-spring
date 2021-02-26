# Assignment 6 - Regression

# Tutorials to review

Review [this notebook with regression analysis](https://github.com/justmarkham/DAT4/blob/master/notebooks/08_linear_regression.ipynb)

Note that the code for a linear regression is:

```python
import statsmodels.formula.api as smf # convention for importing statsmodels

# assuming you have a dataframe `df` with variables `Return` and `Unemployment`
model = smf.ols(formula="Return ~ Unemployment", data=df)
result = model.fit()
result.summary()
```

## Glassdoor.com

[Glassdoor](www.glassdoor.com) is a website where employees can leave reviews (anonymously). For example, reviews for EY can be found at [https://www.glassdoor.com/Reviews/EY-Reviews-E2784.htm](https://www.glassdoor.com/Reviews/EY-Reviews-E2784.htm).

One of the scores is the work-life balance, ranging between 1 (poor) and 5 (good).  

## Required

Do auditors working for a 'big 4' (Deloitte, EY, KPMG, PWC) have different (lower or higher) work-life balance ratings compared with auditors working for 'non-big 4' audit firms?

To answer this question, use [this Glasdoor.com dataset](assignment_6_glassdoor.csv). Click 'raw' to get to a page with the actual data. Copy/paste this in a new textfile in the same folder as your jupyter notebook. Name it as 'assignment_6_glassdoor.csv'.

The dataset consists of 438 ratings for employees of Florida offices of the 8 largest Audit firms. Reviews were downloaded summer 2017. 

Most of the variables are self-explanatory. Rating variables are between 1 (lowest) and 5 (highest).

Rating variables:

- overall_rating: Overal rating
- worklife: Rating for work-life balance
- cultule_values: Rating for culture/values
- career: Rating for career
- compensation: Rating for compensation
- seniormanagement: Rating for senior management

Note that some variables may be missing, meaning that these were not filled out. You will also need to create a variable to capture if the firm was a 'big 4' or not. (Create a variable `big4` and set it to 1 if that is the case, 0 otherwise.) You can create this variable in Excel (and save the csv again with an extra column), or add a column (variable) in the dataframe using python. See [https://stackoverflow.com/questions/12555323/adding-new-column-to-existing-dataframe-in-python-pandas](https://stackoverflow.com/questions/12555323/adding-new-column-to-existing-dataframe-in-python-pandas) for some suggestions.

### Reading the csv file into a dataframe

The following code will load the dataset into a dataframe (used to do regressions). It assumes that the csv is in the same folder as your jupyter notebook file.

```python
import pandas as pd

# read data into a DataFrame
data = pd.read_csv('assignment_6_glassdoor.csv')
# show the first 5 records
data.head()
```