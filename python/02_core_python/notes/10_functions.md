# Topic 10: Functions (Definitions, Returns)

## 1. What is it?
A function is a reusable block of code that performs a specific task. You "define" it once, and then you can "call" it as many times as you want.

## 2. Why does it exist?
Without functions, you would have to copy and paste the same block of code every time you wanted to do something twice. This violates a core programming principle called **DRY** (Don't Repeat Yourself).
In Machine Learning, functions are used to:
- Load data (`load_dataset()`)
- Preprocess data (`normalize_image(image)`)
- Train models (`train_step(model, data, labels)`)
- Calculate metrics (`calculate_accuracy(predictions, truths)`)

## 3. How does it work?
You define a function using the `def` keyword, followed by the function name, parentheses `()`, and a colon `:`. Everything indented beneath it belongs to the function.

```python
# 1. Defining the function
def greet_user():
    print("Welcome to the Machine Learning pipeline!")

# 2. Calling the function
greet_user()
```

## 4. Inputs (Parameters/Arguments)
Functions are most powerful when they can accept data, process it, and do something dynamic. The variables listed in the definition are called **parameters**. The actual data you pass in are called **arguments**.

```python
# 'name' is the parameter
def greet(name):
    print(f"Hello, {name}!")

greet("Alice") # 'Alice' is the argument
greet("Bob")
```

## 5. Outputs (The `return` Statement)
Printing data is great for humans, but useless for the computer. If you want a function to calculate a value and *hand it back* to you so you can use it later, you must use the `return` keyword. 

**Important:** Once a function hits a `return` statement, it exits immediately. No code below the `return` will run!

```python
def multiply(a, b):
    result = a * b
    return result
    print("This will never print!") # Unreachable code

# Capturing the returned value
answer = multiply(5, 10)
print(answer) # 50
```

## 6. Returning Multiple Values (The Tuple Secret)
In many languages, a function can only return one thing. In Python, you can return multiple values separated by commas. Under the hood, Python secretly packages them into a **Tuple**!

```python
def get_model_stats():
    accuracy = 0.95
    loss = 0.05
    time_taken = 120
    # Returning 3 values!
    return accuracy, loss, time_taken

# We use Tuple Unpacking to catch them!
acc, lss, time = get_model_stats()
print(f"Accuracy: {acc}, Loss: {lss}")
```

## 7. ML Connection
When you write a custom neural network layer or an evaluation script, you will always wrap it in a function. For example, a standard evaluation function in PyTorch looks exactly like this structurally:

```python
def evaluate_model(model, test_data):
    # ... logic to run the model ...
    final_accuracy = 0.88
    final_loss = 0.21
    
    return final_accuracy, final_loss
```
