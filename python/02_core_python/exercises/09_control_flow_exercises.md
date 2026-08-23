# Topic 9 Exercises: Control Flow

## Exercise 1: The Classifier (Level 1)
You are writing a script that categorizes a user's age into demographic groups.
- If `age` is less than 18, print `"Minor"`
- If `age` is between 18 and 64 (inclusive), print `"Adult"`
- If `age` is 65 or older, print `"Senior"`

Write the `if-elif-else` statement to handle this. Test it with `age = 45`.

## Exercise 2: The Data Cleaner (Level 2)
You have a list of sensor readings, but some of the sensors malfunctioned and outputted `None`.
```python
readings = [12.5, 14.1, None, 11.2, None, 15.0]
```
Write a `for` loop that iterates over `readings`. 
- If the reading is `None`, use `continue` to skip it.
- Otherwise, print the reading.

## Exercise 3: Early Stopping (Level 3)
You are simulating a training process. 
```python
loss = 1.0
epoch = 0
```
Write a `while` loop that runs forever (`while True:`).
Inside the loop:
1. Increase `epoch` by 1.
2. Decrease `loss` by `0.1` (Hint: `loss -= 0.1`).
3. Print the current epoch and loss.
4. If `loss` falls below `0.3` or `epoch` hits `5`, use the `break` statement to exit the loop.
