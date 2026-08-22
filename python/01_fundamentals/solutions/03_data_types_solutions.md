# Topic 3 Solutions: Data Types

## Exercise 1
```python
data = ""
result = 100

if data:
    result = result + 50
else:
    result = result - 20

print(result)
```
**Answer:** `80`. 
**Reasoning:** An empty string `""` evaluates to `False` in Python (it is "falsy"). The `if data:` condition fails, so execution falls to the `else` block, where `100 - 20 = 80`.

## Exercise 2
Original clunky code:
```python
def process_text(text):
    if type(text) == str:
        if len(text) > 0:
            print("Processing:", text)
        else:
            print("Empty string provided.")
    else:
        print("Error: Input is not a string.")
```

**Professional Pythonic Refactor:**
```python
def process_text(text):
    if isinstance(text, str): 
        if text:  # Pythonic truthiness check
            print("Processing:", text)
        else:
            print("Empty string provided.")
    else:
        print("Error: Input is not a string.")
```
**Reasoning:** `isinstance(text, str)` is the preferred way to check types because it accounts for subclasses (crucial in ML libraries). `if text:` perfectly evaluates whether the string contains characters, replacing the clunky `len(text) > 0`.
