Pattern: Use of `super()` with arguments

Issue: -

## Description

Emitted when calling the `super()` builtin with the current class and instance. On Python 3 these arguments are the default and they can be omitted.

Example of **incorrect** code:

```python
class Test(Foo):
    def __init__(self):
        super(Test, self).__init__()  # [super-with-arguments]
```

Example of **correct** code:

```python
class Test(Foo):
    def __init__(self):
        super().__init__()
```