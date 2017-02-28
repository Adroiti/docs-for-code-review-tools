Pattern: Avoid unidiomatic typecheck

Issue: -

## Description

This rule enforces `PEP 8` recommendation to always use `isinstance()` instead of comparing types directly. Even though latter code is correct, it's less readable and is not considered 'pythonic'.


Example of **incorrect** code:

```python
if type(obj) is type(1):
```

Example of **correct** code:

```python
if isinstance(obj, int):
```

## Further Reading

* [PEP 8 - Programming Recommendations](https://www.python.org/dev/peps/pep-0008/#programming-recommendations)
