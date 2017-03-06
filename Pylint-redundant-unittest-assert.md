Pattern: Redundant unit test assert

Issue: -

## Description

The first argument of `assertTrue` and `assertFalse` is a condition which should evaluate to `True` or `False`. If a constant is passed as parameter, that condition will be always `True` thus making the assert redundant.


Example of **incorrect** code:

```python
class Tests(unittest.TestCase):
    def test_something(self):
        self.assertTrue(1)
```

Example of **correct** code:

```python
class Tests(unittest.TestCase):
    def test_something(self):
        self.assertTrue('bar'.isupper())
```

## Further Reading

* [The Python Standard Library - assertTrue](https://docs.python.org/2/library/unittest.html#unittest.TestCase.assertTrue)
