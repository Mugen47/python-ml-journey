# Topic: Python Syntax and Indentation

## Why This Matters
Unlike languages such as C++, Java, or JavaScript that use curly braces `{}` to define blocks of code, Python uses **indentation** (whitespace at the beginning of a line) to determine the structure and grouping of your code. If your indentation is wrong, your program will crash. This design choice forces Python code to be readable and uniform, which is incredibly important when collaborating on large Machine Learning projects.

## Explanation
### 1. The Python Execution Model
Python executes code line by line from top to bottom. It evaluates **expressions** (which produce a value, like `5 + 3`) and executes **statements** (which do something, like assigning a variable or printing).

### 2. Indentation
When you write conditional statements, loops, or functions, you create a "block" of code. In Python, you indicate that a block is starting using a colon (`:`). Every line inside that block MUST be indented by the same amount of spaces (the standard is 4 spaces).

### 3. Comments
Any text following a hash symbol `#` is ignored by Python. These are used to explain what the code does.

## Examples

### Level 1 — Basic (Simple Execution and Indentation)
```python
# This is a comment. Python ignores this.
print("Hello, Machine Learning!")  # This is a statement

if True:
    # Notice the 4 spaces before print. This is a block of code.
    print("This line is indented.")
    print("This is in the same block.")
    
print("This is NOT indented, so it is outside the block.")
```

### Level 2 — Intermediate (Nested Blocks)
```python
if True:
    print("Outer block started.")
    if True:
        # We indent another 4 spaces for the inner block (8 spaces total)
        print("Inner block.")
    print("Back to the outer block.")
```

### Level 3 — Hard (Whitespace and Line Continuations)
Sometimes a single statement is too long for one line. You can break it up using parentheses `()` or a backslash `\`.
```python
# Using parentheses to split a long logical statement
if (True and 
    True and 
    True):
    print("All true!")

# Using backslash (less common, usually discouraged in favor of parentheses)
long_calculation = 10 + 20 + \
                   30 + 40
```

## Common Mistakes
1. **IndentationError**: Mixing spaces and tabs, or using an inconsistent number of spaces. Python 3 strictly prohibits mixing tabs and spaces.
    ```python
    if True:
        print("4 spaces")
      print("2 spaces - THIS WILL CAUSE AN ERROR!")
    ```
2. **Forgetting the colon (`:`)**: The colon is required before starting an indented block.
    ```python
    if True  # Missing colon! SyntaxError
        print("Oops.")
    ```

## ML Connection
In Machine Learning, you will often write training loops that iterate over data epochs and batches. These loops are deeply nested. Proper indentation is the only way Python knows whether your model update step is happening *inside* the batch loop (correct) or *outside* the batch loop (incorrect, which ruins the training process).
