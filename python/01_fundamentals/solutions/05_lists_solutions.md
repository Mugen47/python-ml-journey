# Topic 5 Solutions: Lists

## Exercise 1
```python
queue = ["img1.png", "img2.png"]
queue.append("img3.png")
print(queue.pop(0))
```
**Reasoning:** `.append("img3.png")` safely adds the new image to the very end of the list. `.pop(0)` removes the element at index `0` (the first element) and returns it so it can be printed.

## Exercise 2
```python
batch = [
    [ [0, 0], [0, 0] ],   
    [ [1, 1], [1, 1] ],   
    [ [2, 2], [2, 9] ]    
]
print(batch[2][1][1])
```
**Reasoning:** 
- `batch[2]` selects the 3rd image `[ [2, 2], [2, 9] ]`.
- `[1]` selects the 2nd row `[2, 9]`.
- `[1]` selects the 2nd element `9`.

## Exercise 3
```python
original_data = [100, 200, 300]

normalized = original_data.copy()
normalized.remove(300)

print("Original:", original_data)
print("Normalized:", normalized)
```
**Reasoning:** By using `.copy()`, Python creates a brand new list in memory containing the same elements. Now `normalized` points to this new list, while `original_data` points to the old one. Modifying `normalized` no longer destroys `original_data`.
