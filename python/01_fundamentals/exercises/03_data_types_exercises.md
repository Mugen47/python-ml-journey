# Exercise 1: Truthiness and Types
Predict the output of the following code snippet:

```python
data = ""
result = 100

if data:
    result = result + 50
else:
    result = result - 20

print(result)
```

# Exercise 2: Debugging and Best Practices
The following function tries to check if the input is a string and if it is not empty. However, it uses poor Python practices. Rewrite it using `isinstance()` and Pythonic truthiness.

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
