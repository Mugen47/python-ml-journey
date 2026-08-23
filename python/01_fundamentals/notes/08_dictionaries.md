# Topic 8: Dictionaries

## 1. What is it?
A dictionary (`dict`) in Python is an unordered, **mutable** collection of **key-value pairs**. It is incredibly fast for looking up values based on a unique key, just like looking up a word's definition in a real dictionary.

## 2. Why does it exist?
In Machine Learning, dictionaries are the backbone of data structure formatting.
- **JSON Data:** APIs and datasets often return data in JSON format, which maps perfectly 1-to-1 with Python dictionaries.
- **Hyperparameters:** When training an ML model, you will often pass in a dictionary of configuration settings (e.g., `{"learning_rate": 0.01, "batch_size": 32}`).
- **Model Weights:** PyTorch and TensorFlow store neural network layers and weights inside dictionaries (called a `state_dict`).

## 3. How does it work?
Dictionaries are created using curly braces `{}` with keys and values separated by a colon `:`. 
**Keys MUST be unique and immutable** (like strings, integers, or tuples).
**Values can be absolutely anything** (including lists or other dictionaries).

## 4. Syntax and Core Methods
```python
# Creating a dictionary
student = {
    "name": "Alice",
    "age": 28,
    "courses": ["Math", "CompSci"]
}

# Accessing a value
print(student["name"])  # 'Alice'

# Modifying or Adding a new key-value pair
student["age"] = 29
student["graduated"] = False
```

### Essential Dictionary Methods
- `.get(key, default)`: Safely gets a value. If the key doesn't exist, it returns the `default` (or `None`) instead of crashing.
- `.keys()`: Returns a view of all keys.
- `.values()`: Returns a view of all values.
- `.items()`: Returns a view of all `(key, value)` tuples.
- `.update(dict2)`: Merges another dictionary into this one.

## 5. Basic Examples (The Safe Lookup)
Accessing a key that doesn't exist using brackets `[]` will crash your program with a `KeyError`. Always use `.get()` if you aren't 100% sure the key exists.
```python
config = {"theme": "dark"}

# print(config["font_size"]) <--- KeyError! Program crashes.

# Safe way:
font = config.get("font_size", 12)
print(font) # Prints 12 (the default fallback value)
```

## 6. Intermediate Examples (Iterating through a Dictionary)
To loop through a dictionary effectively, use the `.items()` method, which unpacks the key and value simultaneously.
```python
model_metrics = {"accuracy": 0.95, "loss": 0.02, "f1_score": 0.93}

for metric_name, value in model_metrics.items():
    print(f"{metric_name.capitalize()}: {value}")
```

## 7. Hard Examples (Nested Dictionaries)
When working with JSON data, you will often deal with dictionaries inside dictionaries.
```python
dataset = {
    "user_101": {
        "name": "Bob",
        "purchases": [15.99, 20.00]
    },
    "user_102": {
        "name": "Charlie",
        "purchases": [5.50]
    }
}

# Extract Bob's first purchase amount:
print(dataset["user_101"]["purchases"][0]) # 15.99
```

## 8. ML Connection
When you use **Pandas**, the most popular data manipulation library, creating a DataFrame (a table of data) from scratch is often done using a dictionary where the keys are the column names and the values are lists representing the rows.
```python
import pandas as pd

data = {
    "Age": [25, 30, 35],
    "Income": [50000, 60000, 70000],
    "Target": [0, 1, 1]
}

df = pd.DataFrame(data) 
# This instantly creates a beautifully formatted table ready for ML!
```
