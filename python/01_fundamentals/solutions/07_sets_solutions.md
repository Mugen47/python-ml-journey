# Topic 7 Solutions: Sets

## Exercise 1
```python
emails = ["a@a.com", "b@b.com", "a@a.com", "c@c.com", "b@b.com"]
unique_emails = set(emails)
print(len(unique_emails)) # 3
```
**Reasoning:** Converting a list to a set automatically removes all duplicates. Then `len()` calculates the total number of items remaining.

## Exercise 2
```python
user_likes = {"The Matrix", "Inception", "Interstellar"}
friend_likes = {"Interstellar", "The Prestige", "The Matrix"}
print(user_likes & friend_likes)
```
**Reasoning:** The `&` operator finds the intersection of two sets. It returns a new set containing only the items present in BOTH sets.

## Exercise 3
```python
unique_ips = set()
unique_ips.add("192.168.1.1")
```
**Reasoning:** In Python, `{}` evaluates to an empty dictionary, not an empty set. A dictionary does not have an `.add()` method, which is why it throws an `AttributeError`. To create an empty set, you MUST use `set()`.
