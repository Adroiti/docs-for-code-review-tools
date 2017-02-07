Pattern: Consider using enumerate

Issue: -

## Description

Emitted when code that iterates with `range()` and `len()` is encountered. Such code can be simplified by using the `enumerate()` builtin.

A common idiom to change every element of a list looks like this: 

```python
for i in range(len(L)):
    item = L[i]
    # ... compute some result based on item ...
    L[i] = result
```

This can be rewritten using `enumerate()` as: 

```python
for i, item in enumerate(L):
    # ... compute some result based on item ...
    L[i] = result
```