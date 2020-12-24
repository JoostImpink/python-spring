# Assignment 3


# Tutorials to review

Make sure you have reviewed the following topics before starting to work on this assignment. 

Files: [https://www.py4e.com/lessons/files](https://www.py4e.com/lessons/files)

Lists: [https://www.py4e.com/lessons/lists](https://www.py4e.com/lessons/lists)


## Input file

The data used for this assignment can be downloaded from [assignment_3_cinderella.txt](assignment_3_cinderella.txt). Once you have downloaded the dataset, copy it to the same folder where you write your Python script.

If you are not sure in which directory Jupyter notebook is working from, you can run the following:

```python
# import the package os (operating system functions)
import os
# get the current working directory
cwd = os.getcwd()
# print it
print('Currently working in folder', cwd)
```

You can also use Jupyter notebook to create a new text file. Click 'new' and instead of a Python 3 notebook, select 'text file'. Copy the poem in this text file, and be sure to save it. You can doublecheck if it saved correctly by clicking on the file name in Jupyter notebook. Note the file name; your python code to read the file needs the exact file name.

You may drop the the last line as it is not part of the poem.

## Assignment

Look at the question/answer on Stackoverflow on how to read a file into a list [https://stackoverflow.com/questions/3277503/in-python-how-do-i-read-a-file-line-by-line-into-a-list](https://stackoverflow.com/questions/3277503/in-python-how-do-i-read-a-file-line-by-line-into-a-list):

Run the following code:

```python
# this assumes that the file 'cinderella.txt' is in the same folder as your ipynb script 
fname = "cinderella.txt"
with open(fname) as f:
    content = f.readlines()

# what kind of variable is content?
print(type(content))    
# you may also want to remove whitespace characters like `\n` at the end of each line
content = [x.strip() for x in content]

# print the first 5 lines
for line in content[0:5]:
	print(line)
```

The above code will read the cinderella poem into a list of strings, and will print the first 5 lines.

## Required

Write python code to do the following:

- the number of lines in the poem (note that content is a list, so use the 'len' function)
- the number of words in the poem (use the split function to turn each line into a list of words, use Google 'python string split') 
- how often does the prince cry? (count the lines that include both 'Prince' and 'cried')
- Caesar has received your reply for assignment 2 and let's you know he is interested in cultural milestones of the last 2,000 years. Encrypt the first 5 lines of the poem for Caesar (do not worry about interpunction).


