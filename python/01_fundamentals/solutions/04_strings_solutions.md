# Topic 4 Solutions: Strings and Manipulation

## Exercise 1
```python
file_path = "/data/images/dataset_2024.csv"
print(file_path[-16:])
```
**Reasoning:** Negative indexing counts from the end of the string. `dataset_2024.csv` is exactly 16 characters long. By taking `[-16:]`, we always grab the last 16 characters, ensuring robustness even if the folder path length changes.

## Exercise 2
```python
raw_tweet = "   Python is AWESOME for Machine Learning!!!   \n"
clean_tweet = raw_tweet.strip().lower().replace("!!!", "")
print(clean_tweet)
```
**Reasoning:** We chain string methods. `.strip()` removes the leading/trailing spaces and newline. `.lower()` makes it entirely lowercase. Finally, `.replace("!!!", "")` replaces the exclamation marks with nothing, effectively deleting them.

## Exercise 3
```python
epoch = 5
loss = 0.0345678
val_accuracy = 0.892
print(f"[Epoch {epoch:02d}] Training Loss: {loss:.3f} | Validation Acc: {val_accuracy:.1%}")
```
**Reasoning:** Using the Format Specification Mini-Language inside f-strings:
- `:02d` pads the integer `epoch` to 2 digits with a leading zero.
- `:.3f` rounds the float `loss` to 3 decimal places.
- `:.1%` converts `val_accuracy` to a percentage and rounds it to 1 decimal place.
