Pattern: Use of `format()` on non-`str` object

Issue: -

## Description

Emitted when `format()` is not called on `str` object. This might not be what you intended to do.

Example of **incorrect** code:

```python
print("value: {}").format(123)
```

Example of **correct** code:

```python
print("value: {}".format(123))
```