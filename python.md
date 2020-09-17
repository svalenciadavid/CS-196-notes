# Python
**Python** is a programming language, duh!
- **object oriented** & high level 
- converted into bytecode for an interpreter to execute.
- ends in .py

Object oriented: uses objects (ofc!)
Your code should be **pythonic** eg: it should be styled properly and less code whilst maintaing readability is the best.

### Making a simple Hello World program
In your terminal, use the follwing syntax to create a python script 
```bash$
$  python <filename>.py
$  python3 <filename>.py
```
Either of these methods work.
Now print "Hello World"
```bash$
$  print("Hello World")
```
### Variables
**Variables** help us store stuff in our programs. 
You don't need to specify a type for python variables, this is called **Dynamic Typing**
Some type examples are integers, floats, strings and booleans.

The **None Type** is a type of it's own that cannot be manipulated. It's used as an empty placeholder but it's not the same as 0, false, or "".

After you define a variable, you can change it to an array, int, string or whatever you want. You can store different types of things in the same array.

### Conditionals
Operators: 
- == : true if values are the same
- !=: true if values are not the same
- >=, <=, <, > : true if value is greater/less than the other
- is: checks if you are referencing the same object
- in: checks if the values is within another object.
```python 3.0
x = input("What number should x be: ")
x = int(x) #we are casting the input to an int
if x == 196:
    print("We have my favourite number")
else:
    print("We just have", x, "instead")
```
remember to indent! 

Use if/else for > 1 conditionals. Use elif for > 2 conditionals.
```python 3.0
if x == 196 or x % 5 == 0:
  print("We have my favourite number")
elif x % 5 == 0:
    print(x, "is a multiple of 5")
else:
    print("We just have ", x, " instead")
```
Use **and** and **or** kewords to group conditionals together.
