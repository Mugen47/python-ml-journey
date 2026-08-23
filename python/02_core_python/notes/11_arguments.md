# Topic 11: Arguments (Positional, Keyword, Default)

## 1. What is it?
When you pass data into a function, Python needs to know *which* parameter gets *which* piece of data. Understanding Positional, Keyword, and Default arguments allows you to write incredibly flexible ML functions.

## 2. Positional Arguments (The Default Way)
By default, arguments are mapped to parameters based on their **position** (order).

```python
def describe_model(name, layers):
    print(f"Model: {name}, Layers: {layers}")

# 'ResNet' goes to name, 50 goes to layers
describe_model("ResNet", 50) 
```
*Danger:* If you accidentally swap them (`describe_model(50, "ResNet")`), the function will still run, but your logic might break!

## 3. Keyword Arguments (The Safe Way)
Instead of relying on order, you can explicitly state which parameter gets which value by using the parameter's name. This is called a **keyword argument**.

```python
def describe_model(name, layers):
    print(f"Model: {name}, Layers: {layers}")

# Order doesn't matter anymore!
describe_model(layers=50, name="ResNet") 
```
*Rule:* If you mix positional and keyword arguments, positional arguments **MUST** come first!
`describe_model("ResNet", layers=50)` works.
`describe_model(name="ResNet", 50)` throws a `SyntaxError`.

## 4. Default Arguments (The Flexible Way)
Often in Machine Learning, a function has a setting that is used 99% of the time, but you want to allow the user to change it if they *really* need to. You can provide a **default value** in the function definition.

```python
# 'epochs' defaults to 10 if the user doesn't provide it
def train_model(model_name, epochs=10):
    print(f"Training {model_name} for {epochs} epochs.")

train_model("YOLOv8")              # Uses default: Training YOLOv8 for 10 epochs.
train_model("YOLOv8", epochs=100)  # Overrides default: Training YOLOv8 for 100 epochs.
```

*Rule:* Parameters with default values MUST come **after** parameters without default values in the `def` statement.
`def train(epochs=10, model_name):` throws a `SyntaxError`.

## 5. `*args` and `**kwargs` (The Advanced Magic)
Sometimes you don't know how many arguments the user will pass. 
- `*args` (Arguments): Allows you to pass any number of **positional** arguments. They are packed into a **Tuple**.
- `**kwargs` (Keyword Arguments): Allows you to pass any number of **keyword** arguments. They are packed into a **Dictionary**.

```python
# Using *args
def calculate_total_loss(*losses):
    print(type(losses)) # <class 'tuple'>
    return sum(losses)

print(calculate_total_loss(0.5, 0.2, 0.1, 0.05)) # 0.85

# Using **kwargs
def build_config(**settings):
    print(type(settings)) # <class 'dict'>
    for key, value in settings.items():
        print(f"{key}: {value}")

build_config(learning_rate=0.01, batch_size=32, optimizer="Adam")
```

## 6. ML Connection
When you use a library like `scikit-learn` or `TensorFlow`, functions have dozens of parameters. 
For example: `RandomForestClassifier(n_estimators=100, max_depth=None, random_state=42)`. 
They rely heavily on **Default Arguments** (so you don't have to specify all 20 settings every time) and **Keyword Arguments** (so you know exactly what you are modifying). Furthermore, wrappers around ML models heavily use `**kwargs` to pass arbitrary parameters down to lower-level functions.
