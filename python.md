# Python
[**Slides Pt.1**](https://docs.google.com/presentation/d/1JRMhGyehMycagS3AaHW6hQt8xCXzSqiJuN_Rvr5WhEw/edit#slide=id.g989f9d05b8_0_13) 

[**Youtube Video Pt.1**](https://www.youtube.com/watch?v=-l4afjEqSd4&feature=youtu.be)

**Python** is a programming language, duh!
- **object oriented** (classes) & high level (abstraction from lower level, handles/hides more form you) 
- converted into bytecode for an interpreter to execute.
- Python file end in .py

Aim to have [**pythonic**](https://docs.python-guide.org/writing/style/) code eg: it should be styled properly and less code whilst maintaing readability is the best.


### Making a simple Hello World program
In your terminal, use the following syntax to run a python file (both work)
```bash$
$  python <filename>.py
$  python3 <filename>.py
```

# Programming in Python
**_Note:_** Python is _**indentation Sensitive**_ as well as caps sensitive. You will see this later on in the examples

## **Variables** 
They help us store stuff in our programs. 

**_Notes:_** 
* You don't need to specify a type (boolean, char, string...) for python variables (**Dynamic Typing**)
* Once you have declared and assigned a variable a value, it can change to anything later on (dynamic)

* **None** is a type of it's own that cannot be manipulated. It's used as an empty placeholder (not the same as 0, false, or "")
```python
x = 4
x = [1, 2, 3, 4]
x = "There is no char type in python"
print(x)
# Output:
# There is no char type in python
```

### Casting:
Casting allows us to force a variable into a specific data type

**_Note:_**  The input function asks for user input, therefore you will have to type in a number, in this example, I typed "199". You will see this function returns a String type object (text), however, we can cast it to be an int (numerical value).
```python
x = input("What number should x be: ")
print(x, type(x))
x = int(x)
print(x, type(x))

# Output:
# What number should x be: 199
# 199 <class 'str'>
# 199 <class 'int'>
```

## If-else
If-else statements/conditionals allow us to make decisions in code

This is the syntax:
```python
if <some-condition>:
	# Do something
elif <alternative-condition>:
	# Do something else
else:
	# Damn, all that failed, okay, do this
```
 
### Operators:
To specify our conditions, we use operators. Here are some operators, and what they do: 
- **" == " :** Returns true if values are the same
- **" != " :** Returns true if values are not the same
- **" > ", " < "  :** Returns true if value is greater/less than the other
- **" >= ", " <= " :** Returns true if value is greater/less than or equal to the other
- **" is " :** Returns true if you are referencing the same object
- **" in " :** checks if the values is within another object.

**_Note:_** Use **and** and **or** keywords to group conditionals together.

In this example I use and for fun, to showcase grouping conditionals. Both x == 196 and g == 100 have to be true so that the block of code, that is indented, runs.
```python 3.0
x = input("What number should x be: ")
x = int(x) #Cast to int type 
y = x
g = 100
if x == 196 and g == 100:
	print("We have my favourite number")
    if y is x:
	    print("this is the same thing")
	 elif y >= x:
		 print("y is a bigger number than x")
else:
    print("We just have", x, "instead")

# Output:
# What number should x be: 196
# We have my favourite number
# this is the same thing
```
## Loops

Loops allow us to repeatedly run the same block of code

### For loops
For loops allow us to iterate in a range of values, until a list ends..etc

In this example, we use range(x, y, z) with a different amount of parameters(x, y, z)
```python 3.0
print("--First Example--")
# y value specifies end in range (exclusive, aka, ends at 9)
# With only one parameter we assume x (starting number) is 0
for i in range(4):
	print(i)
	
print("--Second Example--")
# Specifies both starting and ending index
for i in range(1,4):
	print(i)
	
print("--Third Example--")
# Specifies both starting, ending, and steps(we will count up by two/skip odd numbers)
for i in range(0,4,2):
	print(i)
	
# Output:
# --First Example--
# 0
# 1
# 2
# 3
# --Second Example--
# 1
# 2
# 3
# --Third Example--
# 0
# 2
```

We can also iterate through a data structure, like a list of items (arraylist in java)
```python 3.0
x = [1,9,6] #Create list of values
for values in x:
	print(val)	
	
# Output:
# 1
# 9
# 6
```
### While loops
While loops allow us to run a block of code while a condition is true
```python 3.0
while <conditional is true>:
	#do stuff
```
### Break and continue
These are used if you want to break completely out of a loop, or continue on to the next number in the range (for loop specific-i think)

```python 3.0
while <conditional is true>:
	if <conditional>:
		break #while loop stops running
for i in range(10):
	if i % 2 == 0:
		continue #skips even numbers
	elif i == 9:
		break #breaks out of the loop at i == 3
```

## Functions
Functions allow us to add FuNCTIOnAlitY to our programs, it will allow us to specify a block of code which we plan on reusing, we can _call_ this function whenever we want it to run the code in it.

Declaring a function looks like this:
```python 3.0
def function_name(<arg1>, <arg2>, <arg...>):
	#code goes here
```
To have the function return to the block of code where it was called, you use the _return_ keyword, like this:

```python 3.0
def function_name(<arg1>, <arg2>, <arg...>):
	#code goes here
	return
```
Alternatively, we can also have this function return a value as it returns to where it was called, we do this like so:
```python 3.0
def function_name(<arg1>, <arg2>, <arg...>):
	#code goes here
	return -1 #returns the value -1
	#return can also return a boolean, string..etc
```

**_Note:_** In python you do not need to specify return types or types for your arguments

Calling a function looks like this:
```python 3.0
function_name(arg1, arg2, arg...)
```

## Data Structures

### List:
Lists are a collection that is **ordered** and **changeable**, it allows duplicate values as well.
**_Note:_** In python the types of elements don't need to be the same
```python 3.0
# Declaration + initialization
x = [1, 4, 4, -5, 3]
# Accesing index
# indexes start at 0, will print out 4
print(x[1])
# we use the len() function to get the 
# length of a list
print(len(x)) 
# acessing an index that is out of bounds
# will lead your program to crash, as in here.
print(x[5])
```
We can also slice through a list using the " : " separator
```python 3.0
x = [1, 4, 4, -5, 3]
# Works like range
print(x[2:5])

# Output:
# [4, -5, 3]
```

## Exception handling

When an exception (error) occurs in Python, the program stops running and sends an error message
Exception handling is us handling an exception in code so that the program doesn't go boom

To handle exceptions we use try and except, try tries to run a block of code, if an exception happens inside, it will run anything in the except block.
```python 3.0
x = "CS 196"
try:
	x += 2
except:
	print("ah shucks, something happened")
finally:
	# This block of code runs no matter what

# Output:
# ah shucks, something happened 
```
## Importing 
Importing is used to get access to libraries with packages of classes that may provide functionality needed without needing to code it yourself.


### Libraries
Libraries provide a set of helper functions/objects/modules for your code to call

**_Notes:_** If you want good libraries, google for them, check git stars, check documentation(example code), README, check support (look at the issues tab, are people getting the help they need?). 

### Language:
* **Module:** A file with a .py extension
* **Package:** a directory containing an \_\_init\_\_.py file
* **Build in module:** A module natively installed with Python
* **Object:** anything inside a module/package that can be referenced like a class or function or variable

To import an entire module/package you use:
```python
import <module/package>
# Example:
import math
```
If you only need to use a small portion of it use:
```python
from <module/package> import <stuff you're-using>, <stuff>, <stuff>
# Example:
from math import gcd, factorial
```
You can also change the names of the functions/rename what's being imported:
```python
from <module/package> import <stuff you're-using> as <rename-here>
# Example:
from math import factorial as <fact>
print(fact(10))
# Output prints out 10!
```
**What about third party ones?**
we need a package manager for that because people use libraries to build their libraries, we create then dependency graphs.
Python's package manager is **Pip**
(Rust-> Cargo, JS-> NMP, Java-> Maven)

In bash we type:
```bash
$ pip install <package-name>
```
If we need a lot of packages we create a requirements.txt
```
Mako==1.1.1
MarkupSafe==1.1.1
six==1.14.8
```
```bash
$ pip install -r requirements.txt
```