# Topic 4: Strings and Manipulation

## 1. What is it?
A string (`str`) in Python is a sequence of characters used to represent text. Strings are **immutable**, meaning once created, they cannot be changed in place. Any operation that modifies a string actually creates a brand new string.

## 2. Why does it exist?
In Machine Learning and Data Science, a massive portion of data is unstructured text (e.g., medical records, tweets, reviews, log files). To perform Natural Language Processing (NLP) or even basic data cleaning (like stripping whitespace from a CSV column), you must know how to manipulate strings efficiently.

## 3. How does it work?
Strings are created by enclosing characters in single quotes `''`, double quotes `""`, or triple quotes `''' '''` (for multi-line strings). Because they are sequences, you can access individual characters using an index (starting at 0) and slice them to extract substrings.

## 4. Syntax and Methods
```python
text = "Machine Learning"

# Indexing (Accessing a single character)
print(text[0])   # 'M'
print(text[-1])  # 'g' (negative indices count from the end)

# Slicing [start:stop:step] (Stop is exclusive)
print(text[0:7]) # 'Machine'
print(text[:7])  # 'Machine' (implicit start at 0)
print(text[8:])  # 'Learning' (implicit end)
print(text[::-1])# 'gninraeL enihcaM' (reverses the string!)
```

### Essential String Methods
- `.lower()` / `.upper()`: Changes case.
- `.strip()`: Removes leading and trailing whitespace.
- `.split(delimiter)`: Splits the string into a list based on a delimiter.
- `.replace(old, new)`: Replaces substrings.
- `.join(list)`: Joins a list of strings into one string.

## 5. Basic Examples
```python
# Cleaning dirty data
raw_data = "   user@email.com   \n"
clean_data = raw_data.strip().lower()
print(clean_data)  # 'user@email.com'

# Splitting CSV data
csv_line = "apple,banana,cherry"
fruits = csv_line.split(",")
print(fruits)  # ['apple', 'banana', 'cherry']
```

## 6. Intermediate Examples (F-Strings & Formatting)
F-strings (formatted string literals) are the modern, readable way to inject variables into strings.

### The Format Specification Mini-Language
When inside an f-string's curly braces `{}`, anything to the **left** of the colon `:` is the variable, and anything to the **right** is the formatting rule.

- **`{epoch:02d}` (Integer Padding)**:
  - `0`: Pad the empty space with zeros.
  - `2`: The number must take up at least 2 characters.
  - `d`: Decimal integer (treat strictly as a whole number).
  - *Example*: `5` becomes `05`.
  
- **`{loss:.3f}` (Float Rounding)**:
  - `.3`: Round the number to exactly 3 decimal places.
  - `f`: Fixed-point number (a float).
  - *Example*: `0.03456` becomes `0.035`.
  
- **`{accuracy:.1%}` (Percentage Conversion)**:
  - `.1`: Round to 1 decimal place.
  - `%`: Multiply the float by 100 and add a `%` sign.
  - *Example*: `0.892` becomes `89.2%`.

```python
accuracy = 0.9456
model_name = "RandomForest"

# Using f-strings to format to 2 decimal places
print(f"The {model_name} model achieved an accuracy of {accuracy:.2f}.")
# Output: The RandomForest model achieved an accuracy of 0.95.
```

## 7. Hard Examples (Immutability in Action)
Because strings are immutable, beginners often make this mistake:
```python
text = "hello"
text.replace("h", "j")
print(text)  # Still "hello"! The replacement was lost.

# Correct way:
text = text.replace("h", "j")
print(text)  # "jello"
```

## 8. Common Mistakes
1. Trying to change a string character directly: `text[0] = 'X'` will throw a `TypeError: 'str' object does not support item assignment`.
2. Forgetting that `.strip()` does not remove spaces *inside* the string, only at the edges.

## 9. ML Connection
When preparing text data for an ML model (like a text classifier or an LLM), you usually build a **preprocessing pipeline**. This involves converting all text to lowercase, removing punctuation via `.replace()`, and splitting sentences into individual words via `.split()`. If your string manipulation is slow or incorrect, your entire ML training pipeline will suffer.
