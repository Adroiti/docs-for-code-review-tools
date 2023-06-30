Pattern: Undefined variable

Issue: -

## Description

Used when an undefined variable is accessed. Such variables can be added to the `additional-builtins` option so Pylint will consider them as defined.


Example of **incorrect** code:

```python
class Self(object):
    """ Detect when using the same name inside the class scope. """
    obj = Self # [undefined-variable]
```

Example of **correct** code:

```python
class Self1(object):
    """ No error should be raised here. """

    def test(self):
        """ empty """
        return Self1
```
