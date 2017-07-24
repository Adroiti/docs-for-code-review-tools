Pattern: Use of `range()` and `len()` instead of `enumerate()`

Issue: -

## Description

Emitted when code that iterates with `range()` and `len()` is encountered. Such code can be simplified by using the `enumerate()` built-in.


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


## Further Reading

* [PEP 279 - The enumerate() built-in function](https://www.python.org/dev/peps/pep-0279/)
