# Topic 9 Solutions: Control Flow

## Exercise 1
```python
age = 45

if age < 18:
    print("Minor")
elif age >= 18 and age <= 64:
    print("Adult")
else:
    print("Senior")
```
**Reasoning:** The `if` statement checks the first condition. If it's false, the `elif` checks the boundaries using the `and` logical operator. If neither is true, it falls back to the `else` statement. 
*(Pro-tip: Python allows chained comparisons, so you could also write `18 <= age <= 64`!)*

## Exercise 2
```python
readings = [12.5, 14.1, None, 11.2, None, 15.0]

for result in readings:
    if result is None:
        continue
    print(result)
```
**Reasoning:** The `for` loop iterates through each reading. The `continue` statement acts as a short-circuit; if the value is `None`, it skips the `print` statement and instantly jumps to the next iteration.

## Exercise 3
```python
loss = 1.0
epoch = 0

while True:
    epoch += 1
    loss -= 0.1
    print(f"Epoch: {epoch}, Loss: {loss:.1f}")
    
    if loss < 0.3 or epoch == 5:
        break
```
**Reasoning:** This is a classic infinite loop pattern `while True`. It only stops because we explicitly coded a `break` condition. The `or` operator ensures that the loop shatters if *either* the target loss is reached, or the maximum number of epochs is hit.
