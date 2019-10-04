Pattern: Missing use of `.items()` for dict iteration

Issue: -

## Description

Emitted when trying to iterate through a dictionary without calling `.items()` method.

Example of **incorrect** code:

```python
for k, v in d:  # [dict-iter-missing-items]
    pass
```

Example of **correct** code:

```python
for k, v in d.items():
    pass
```
