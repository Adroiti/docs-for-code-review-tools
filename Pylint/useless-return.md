Pattern: Useless `return`

Issue: -

## Description

Emitted when a single `return` or `return None` statement is found at the end of function or method definition. This statement can safely be removed because Python will implicitly return `None`.

Example of **incorrect** code:

```python

def test():
    print('---- testing ---')
    return
```

Example of **correct** code:

```python
def test():
    print('---- testing ---')
```