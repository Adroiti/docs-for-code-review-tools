Pattern: Pointless string statement

Issue: -

## Description

Used when a string is used as a statement having no effect. This may lead to confusion by readers and increased code size. You can ignore this issue it if you're using those strings as documentation, instead of comments.


Example of **incorrect** code:

```python
class Test(object):
    def __init__(self):
        val = 0
        """ Invalid attribute docstring """
        self.val = val
```

Example of **correct** code:

```python
class Test(object):
    def __init__(self):
        """ Valid attribute docstring """
        val = 0
        self.val = val
```
