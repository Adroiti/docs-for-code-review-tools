Pattern: Member accessed before definition

Issue: -

## Description

If class member is used before definition, a runtime error will be raised. Define it first to resolve this issue.


Example of **incorrect** code:

```python
class Test:
    def __init__(self):
        print(self.name)  # name is not yet defined
        self.name = "test"
```

Example of **correct** code:

```python
class Test:
    def __init__(self):
        self.name = "test"
        print(self.name)
```

## Further Reading

* [Pylint - E0203](http://pylint-messages.wikidot.com/messages:e0203)
