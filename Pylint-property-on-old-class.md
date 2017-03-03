Pattern: Property on old class

Issue: -

## Description

Used when Pylint detects the use of the built-in `property()` on an old style class while this is relying on new style class features. This message can't be emitted when using Python >= 3.0.


Example of **incorrect** code:

```python
class OldStyleClass:  # <3.0:[old-style-class]
    """bad usage"""
    method = property(getter, doc='hop')  # <3.0:[property-on-old-class]

    def __init__(self):
        pass
```

Example of **correct** code:

```python
class CorrectClass(object):
    """correct usage"""
    method = property(getter, doc='hop')
```
