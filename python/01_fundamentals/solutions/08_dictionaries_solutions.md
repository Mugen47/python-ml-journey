# Topic 8 Solutions: Dictionaries

## Exercise 1
```python
user_profile = {
    "name": "Sarah",
    "email": "sarah@example.com"
}
phone = user_profile.get("phone", "No phone provided")
print(phone)
```
**Reasoning:** `.get("phone", "No phone provided")` checks if the key `"phone"` exists. Since it doesn't, it safely returns the fallback string instead of crashing the program with a `KeyError`.

## Exercise 2
```python
default_config = {"lr": 0.01, "batch_size": 32, "epochs": 100}
user_config = {"batch_size": 64, "optimizer": "Adam"}
default_config.update(user_config)
print(default_config)
```
**Reasoning:** The `.update()` method merges `user_config` into `default_config`. Existing keys (like `batch_size`) are overwritten, and new keys (like `optimizer`) are added.

## Exercise 3
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
print(api_response["data"]["forecast"][1]["conditions"])
```
**Reasoning:** 
- `api_response["data"]` gets the inner dictionary.
- `["forecast"]` gets the list of days.
- `[1]` gets the second item in that list (Tuesday's dictionary).
- `["conditions"]` gets the value `"Rain"`.
