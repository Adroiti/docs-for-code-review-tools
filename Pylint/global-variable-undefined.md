Pattern: Global variable not defined in the module scope

Issue: -

## Description

Used when a variable is defined through the `global` statement but the variable is not defined in the module scope.


Example of **incorrect** code:
```python
def define_constant():
    global SOMEVAR
    SOMEVAR = 2
```

Example of **correct** code:
```python
SOMEVAR = 1

def fix_contant(value):
    SOMEVAR = value
```

## Further Reading

* [ Python Frequently Asked Questions - What are the rules for local and global variables in Python?](https://docs.python.org/2/faq/programming.html#what-are-the-rules-for-local-and-global-variables-in-python)
