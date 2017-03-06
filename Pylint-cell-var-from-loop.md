Pattern: Avoid defining closure variables in loops

Issue: -

## Description

A variable used in a closure is defined in a loop. This will result in all closures using the same value for the closed-over variable.


Example of **incorrect** code:

```python
def bad_case():
    """Closing over a loop variable."""
    lst = []
    for i in range(10):
        print(i)
        lst.append(lambda: i)  # [cell-var-from-loop]
```

Example of **correct** code:
```python
def good_case():
    """No problems here."""
    lst = []
    for i in range(10):
        lst.append(i)
```
