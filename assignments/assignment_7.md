# Assignment 6 - Regression (Cost function estimation)

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

## Hospital cost data

CMS.gov is providing healthcare cost data that are available for download. You can download 2018 data at [https://www.cms.gov/research-statistics-data-systems/medicare-provider-utilization-and-payment-data/medicare-provider-utilization-and-payment-data-inpatient/inpatient-charge-data-fy-2018](https://www.cms.gov/research-statistics-data-systems/medicare-provider-utilization-and-payment-data/medicare-provider-utilization-and-payment-data-inpatient/inpatient-charge-data-fy-2018), see 'detailed data', Downloadable CSV.

The dataset contains the following variables:
- DRG Definition: description of the procedure
- Provider Id: id of hospital
- Provider Name/address/city/state/zip: name, etc of hospital
- Hospital Referral Region: region
- Total discharges: number of time sthe DRG has been performed in 2018
- Average covered charges: initial billing amount (ignore)
- Average Total Payment: average payment
- Average Medicare Payments: reimbursement Medicare

The cost data is for the 100 most common DRGs, for about 3,000 hospitals.

## Required

Examine the costs of procedures DRG 460 “Spinal fusion except servical” and DRG 853 “Parasitic and infectious diseases” for the hospitals in the dataset. Provide some basic statistics (mean, median, min, max) of the costs. Also, determine if hospitals that have a larger volume charge a lower price or not (in other words: test for positive or negative economies of scale). Do this for both procedures. Youse 'Average Total Payment' as a proxy for the cost.

When you do the regression, include dummy variables to capture differences in costs between States. You can use `C(Provider State)' in your regression. 

Example on adding dummies for categorial variables (also see [https://www.statsmodels.org/stable/example_formulas.html#categorical-variables](https://www.statsmodels.org/stable/example_formulas.html#categorical-variables)):

```python
import statsmodels.formula.api as smf
import pandas as pd
import numpy as np

dict = {'industry': ['mining', 'transportation', 'hospitality', 'finance', 'entertainment'],
  'debt_ratio':np.random.randn(5), 'cash_flow':np.random.randn(5) + 90} 

df = pd.DataFrame.from_dict(dict)

x = df[['debt_ratio', 'industry']]
y = df['cash_flow']

# NB. unlike sm.OLS, there is "intercept" term is included here
smf.ols(formula="cash_flow ~ debt_ratio + C(industry)", data=df).fit()
```

### Reading the csv file into a dataframe

The following code will load the dataset into a dataframe (used to do regressions). It assumes that the csv file is in the same folder as your jupyter notebook file.

```python
import pandas as pd

# read data into a DataFrame
data = pd.read_csv('MEDICARE_PROVIDER_CHARGE_INPATIENT_DRGALL_FY2018.CSV')
# show the first 5 records
data.head()
```

> Note: importing the dataset may take 30 seconds or so. Also note that the dataset contains 100 DRGs and that for the regression you will want to filter only the relevant DRG. (One regression for each DRG)

The following code shows you how you can filter records based on the DRG description. It will make a new dataframe with rows for DRG 003.

```python
data003 = data.loc[data['DRG_DESC'].str.startswith('003') ]
data003.head()
```

