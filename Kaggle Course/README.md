## Table of Content
- [Python](#python)
- [Intro to Machine Learning](#intro-to-machine-learning)
- [Pandas](#pandas)
- [Intermediate Machine Learning](#intermediate-machine-learning)
- [Data Visualization](#data-visualization)
- [Feature Engineering](#feature-engineering)
- [Intro to SQL](#intro-to-sql)
- [Advanced SQL](#advanced-sql)
- [Intro to Deep Learning](#intro-to-deep-learning)
- [Computer Vision](#computer-vision)
- [Time Series](#time-series)
- [Data Cleaning](#data-cleaning)
- [Intro to AI Ethics](#intro-to-AI-ethics)
- [Geospatial Analysis](#geospatial-analysis)
- [Machine Learning Explainability](#machine-learning-explainability)
- [Natural Learning Processing](#natural-learning-processing)
- [Intro to Game AI and Reinforcement Learning](#intro-to-game-ai-and-reinforcement-learning)


## Project Summary 
This repository is a centre hub for all notes and codes of Kaggle course.

## Python
- Defining functions 
	``` python
	def least_difference(a,b,c):
		diff1 = abs(a - b)
		diff2 = abs(b - c)
		diff3 = abs(a - c)
		return min(diff1, diff2, diff3)
		
	print(
		lease_difference(1,10,100)
	)
	```
	Functions start with a header introducted by the ```def``` keyword. THe indented block of code following the ```:``` is run when the function is called. 
	
	When python encouters a ```return``` statement, it exits the function immediately, and passes the values on the right hand side to the calling context.
	
- Booleans and Conditionals
	```python
	True or Ture and False
	
	# True
	```

	```and``` is evaluated before ```or```.

- Blackjack Solution 
	```python
	from learntools.core import binder; binder.bind(globals())
	from learntools.python.ex3 import q7 as blackjack

	def should_hit(dealer_total, player_total, player_low_aces, player_high_aces):
		if player_total <= 11:
			return True
		else:
			return False

	blackjack.simulate(n_games=1000000) 

	# Player win 413055 out of 1000000 games (win rate = 41.3%)
	```

	[Blackjack Solution](https://github.com/wtbrissy/kaggle/blob/main/Kaggle%20Course/Course%20Codes/blackjack-solution.ipynb)

- List 
	```Python
	hands = [
		['J', 'Q', 'K'],
		['2', '2', '2'],
		['6', 'A', 'K'], 
	]

	# Best pratice is not writting on one line 
	```
	- Objects
	In short, objects carry some things around with them. The stuff can be accessed using Python's ***dot syntax***
	
	- A function attached to a object is called a ***method***
	- Non-function things attached to an object, such as ```imag```, are called ***attributes***
		```python 
		# numbers have a method called bit_length
		x.bit_length  
		#<funtion int.bit_length()>
		#To actually call it, we add parentheses: 
		x.bit_length()
		#4 
		```

 