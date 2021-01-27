# Assignment 2

In this assignment you will get familiar with commonly used functions for strings.

# Tutorials to review

Make sure you have reviewed the following topics before starting to work on this assignment. 

Strings: [https://www.py4e.com/lessons/strings](https://www.py4e.com/lessons/strings)

Also, please review the different [string functions](https://www.w3schools.com/python/python_ref_string.asp) that exist. 

## Required

You are asked to write a Python program to be able to communicate with Julius Caesar (as if he were still alive). Read up on his encryption method here: [https://en.wikipedia.org/wiki/Caesar_cipher](https://en.wikipedia.org/wiki/Caesar_cipher).

Through a time capsule you have received the following message from him, that uses a right-shift of 3: 'klzkdwvxs'. (Use left-shift to decode)

> Note: Caesar is not a big fan of spaces and interpunction.

Please write a function to reply to him, and send him an encrypted message(using a right-shift of 3). Please submit your python code along with the output of the program. In Jupyter notebook, select 'File', 'Download as', 'html'. This will create a HTML file with all cells and output, that you can submit in Canvas.

> Use Google to figure out how to add a number to a letter (like 'A' + 3 = 'D')

> Hint: to go through each character in a string: 

```python
for c in "hello": 
	print(c)
```