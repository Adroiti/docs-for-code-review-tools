Pattern: Possibly using variable before assignment

Issue: -

## Description

Emitted when a local variable is accessed before its assignment took place in both branches of an `if`/`else` switch.


Example of **incorrect** code:

```python
def check_lunchbox(items: list[str]):
    if not items:
        empty = True
    print(empty)  # [possibly-used-before-assignment]
```

Example of **correct** code:
```python
def check_lunchbox(items: list[str]):
    empty = False
    if not items:
        empty = True
    print(empty)
```
