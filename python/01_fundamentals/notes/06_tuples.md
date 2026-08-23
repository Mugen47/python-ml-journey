# Topic 6: Tuples

## 1. What is it?
A tuple in Python is an ordered, **immutable** (unchangeable) collection of items. It is almost exactly like a list, except once you create a tuple, you can NEVER change its contents.

## 2. Why does it exist?
If a tuple is just a list you can't change, why use it? 
1. **Safety:** In Machine Learning, you often have data that should *never* change during execution (like the shape of an image matrix: `(256, 256, 3)`). Using a tuple guarantees that a stray line of code won't accidentally mutate this critical data.
2. **Speed and Memory:** Because tuples are immutable, Python optimizes them. They take up slightly less memory and are faster to iterate through than lists.
3. **Dictionary Keys:** Lists cannot be used as keys in a dictionary (because they can change), but tuples can!

## 3. How does it work?
Tuples are created using parentheses `()` (though the parentheses are actually optional; it's the commas `,` that define a tuple). Because they are ordered, you index and slice them just like lists and strings.

## 4. Syntax and Core Methods
```python
# Creating tuples
dimensions = (1920, 1080)
hyperparameters = 0.01, 32, 64  # Parentheses are optional!

# Indexing and Slicing (Same as lists!)
print(dimensions[0])    # 1920
print(hyperparameters[-1]) # 64

# Attempting to mutate throws an error!
# dimensions[0] = 800  <--- TypeError: 'tuple' object does not support item assignment
```

### Essential Tuple Methods
Because they are immutable, tuples only have **two** methods:
- `.count(value)`: Returns the number of times a value appears in the tuple.
- `.index(value)`: Returns the index of the first occurrence of a value.

## 5. Basic Examples
```python
# Unpacking (A very Pythonic feature!)
# You can assign multiple variables at once from a tuple
model_config = ("Adam", 0.001, 100)
optimizer, learning_rate, epochs = model_config

print(learning_rate) # 0.001
```

## 6. Intermediate Examples (The Single Element Tuple Trap)
If you want to create a tuple with exactly ONE element, you **must** include a trailing comma. Parentheses alone are just treated as mathematical grouping!
```python
math_variable = (5)
print(type(math_variable))  # <class 'int'>

single_tuple = (5,)
print(type(single_tuple))   # <class 'tuple'>
```

## 7. Hard Examples (Nested Mutability)
This is a tricky interview question! A tuple itself cannot be changed. However, if a tuple *contains* a mutable object (like a list), you CAN mutate the list inside the tuple!
```python
complex_tuple = (1, 2, [3, 4])

# You cannot do this: complex_tuple[0] = 99
# But you CAN do this:
complex_tuple[2].append(5)

print(complex_tuple) # (1, 2, [3, 4, 5])
```
*Why? Because the tuple is still pointing to the EXACT same list object in memory. The tuple didn't change its pointers, the list itself changed.*

## 8. ML Connection
When you use a library like **NumPy** or **TensorFlow**, the shape of a multi-dimensional array or tensor is ALWAYS returned as a tuple (e.g., `(batch_size, height, width, channels)`). Furthermore, many ML functions return multiple values (e.g., `return loss, accuracy`). When a function returns multiple values separated by commas, it is secretly returning a tuple!
