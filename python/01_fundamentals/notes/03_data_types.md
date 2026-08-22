# Topic: Python Data Types

## Why This Matters
In Machine Learning, your data will take many forms: numerical arrays, text labels, boolean masks, and configurations. Understanding the core Python data types is essential because applying the wrong operation to the wrong type (e.g., trying to add a string to an integer) will crash your pipeline. Knowing how to check types and understand "truthiness" will help you debug faster.

## Explanation

### 1. Numeric Types
- **`int`**: Whole numbers. Python handles arbitrarily large integers automatically.
- **`float`**: Decimal numbers. Standard for ML model weights and probabilities.
- **`complex`**: Complex numbers (e.g., `3 + 4j`). Rarely used in standard ML, but important for signal processing.

### 2. Text and Binary Types
- **`str`**: Text data, enclosed in quotes. Immutable.
- **`bytes` / `bytearray`**: Raw byte data. Useful for reading images, audio, or serialized ML models.

### 3. Boolean and None
- **`bool`**: `True` or `False`. Used for logic and masking.
- **`None`**: A special constant representing the absence of a value (similar to `null` in other languages). 

### 4. Collection Types (Brief intro, deeply covered later)
- **`list`**: Ordered, mutable sequence `[1, 2, 3]`.
- **`tuple`**: Ordered, immutable sequence `(1, 2, 3)`.
- **`set`**: Unordered collection of unique items `{1, 2, 3}`.
- **`dict`**: Key-value pairs `{"a": 1, "b": 2}`.

### 5. `type()` and `isinstance()`
- `type(x)` returns the exact type of `x`.
- `isinstance(x, type)` checks if `x` is an instance of a specific type (or a tuple of types). **This is the preferred, professional way to check types.**

### 6. Truthiness
In Python, every object can be evaluated as a boolean. 
- **Falsy**: `0`, `0.0`, `""` (empty string), `None`, `[]`, `{}`, `()`, `set()`.
- **Truthy**: Almost everything else!

### 7. Equality (`==`) vs Identity (`is`)
- `==` checks if the **values** are equal.
- `is` checks if they are the **exact same object in memory**.

## Examples

### Level 1 — Basic (Type Checking)
```python
x = 3.14
print(type(x))                  # Output: <class 'float'>
print(isinstance(x, float))     # Output: True
print(isinstance(x, (int, float))) # Output: True (checks if int OR float)
```

### Level 2 — Intermediate (Truthiness)
```python
empty_list = []
if empty_list:
    print("This won't print because empty lists are falsy.")

if not empty_list:
    print("This WILL print!")  # Preferred way to check if a list is empty
```

### Level 3 — Hard (Equality vs Identity with None)
```python
a = None
b = None

# Because None is a singleton (only one exists in memory), BOTH are True.
print(a == b)  # True
print(a is b)  # True

list_1 = [1, 2]
list_2 = [1, 2]
print(list_1 == list_2) # True, they have the same values
print(list_1 is list_2) # False, they are different objects in memory!
```

## Common Mistakes
1. Using `type(x) == list` instead of `isinstance(x, list)`. `isinstance` gracefully handles inheritance (subclasses), which is crucial when working with ML libraries that create custom object types.
2. Checking if a list is empty using `if len(my_list) == 0:`. The Pythonic way is simply `if not my_list:`.

## ML Connection
When reading a CSV dataset using Pandas, missing values often start as `None` or `NaN` (Not a Number, which is a float). Knowing how to detect and handle these null types, and understanding how booleans act as masks (e.g., selecting all rows where `age > 30`), is the absolute foundation of data preprocessing.
