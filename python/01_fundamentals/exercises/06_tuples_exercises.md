# Topic 6 Exercises: Tuples

## Exercise 1: Unpacking (Level 2)
You are writing an evaluation script for an ML model. The function you called returned a tuple containing three items: the model's name, its accuracy, and its training time.
```python
results = ("ResNet50", 0.92, 14.5)
```
Using **Tuple Unpacking** (do not use indices like `results[0]`), write the Python code to extract these three values into three separate variables named `name`, `acc`, and `time`. Then print them in a formatted f-string.

## Exercise 2: The Tuple Trap (Level 2)
You want to create a tuple containing exactly one hyperparameter (the learning rate `0.01`). 
```python
lr_tuple = (0.01)
```
1. Run `print(type(lr_tuple))` in your code. What type does it output?
2. Fix the code so that `lr_tuple` is actually a tuple containing `0.01`.

## Exercise 3: Swapping Variables (Level 3 - Pythonic Secret)
In many programming languages, if you want to swap the values of two variables, you need a temporary third variable:
```python
x = 10
y = 20
# Traditional swap:
temp = x
x = y
y = temp
```
In Python, because of **Tuple Packing and Unpacking**, you can swap `x` and `y` in exactly ONE line of code without using a `temp` variable. 

Write the single line of code that swaps `x` and `y`. *(Hint: Think about creating a tuple on the right side of the equals sign, and unpacking it on the left!)*
