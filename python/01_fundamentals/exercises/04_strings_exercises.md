# Topic 4 Exercises: Strings and Manipulation

## Exercise 1: String Slicing (Level 2)
You are given a string representing a file path containing a dataset:
`file_path = "/data/images/dataset_2024.csv"`

Using **only string slicing** (do not use `.split()`), extract the word `"dataset_2024.csv"` from the string. Try to do it using negative indexing so it would work even if the folder names change, as long as the file name is the same length.

## Exercise 2: Data Cleaning (Level 3)
In NLP (Natural Language Processing), you often receive messy, inconsistent text data from users. 

Write a script in your `practice.py` that takes the following raw string:
`raw_tweet = "   Python is AWESOME for Machine Learning!!!   \n"`

Chain string methods together to achieve the following clean format:
`"python is awesome for machine learning"`
*(Notice that whitespace, newlines, and the exclamation marks are gone, and it is entirely lowercase).*

## Exercise 3: F-Strings and Formatting (Level 4)
You have trained an ML model and need to print the log output. 
```python
epoch = 5
loss = 0.0345678
val_accuracy = 0.892
```
Using a **single f-string**, print the exact following message:
`[Epoch 05] Training Loss: 0.035 | Validation Acc: 89.2%`

*Hint: Look up how to pad integers with zeros, and how to format decimals and percentages inside f-strings!*
