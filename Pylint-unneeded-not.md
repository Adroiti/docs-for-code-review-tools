Pattern: Simplify `if not`

Issue: -

## Description


You can simplify certain boolean expressions containing negation to not use it making the code more succinct and clear.


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
