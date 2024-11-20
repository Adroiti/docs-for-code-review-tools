Pattern: Missing direct use of `yield from`

Issue: -

## Description

Use `yield from` directly instead of yielding each element one by one.

Yielding directly from the iterator is faster and arguably cleaner code than yielding each element one by one in the loop.


Example of **incorrect** code:

```python
def bad_yield_from(generator):
    for item in generator:  # [use-yield-from]
        yield item
```

Example of **correct** code:
```python
def good_yield_from(generator):
    yield from generator
```
