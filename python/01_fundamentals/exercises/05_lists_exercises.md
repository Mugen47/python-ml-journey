# Topic 5 Exercises: Lists

## Exercise 1: The Queue (Level 1)
You are writing code to manage a queue of image files to be processed by a neural network.
```python
queue = ["img1.png", "img2.png"]
```
Write the Python code to:
1. Add `"img3.png"` to the end of the queue.
2. Remove and print the **first** image in the queue (simulating that it has been processed).
*Hint: Look up how the `.pop()` method works with specific indices.*

## Exercise 2: Nested Data Extraction (Level 3)
You have a small batch of image data represented as a 3D list (a list containing lists of lists). 
```python
batch = [
    [ [0, 0], [0, 0] ],   # Image 1 (2x2 pixels)
    [ [1, 1], [1, 1] ],   # Image 2 (2x2 pixels)
    [ [2, 2], [2, 9] ]    # Image 3 (2x2 pixels)
]
```
Write the single line of Python code (using chained indexing like `batch[x][y][z]`) to extract and print the number `9` from the 3rd image.

## Exercise 3: The Copy Trap (Level 4)
You are writing an algorithm to normalize data. You want to keep the original data safe, and only modify the `normalized` variable.

```python
original_data = [100, 200, 300]

# Your junior colleague wrote this:
normalized = original_data
normalized.remove(300)

print("Original:", original_data)
print("Normalized:", normalized)
```
Run this code. You will see the original data is destroyed (300 is removed). **Fix the junior colleague's code** so that `original_data` remains `[100, 200, 300]`, but `normalized` becomes `[100, 200]`.
