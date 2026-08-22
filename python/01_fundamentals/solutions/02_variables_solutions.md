# Exercise 1: Output Prediction
Output:
```text
5
[10, 20, 30]
```

# Exercise 2: Concept Check
Integers (like `5`) are **immutable**. When `x` was reassigned (`x = x + 1`), Python created a brand new integer object (`6`) and pointed `x` to it. The **reference** `y` was still pointing to the original object (`5`).
Lists, however, are **mutable**. `list_1` and `list_2` are just two references pointing to the exact same list in memory. Mutating the list through `list_2` (using `.append()`) changes the underlying object, so both variables reflect the change.
