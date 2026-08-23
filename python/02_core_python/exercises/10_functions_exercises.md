# Topic 10 Exercises: Functions

## Exercise 1: The Basic Calculator (Level 1)
Write a function called `subtract` that takes two parameters: `x` and `y`.
The function should **return** the result of `x - y`.
After defining it, call the function with `10` and `3`, save the result to a variable, and print the variable.

## Exercise 2: The Data Normalizer (Level 2)
In ML, we often "normalize" data by dividing it by the maximum possible value.
Write a function called `normalize_pixel` that takes one parameter: `pixel_value`.
- The function should calculate `pixel_value / 255.0`
- It should **return** this new normalized value.

Call your function passing in `128` and print the result.

## Exercise 3: Early Return Logic (Level 3)
You are writing a security function for a server. 
Write a function called `check_access` that takes one parameter: `role`.
- If `role` is `"admin"`, the function should immediately **return** `True`.
- If `role` is anything else, the function should **return** `False`.

*(Hint: Do this without using an `else` block! Remember that `return` exits the function immediately).*
Test it by calling `check_access("guest")` and printing the result.
