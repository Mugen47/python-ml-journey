# Topic 6 Solutions: Tuples

## Exercise 1
```python
results = ("ResNet50", 0.92, 14.5)
name, acc, time = results
print(f"Model: {name} | Accuracy: {acc:.0%} | Time: {time}s")
```
**Reasoning:** `name, acc, time = results` unpacks the tuple seamlessly into three separate variables in one line. We then use an f-string to format the output cleanly.

## Exercise 2
```python
lr_tuple = (0.01,)
```
**Reasoning:** `(0.01)` without a comma is just a mathematical operation (grouping) resulting in a float (`<class 'float'>` or `<class 'int'>` if it was a whole number). Adding the trailing comma `(0.01,)` forces Python to recognize it as a single-element tuple.

## Exercise 3
```python
x = 10
y = 20

x, y = y, x
```
**Reasoning:** This is the famous Pythonic variable swap. On the right side, `y, x` creates a hidden tuple `(20, 10)`. On the left side, `x, y` instantly unpacks that tuple into the variables, completely bypassing the need for a temporary variable!
