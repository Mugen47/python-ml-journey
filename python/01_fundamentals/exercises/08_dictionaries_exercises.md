# Topic 8 Exercises: Dictionaries

## Exercise 1: Safe Access (Level 1)
You are pulling user profiles from a database. Some users have a `"phone"` key, and some do not.
```python
user_profile = {
    "name": "Sarah",
    "email": "sarah@example.com"
}
```
Write a single line of code that attempts to retrieve the user's phone number. If it doesn't exist, it should return the string `"No phone number provided"`. Save this to a variable called `phone` and print it.

## Exercise 2: Dictionary Updating (Level 2)
You have a set of default ML hyperparameters, but the user has provided some custom overrides.
```python
default_config = {"lr": 0.01, "batch_size": 32, "epochs": 100}
user_config = {"batch_size": 64, "optimizer": "Adam"}
```
Using a single dictionary method on `default_config`, merge the `user_config` into it so that `batch_size` gets updated to 64, `optimizer` gets added, and the rest stay the same. Print `default_config` to verify.

## Exercise 3: Nested Extraction (Level 3)
You sent a request to a weather API and received this complex nested dictionary containing JSON data:
```python
api_response = {
    "status": "success",
    "data": {
        "location": "New York",
        "forecast": [
            {"day": "Monday", "temp": 72, "conditions": "Sunny"},
            {"day": "Tuesday", "temp": 68, "conditions": "Rain"}
        ]
    }
}
```
Using chained indexing (combining dictionary keys and list indices), write a single line of code that extracts and prints the word `"Rain"`.
