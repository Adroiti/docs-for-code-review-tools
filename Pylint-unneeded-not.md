Pattern: Use of verbose boolean negation

Issue: -

## Description


You can simplify certain boolean expressions containing negation to not use it. This change will make the code more succinct and clear to the readers.


Example of **incorrect** code:
```python
def do_stuff():
    someint = 5
    if not someint > 3:
        return False
    else:
        return True
```

Example of **correct** code:
```python
def do_stuff():
    someint = 5
    if someint <= 3:
        return False
    else:
        return True
```
