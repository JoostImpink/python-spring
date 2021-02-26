# Assignment 9 - Process costing

This assignment is about processing data that is in a file.

# Tutorials to review

Make sure you have reviewed the following topics before starting to work on this assignment. 

Files: [https://www.py4e.com/lessons/files](https://www.py4e.com/lessons/files)

Lists: [https://www.py4e.com/lessons/lists](https://www.py4e.com/lessons/lists)

## Input files

Create the three input files.

### Beginning op period details

Copy/paste the following lines in a new file and call this file `begin.txt`:

```
units:250
materialsComplete:0.8
conversionComplete:0.4
materialCost:2200
conversionCost:1500
```

This input file will hold the number of units that were in process at the beginning of the period, and the degree of completion with regards to material and conversion, as well as the cost of materials and conversion that were made for the units.

### End of period details

Copy/paste the following lines in a new file and call this file `end.txt`:

```
materialsComplete:0.9
conversionComplete:0.5
```

The end data only has information about the degree of completion of end of period work in process for materials and conversion.

### Events throughout the period

Copy/paste the following lines in a new file and call this file `events.txt`:


```
event,date,detail
2,02/01/2019,5
4,02/01/2019,250
3,04/01/2019,550
2,05/01/2019,40
3,06/01/2019,700
4,07/01/2019,100
3,07/01/2019,1000
4,08/01/2019,150
1,09/01/2019,20
4,09/01/2019,200
2,09/01/2019,30
2,10/01/2019,30
4,10/01/2019,350
1,12/01/2019,15
3,14/01/2019,400
2,14/01/2019,30
4,15/01/2019,550
3,15/01/2019,450
2,16/01/2019,50
2,17/01/2019,5
1,17/01/2019,40
2,19/01/2019,40
3,19/01/2019,850
4,20/01/2019,350
1,22/01/2019,30
2,22/01/2019,40
3,22/01/2019,350
1,23/01/2019,45
2,25/01/2019,10
4,26/01/2019,750
2,29/01/2019,15
1,31/01/2019,50
```

The events data starts with an eventid (1: start new units, 2: completed units, 3: material cost, 4: conversion cost), followed by the date, and #units (events 1 and 2) or $ amount (events 3 and 4).

For example:

- 2,02/01/2019,5: 5 units were completed
- 4,02/01/2019,250: $250 conversion costs incurred
- 3,04/01/2019,550: $550 material costs incurred
- 1,09/01/2019,20: started 20 new units 


## Assignment

Create a program that reads the input files, and computes the cost of goods manufactured and the cost of ending work in process using the weighted average method.


