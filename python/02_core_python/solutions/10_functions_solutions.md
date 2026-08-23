# Topic 10 Solutions: Functions

## Exercise 1
```python
def subtract(x, y):
    return x - y

result = subtract(10, 3)
print(result) # 7
```
**Reasoning:** We define the function to accept two parameters. It calculates the difference and uses `return` to hand the value back to the main program, where it is captured in the variable `result`.

## Exercise 2
```python
def normalize_pixel(pixel_value):
    return pixel_value / 255.0

print(normalize_pixel(128)) # 0.50196...
```
**Reasoning:** The function takes a single pixel value, performs float division, and returns the mathematically normalized value.

## Exercise 3
```python
def check_access(role):
    if role == "admin":
        return True
    
    return False

print(check_access("guest")) # False
```
**Reasoning:** Notice the lack of an `else` block! Because the `return` statement instantly exits the function, if the role is `"admin"`, the function returns `True` and dies immediately. If the role is NOT `"admin"`, the `if` block is skipped, and it hits the `return False` at the bottom. This is a very common professional pattern called "Early Return"!
