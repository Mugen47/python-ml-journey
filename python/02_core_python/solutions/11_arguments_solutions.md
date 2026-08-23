# Topic 11 Solutions: Arguments

## Exercise 1
```python
def setup_server(host, port=8080, debug=False):
    print(f"Server starting on {host}:{port} | Debug mode: {debug}")

setup_server("localhost")
setup_server("192.168.1.1", 9000)
setup_server("production.com", debug=True)
```
**Reasoning:** Default arguments make the function flexible. The first call uses the defaults. The second call overrides the `port` using positional order. The third call skips over `port` and explicitly overrides `debug` using a keyword argument.

## Exercise 2
```python
def train_network(learning_rate, batch_size, epochs, momentum):
    print(f"LR: {learning_rate}, Batch: {batch_size}, Epochs: {epochs}, Momentum: {momentum}")

train_network(learning_rate=0.001, batch_size=64, epochs=100, momentum=0.9)
```
**Reasoning:** When a function takes many numerical parameters, passing them as positional arguments is very confusing to read. By enforcing keyword arguments on the function call, it is immediately obvious what each number represents.

## Exercise 3
```python
def average_scores(*args):
    return sum(args) / len(args)

print(average_scores(85, 90, 95, 100)) # 92.5
```
**Reasoning:** The `*args` syntax captures all the individual positional arguments and packs them into a single tuple called `args`. We can then use built-in functions like `sum()` and `len()` on that tuple to calculate the average.
