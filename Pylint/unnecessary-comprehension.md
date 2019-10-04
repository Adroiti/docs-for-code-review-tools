Pattern: Unnecessary comprehension

Issue: -

## Description

Emitted when pylint finds list-, set- or dict-comprehensions, that are unnecessary and can be rewritten with the list-, set- or dict-constructors.

Example of **incorrect** code:

```python
[x for x in iterable]
```

Example of **correct** code:

```python
list(iterable)
```