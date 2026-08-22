# Topic: Variables, References, and Object Identity

## Why This Matters
In Machine Learning, you handle massive datasets and complex models. Understanding how Python assigns variables, how it handles memory, and the difference between mutable (changeable) and immutable (unchangeable) objects is critical. If you don't understand this, you will accidentally modify a dataset when you think you are just creating a copy of it, leading to disastrous ML bugs.

## Explanation

### 1. Variables and Assignment
In Python, variables are not "buckets" that hold values. They are **labels** or **name tags** attached to objects in memory. You assign a variable using the `=` operator.

### 2. Naming Rules & Conventions
- **Rules**: Names can contain letters, numbers, and underscores, but *cannot* start with a number. They are case-sensitive (`data` and `Data` are different).
- **Conventions**: We use `snake_case` for variable names (e.g., `training_data`, `learning_rate`). Constants are usually written in `UPPER_SNAKE_CASE` (e.g., `MAX_ITERATIONS = 100`).

### 3. Reassignment
You can reassign a variable to point to a completely different type of object. Python is dynamically typed.

### 4. References and Object Identity (`id()`)
Because variables are just name tags, multiple variables can point to the *exact same object in memory*. You can check an object's unique memory address using the `id()` function. The `is` operator checks if two variables point to the exact same memory location.

### 5. Mutable vs Immutable Objects
This is one of the most important concepts in Python:
- **Immutable Objects**: Once created, their contents *cannot* be changed. If you try to change them, Python creates a brand new object. Examples: Integers, floats, strings, booleans, and tuples.
- **Mutable Objects**: Their contents *can* be changed in-place without creating a new object. Examples: Lists, dictionaries, and sets.

## Examples

### Level 1 — Basic (Assignment and Reassignment)
```python
epochs = 10         # Assigned to an integer
learning_rate = 0.01 # Assigned to a float
epochs = "Ten"      # Reassigned to a string (Python allows this!)
```

### Level 2 — Intermediate (Object Identity)
```python
x = 100
y = x     # y is now pointing to the exact same object as x
print(x is y)  # Output: True
print(id(x) == id(y)) # Output: True
```

### Level 3 — Hard (Mutable vs Immutable Behavior)
```python
# IMMUTABLE: Integers
a = 10
b = a
a = 20  # Reassigns 'a' to a new integer. 'b' is still looking at 10.
print(b) # Output: 10

# MUTABLE: Lists
list_a = [1, 2, 3]
list_b = list_a  # list_b points to the SAME list as list_a
list_a.append(4) # Mutates the object in place
print(list_b)    # Output: [1, 2, 3, 4] -> list_b changed too!
```

## Common Mistakes
Assuming that `y = x` creates an independent copy of `x`. If `x` is a mutable object (like a list), modifying `y` will also modify `x` because they are just two labels for the same memory location.

## ML Connection
When preprocessing data, you might do something like `clean_data = raw_data`. If `raw_data` is a Pandas DataFrame (which is mutable), and you drop a column from `clean_data`, that column will also vanish from `raw_data`! To prevent this, you explicitly have to ask for a copy: `clean_data = raw_data.copy()`.
