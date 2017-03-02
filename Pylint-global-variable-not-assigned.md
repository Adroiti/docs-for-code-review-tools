Pattern: Global variable is not assigned

Issue: -

## Description

Used when a variable is defined through the `global` statement but no assignment to this variable is done.


Example of **incorrect** code:

```python
def func():
    global name
```

Example of **correct** code:

```python
def func():
    global name
    mouse = "modified"
```

## Further Reading

* [The Python Language Reference - The global statement](https://docs.python.org/2/reference/simple_stmts.html#the-global-statement)
