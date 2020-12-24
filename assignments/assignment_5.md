# Assignment 5

# Tutorials to review

This assignment uses lists and dictionaries.

Make sure you have reviewed the following topics before starting to work on this assignment. 

Lists: [https://www.py4e.com/lessons/lists](https://www.py4e.com/lessons/lists)

Dictionaries: [https://www.py4e.com/lessons/dictionary](https://www.py4e.com/lessons/dictionary)

## Random numbers

Run the following code to see how random numbers can be generated:

```python
import random
for x in range(10):
  print ( random.randint(1,21) )
```

### Assignment

Your instructor is attacking you from 'Western United States' with 16 troops. You are defending 'Eastern United States' with only 7 troops.

Write a python program that will play out this attack. For the game rules, see [assignment_5_risk_rules.pdf](assignment_5_risk_rules.pdf), in particular, pages 9-11 show 'Combat' and 'How to battle'.

Record each attack round in a dictionary. Keep track of the dice that were rolled (your instructor will roll 3 dice as long as he can attack with 3 or more troops), you can roll two dice (as long you have at least 2 troops to defend with). 

Each round, also record the number of troops at the start of the round for each player, and the troops lost for each player in that round (and the troops that are left). 

Collect each of the dictonaries in a list (in other words, you will have a list that holds dictonaries, one dictonary for each round). The length of the list will show how many rounds were played.

The game will stop when your instructor conquers Eastern United States. He will also stop attacking if the number of his troops falls below your troops.

After recording the game in the list of dictonaries, answer the following questions:

- How many rounds were played
- Who is in charge of Eastern United States?
- How many troops were lost on average each round by the instructor?
- As above: for  yourself
