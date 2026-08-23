# Topic 7 Exercises: Sets

## Exercise 1: Deduplication (Level 1)
You scraped data from a website, but the scraper malfunctioned and collected duplicate emails.
```python
emails = ["a@a.com", "b@b.com", "a@a.com", "c@c.com", "b@b.com"]
```
Write the Python code to convert this list into a collection of unique emails, and then print how many unique emails exist (using the `len()` function).

## Exercise 2: Intersection (Level 2)
You are an ML engineer building a recommendation system. You want to recommend a movie to a user based on what their friend liked.
```python
user_likes = {"The Matrix", "Inception", "Interstellar"}
friend_likes = {"Interstellar", "The Prestige", "The Matrix"}
```
Write a single line of code to print the movies that **both** users liked.

## Exercise 3: The Empty Set Trap (Level 2)
Your junior colleague wrote the following code to initialize an empty set for storing unique IP addresses, but they are getting an `AttributeError` when they try to use `.add()`.
```python
unique_ips = {}
unique_ips.add("192.168.1.1")
```
Explain exactly why this error is happening and fix the code so it works properly.
