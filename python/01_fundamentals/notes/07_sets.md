# Topic 7: Sets

## 1. What is it?
A set in Python is an unordered, mutable collection of **unique** items. You can think of it exactly like a mathematical set.

## 2. Why does it exist?
Sets are incredibly powerful for two main reasons:
1. **Deduplication:** The fastest way to remove duplicates from a list is to convert it into a set.
2. **Membership Testing:** Because sets use a data structure called a "hash table" under the hood, checking if an item exists in a set (e.g., `if "apple" in my_set:`) is almost instantly fast, even if the set has millions of items. Doing this with a list is incredibly slow.

## 3. How does it work?
Sets are created using curly braces `{}` or the `set()` function. Because they are unordered, **they do not support indexing or slicing** (you cannot do `my_set[0]`).

## 4. Syntax and Core Methods
```python
# Creating sets
unique_numbers = {1, 2, 3, 4, 4, 4, 5}
print(unique_numbers)  # {1, 2, 3, 4, 5} -> Duplicates are instantly removed!

# Creating an empty set (You MUST use set(), because {} creates an empty dictionary!)
empty_set = set()
empty_dict = {}
```

### Essential Set Methods
- `.add(item)`: Adds an item to the set.
- `.remove(item)`: Removes an item (throws an error if it doesn't exist).
- `.discard(item)`: Removes an item (does NOTHING if it doesn't exist - safer!).

## 5. Basic Examples (Mathematical Operations)
Sets shine when you need to compare two groups of data.
```python
group_a = {"apple", "banana", "cherry"}
group_b = {"cherry", "date", "elderberry"}

# Union (All unique elements from both)
print(group_a | group_b) # {'apple', 'banana', 'cherry', 'date', 'elderberry'}

# Intersection (Only elements present in BOTH)
print(group_a & group_b) # {'cherry'}

# Difference (Elements in A, but NOT in B)
print(group_a - group_b) # {'apple', 'banana'}
```

## 6. Intermediate Examples (Fast Membership Testing)
If you have a massive dataset of a million user IDs and you want to check if a specific user is in it, use a set, not a list.
```python
allowed_users = ["user1", "user2", "user3"] # ... imagine 1,000,000 items

# Slow: Python checks item by item from start to finish
if "user999" in allowed_users: 
    pass

allowed_set = set(allowed_users)

# Lightning Fast: Python instantly knows via a hash lookup
if "user999" in allowed_set:
    pass
```

## 7. Hard Examples (The Hashable Requirement)
Sets can only store **immutable** (hashable) items. This means you can put strings, integers, and tuples inside a set, but you CANNOT put a list or a dictionary inside a set!
```python
valid_set = {1, "hello", (10, 20)} # Works perfectly

# invalid_set = {1, "hello", [10, 20]}  <--- TypeError: unhashable type: 'list'
```

## 8. ML Connection
In Natural Language Processing (NLP), you often need to find the "vocabulary" of a document—the unique words used. If a document has 10,000 words, you simply run `vocab = set(words_list)` to instantly get the unique words. Sets are also used to quickly identify overlapping features between datasets.
