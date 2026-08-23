# Topic 5: Lists

## 1. What is it?
A list in Python is an ordered, **mutable** (changeable) collection of items. Lists can contain items of different data types, including other lists.

## 2. Why does it exist?
In Machine Learning, lists are the absolute foundation for storing sequences of data. Before you learn advanced numerical arrays (like NumPy), you will use lists to store model predictions, sequences of tokens in NLP, or rows of data from a CSV file.

## 3. How does it work?
Lists are created using square brackets `[]`. Because they are ordered sequences, you can access and slice them exactly like you did with Strings. But unlike Strings, you can modify lists in place.

## 4. Syntax and Core Methods
```python
fruits = ["apple", "banana", "cherry"]

# Indexing and Slicing (Same as strings!)
print(fruits[0])    # 'apple'
print(fruits[-1])   # 'cherry'
print(fruits[:2])   # ['apple', 'banana']

# Mutating (Changing items in place)
fruits[1] = "blueberry" 
print(fruits)       # ['apple', 'blueberry', 'cherry']
```

### Essential List Methods
- `.append(item)`: Adds an item to the **end** of the list.
- `.insert(index, item)`: Inserts an item at a specific position.
- `.pop(index)`: Removes and returns the item at the index (defaults to the last item).
- `.remove(value)`: Removes the *first* occurrence of a specific value.
- `.extend(list2)`: Adds all elements of a second list to the end of the first.
- `.sort()`: Sorts the list in place (modifies the original list).

## 5. Basic Examples
```python
# Building a list of predictions dynamically
predictions = []
predictions.append(0.85)
predictions.append(0.91)
print(predictions)  # [0.85, 0.91]

# Combining lists
batch_1 = [1, 2]
batch_2 = [3, 4]
batch_1.extend(batch_2)
print(batch_1) # [1, 2, 3, 4]
```

## 6. Intermediate Examples (Nested Lists)
Lists can contain other lists. This is how we represent 2D data (like a spreadsheet or an image) in pure Python.
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

# To get the number 6:
# First get the middle row (index 1), then the last item (index -1)
print(matrix[1][-1]) # 6
```

## 7. Hard Examples (The Aliasing Trap)
This is the most common mistake made by Python beginners. Because lists are mutable, variables simply **point** to the list in memory.
```python
a = [1, 2, 3]
b = a          # b points to the EXACT same list as a
b.append(4)

print(a)       # [1, 2, 3, 4] -> 'a' changed too!

# To make an actual independent copy, use the .copy() method or slice it [:]:
c = a.copy()
c.append(5)
print(a)       # Still [1, 2, 3, 4], 'c' is independent.
```

## 8. ML Connection
When building neural networks from scratch, the architecture is often defined as a list of layers. Furthermore, when reading raw data before passing it to a library like Pandas, it usually starts as a "list of lists" where each inner list represents a row in a dataset. 
