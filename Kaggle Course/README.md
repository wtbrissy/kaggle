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

 - Strings and Dictionaries 
	```python
	'Pluto\'s a planet!'
	# using backlash to escape the single quote
	```
	The ```print()```function automatically adds a newline caracter unless we specify a value for the keyword argument ```end``` other than the default value of ```\n```:
	```python
	print("hello")
	print("world")
	print("hello", end='')
	print("pluto", end='')
	
	#hello
	#world
	#hellopluto
	```
	- .format()
	```python
	"{}, you will always be the {}th planet to me.".format(planet,position)
	```
	```python
	pluto_mass = 1.303 * 10*22
	earth_mass = 5.9722 * 10**24
	population = 52910390
	# 2 decimal points 3decimal points, format as percent separate with commas
	"{} weights about {:.2} kilograms ({:.3%} of Earth's mass). It is home to {:,} population.".format(planet, pluto_mass, pluto_mass / earth_mass, Plutonians)
	#"pluto weights about 1.3e+22 kilogram (0.218% of Earth's mass). It is home to 52,910,390 Plutonians"
	```
	[Pyformat](https://pyformat.info/)
	[Format String Syntax](https://docs.python.org/3/library/string.html#formatstrings)
	
- Working with External Libraries 
	```python
	from math import *
	print(pi, log(32,2)
	```
	```import *``` makes all the module's variables directly accessible. 
	
	However, a good compromise is to import **only the specific things we'll need from each module.**
	
	- Three tools for understanding strange objects 
		- type()(what is the thing?)
			```python 
			type(rolls)
			numpy.ndarray
			```
		- dir()(what can I do with it?)
			```python
			print(dir(roll))
			```
		- help()(tell me more)
			```python
			help(rolls.ravel)
			```
			
End of the Python Course. [Python Certificate](https://github.com/wtbrissy/kaggle/blob/main/Kaggle%20Course/Certificates/Winston%20Liang%20-%20Python.png)

## Intro to Machine Learning
- How models work
The step of capturing patterns from data is calling fitting or training the model. The data used to fit the model is called the **training data.** The point at the bottom wher emake a prediction is called a **leaf**. [Data Structure Tree](https://leetcode.com/explore/learn/card/data-structure-tree/)

- Basic Data Exploration 
	```.describe()``` print a summary of the dataset 
	
	- Interpreting Data Description
	
		count| mean | std | min |max
		---|---|---|---|---
		rows with non-missing values| average|standard deviation| column from lowest to highest | largest number|
		
	```columns``` see a list of all columns in the dataset 
	```dropna``` drops missing values 
	
	Prediction Target | Feature 
	---|---|
	dot-notation| Each item in the list should be a string (with quotes)
	
- Building the model 
	- Define: what type of model will it be? A decision tree? Some other types of model? Some other parameters of the model type are specified too? 
	- Fit: capture patterns from provided data. This is the heart of modelling. 
	- Predict: just what it sounds like
	- Evaluate: Determine how accurate the model's predictions are

- Model Validation 

	In most applications, the relevant measure of model quality is predictive accuracy. 

   ```python
      # Mean Absolute Error
      from sklearn.metrics import absoluate_error
   ```
   
   - Validation data
   
	   To exclude some data from the model-building process, and then use those to test te model's accuracy on data it hasn't seen before. The data is called ***validation data***.
	   
	   ```python
	   from sklearn.model_selection import train_test_split
	   ```
	   
- Underfitting and Overfitting
	- ***overfitting***: where a model matches the training data almost perfectly, but does poorly in validation and other new data. 
	- ***underfitting***: when a model fails to capture important distinctions and pattrns in the data, so it performs poorly even in training data. 
	
		```max_leaf_nodes``` argument provides a very sensible way to control overfitting vs underfitting area.
	
		![](https://github.com/wtbrissy/kaggle/blob/main/Kaggle%20Course/Attachments/Pasted%20image%2020211203105826.png)
		
		Example
		
		```python
		from sklearn.metrics import mean_absolute_error
		from sklearn.tree import DecisionTreeRegressor 
		
		def get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y):
			model = DecisionTreeRegressor(max_leaf_nodes=max_leaf_nods, random_state=0)
			model.fit(train_X, train_y)
			preds_val = model.predict(val_X)
			mae = mean_absolute_error(val_y, preds_val)
			return(mae)
			
		# load data 
		# filter rows with missing values 
		# choose target and features 
		# split data into training and validation data, for both featues and target 
		from sklearn.model_selection import train_test_split
		train_X, val_X, train_y, val_y = train_test_split(X, y, random_state=0)
		
		# compare MAE with differing values of max_leaf_nodes
		for max_leaf_nodes in [5, 50, 500, 5000]:
			my_mae = get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y)
			print("Max leaf nodes: %d \t\t Mean Absolute Error: %d" %(max_leaf_nodes, my_mae))
			
			six months (1 month - reconnecting )
	