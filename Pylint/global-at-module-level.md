Pattern: Unnecessary `global` statement at module level

Issue: -

## Description

Using `global` makes sense only within nested scopes of a given module. It has no effect if used at the module level.


Example of **incorrect** code:

```python
global name
name = "test"

def func():
    global name
```

Example of **correct** code:

```python
def func():
    global name
    name = "test"
```

## Further Reading

* [The Python Language Reference - The global statement](https://docs.python.org/2/reference/simple_stmts.html#the-global-statement)
