Pattern: Prefer static functions over instance methods

Issue: Instance method could be a static function

## Description

The method does not make use of the class instance it gets passed. For clarity, it should be declared as a static method using the `@staticmethod` decorator.


Example of **incorrect** code:

```python
class Foo(object):
    ...
    def bar(self, baz):
        ...
        return llama
```

Example of **correct** code:

```python
class Foo(object):
    ...
    @staticmethod
    def bar(cls, baz):
        ...
        return llama
```

## Further Reading

* [Stack Overflow - What is the difference between @staticmethod and @classmethod in Python?](http://stackoverflow.com/questions/136097/what-is-the-difference-between-staticmethod-and-classmethod-in-python)
