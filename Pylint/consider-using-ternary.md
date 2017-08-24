Pattern: Use of old ternary syntax

Issue: -

## Description

Before Python 2.5, a common idiom for ternary was to use logical operators:

```python
[expression] and [on_true] or [on_false]
```

However, this idiom is unsafe, as it can give wrong results when `on_true` has a false boolean value. Therefore, it is always better to use the `... if ... else ...` form:

```python
x, y = 50, 25
small = x if x < y else y
```


## Further Reading

* [ Python Frequently Asked Questions - Is there an equivalent of C’s ”?:” ternary operator?](https://docs.python.org/3/faq/programming.html#is-there-an-equivalent-of-c-s-ternary-operator)
