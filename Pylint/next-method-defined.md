Pattern: Use of `next` method

Issue: -

## Description

Used when a `next` method is defined that would be an iterator in Python 2 but is treated as a normal function in Python 3.

Implement a `__next__` method and use `six.Iterator` as a base class or alias `next` to `__next__` instead.

Example of **incorrect** code:

```python
class SomeClass(object):
  def next(self):
	  return 42
```

Example of **correct** code:

```python
class SomeClass(object):
  def __next__(self):
	  return 42
  next = __next__
```
