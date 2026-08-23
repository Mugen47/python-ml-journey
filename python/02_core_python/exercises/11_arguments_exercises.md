# Topic 11 Exercises: Arguments

## Exercise 1: The Configurator (Level 1)
Write a function called `setup_server` that takes three parameters: `host`, `port`, and `debug`.
- Provide a **default argument** for `port` so it defaults to `8080`.
- Provide a **default argument** for `debug` so it defaults to `False`.

The function should print: `Server starting on {host}:{port} | Debug mode: {debug}`.

Call your function three times:
1. Providing only the `host` (`"localhost"`).
2. Providing the `host` (`"192.168.1.1"`) and overriding the `port` to `9000` using a positional argument.
3. Providing the `host` (`"production.com"`) and overriding `debug` to `True` using a **keyword argument** (leaving the port as the default).

## Exercise 2: Keyword Enforcement (Level 2)
Look at the following function call:
```python
train_network(0.001, 64, 100, 0.9)
```
As an ML engineer reading this, you have no idea what those numbers mean. 

Write the function definition for `train_network` that accepts four parameters: `learning_rate`, `batch_size`, `epochs`, and `momentum`. The function just needs to print them out.
**Then**, call the function using *only* **keyword arguments** to pass those exact four values (0.001, 64, 100, 0.9), so the code is completely readable.

## Exercise 3: The `*args` Aggregator (Level 3)
You are writing a utility function to average an unknown number of metric scores.
Write a function called `average_scores` that uses `*args` to accept any number of positional arguments.
The function should calculate the average of the scores passed in and return it. (Hint: use Python's built in `sum()` and `len()` functions).

Test it by calling `print(average_scores(85, 90, 95, 100))`.
