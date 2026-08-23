# Topic 9: Control Flow (If, For, While)

## 1. What is it?
Control flow is how you dictate the "path" your code takes. Until now, our code has executed strictly from top to bottom, line by line. Control flow allows your code to make **decisions** (`if`), **repeat** tasks (`for`, `while`), and skip lines of code entirely based on logic.

## 2. Why does it exist?
Without control flow, software wouldn't be "smart". In Machine Learning, control flow is used everywhere:
- **`if` statements:** "If the model's accuracy drops below 80%, stop training."
- **`for` loops:** "For every image in the dataset, resize it to 256x256."
- **`while` loops:** "While the loss function is still decreasing, keep training the model."

## 3. The `if` Statement (Making Decisions)
Python uses `if`, `elif` (else if), and `else`. It relies entirely on **indentation** to know what code belongs inside the block.

```python
accuracy = 0.85

if accuracy > 0.90:
    print("Deploy the model!")
elif accuracy > 0.80:
    print("Keep training, it's getting there.")
else:
    print("The model is failing. Restart.")
```
**Important:** You can chain logical operators like `and`, `or`, and `not`.
```python
if accuracy > 0.80 and not is_overfitting:
    pass # 'pass' just means "do nothing right now"
```

## 4. The `for` Loop (Iterating over Collections)
A `for` loop in Python doesn't usually use a counter (like `i=0; i<10` in C++). Instead, it iterates directly over the items in a collection (like a list, tuple, string, or dictionary).

```python
# Iterating over a list
loss_values = [0.5, 0.4, 0.2]
for loss in loss_values:
    print(f"Current loss: {loss}")

# Iterating over a range of numbers using range()
# range(5) generates numbers 0, 1, 2, 3, 4
for epoch in range(5):
    print(f"Training epoch {epoch}")
```
*Note: `range(start, stop, step)` is a very powerful function to generate number sequences.*

## 5. The `while` Loop (Repeating until a Condition is False)
A `while` loop runs forever as long as its condition evaluates to `True`. You MUST ensure the condition eventually becomes `False`, or you will create an **infinite loop**.

```python
battery = 100
while battery > 0:
    print(f"Running... battery at {battery}%")
    battery -= 20 # Same as battery = battery - 20
print("Battery dead.")
```

## 6. Loop Control (`break` and `continue`)
Sometimes you need to interrupt a loop from the inside.
- `break`: Completely shatters the loop. The loop ends immediately.
- `continue`: Skips the rest of the *current* iteration and instantly jumps to the *next* iteration.

```python
# Using break (Early Stopping in ML)
losses = [10, 5, 2, 0.1, 0.05, 0.01]
for loss in losses:
    if loss < 0.1:
        print("Target reached. Stopping early.")
        break
    print(f"Loss is {loss}, continuing...")

# Using continue (Skipping corrupted data)
images = ["img1.png", "CORRUPTED", "img2.png"]
for img in images:
    if img == "CORRUPTED":
        continue # Skip to the next image immediately
    print(f"Processing {img}")
```

## 7. ML Connection (The Training Loop)
When you build neural networks using PyTorch from scratch, the core of your program is quite literally just a massive `for` loop, nested inside another `for` loop!

```python
# Example of a PyTorch-style training loop structure
epochs = 10
batches = [batch1, batch2, batch3] # Pretend these hold data

for epoch in range(epochs):
    print(f"--- Starting Epoch {epoch} ---")
    
    for current_batch in batches:
        # 1. Pass batch through model
        # 2. Calculate loss
        # 3. Update weights
        pass 
```
