Pattern: Misuse of positional-only arguments

Issue: -

## Description

Emitted when positional-only arguments have been passed as keyword arguments. Remove the keywords for the affected arguments in the function call.

Example of **incorrect** code:

```python
def cube(n, /):
    """Takes in a number n, returns the cube of n"""
    return n**3

cube(n=2) # [positional-only-arguments-expected]
```

Example of **correct** code:

```python
def cube(n, /):
    """Takes in a number n, returns the cube of n"""
    return n**3

cube(2)
```

