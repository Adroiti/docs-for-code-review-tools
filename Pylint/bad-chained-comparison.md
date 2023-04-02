Pattern: Bad chained comparison

Issue: -

## Description

Used when there is a chained comparison where one expression is part of two comparisons that belong to different semantic groups (`<` does not mean the same thing as `is`, chaining them in `0 < x is None` is probably a mistake).

Example of **incorrect** code:

```python
def xor_check(*, left=None, right=None):
    if left is None != right is None:  # [bad-chained-comparison]
        raise ValueError('Either both left= and right= need to be provided or none should.')
```

Example of **correct** code:

```python
def xor_check(*, left=None, right=None):
    if (left is None) != (right is None):
        raise ValueError('Either both left= and right= need to be provided or none should.')
```