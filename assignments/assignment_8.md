# Assignment 8 - Reciprocal method

## First

Before working on this assignment, read the following:

- [numpy tutorial](http://cs231n.github.io/python-numpy-tutorial/)
- [Solving a system of equations](https://medium.com/@GalarnykMichael/solving-system-of-linear-equations-using-python-645ad1904cec)


## Required

See file [assignment_8_data.csv](assignment_8_data.csv). It contains data for three service departments (tech_support, payroll and housekeeping) and two production departments (roasting and packaging). (To download, click 'raw', and copy/paste the data into a new file.)

It holds the direct department costs for each, and the cost driver usage (tech_support uses workstations, payroll uses employees, and housekeeping allocates based on square feet).

Required: Compute the costs for both roasting and packaging after allocating the service department costs to these production departments using the reciprocal method. Your code should read the csv file from disk.

You may 'hardcode' the department names, but not the cost driver usage (that is, this info needs to be read from disk, so that if the cost driver usage in the input file changes, the costs get recalculated with rerunning the code with no changes to the code). 

## Notes

### Solving a system of equation example

Note this example to solve a system of equations using numpy. This is a general example, the equations for the reciprocal method may be somewhat different.

```python
import numpy as np

# Solving following system of linear equation
# 1a + 1b = 35
# 2a + 4b = 94

a = np.array([[1, 1],[2,4]])
b = np.array([35, 94])

print(np.linalg.solve(a,b))
```
In the above example, the matrix and vectors are hard-coded. In your code, these numbers should be based on the data in the csv.

### Reading csv file into list of dictionaries

It may be helpful to have the data in dictonaries (list of dictionaries, where each dictionary holds the info for one department). The following code reads a csv into a list of dictionaries:

```python
import csv

with open('assignment_8_data.csv') as f:
    data = [{k: v for k, v in row.items()} for row in csv.DictReader(f, skipinitialspace=True)]
print(data)
```

> To get you started, see the following [notebook](assignment_8_heads_up.ipynb)