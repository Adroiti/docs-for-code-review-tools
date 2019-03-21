Pattern: Invalid exception operation

Issue: -

## Description

Used when an operation is done against an exception, but the operation is not valid for the exception in question. Usually emitted when having binary operations between exceptions in except handlers.


Example of **incorrect** code:

```python
try:
    1/0
except (ValueError | TypeError): # [wrong-exception-operation]
    pass
```