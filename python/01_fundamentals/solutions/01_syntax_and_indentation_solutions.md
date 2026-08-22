# Exercise 1: Debugging
Errors identified:
1. Missing colon `:` after the first `if True`.
2. Inconsistent indentation for `print("Loading dataset...")` (an extra space).
3. Missing indentation for `print("Training model...")` inside the nested `if` block.

Corrected code:
```python
if True:
    print("Preparing data...")
    print("Loading dataset...")
    if True:
        print("Training model...")
```

# Exercise 2: Output Prediction
Output:
```text
Start
Step 1
Step 3
End
```
