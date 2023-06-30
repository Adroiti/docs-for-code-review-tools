Pattern: `__init__` not called from derived class

Issue: -

## Description

Derived class should always call it's parent's `__init__` method if available. Otherwise this could lead to partially initialized instance state causing unexpected behavior.


Example of **incorrect** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

class Puma(Felinae):
    def __init__(self, subfamily, genus):
        self.genus = genus
```

Example of **correct** code:

```python
class Felinae(object):
    def __init__(self, subfamily):
        self.subfamily = subfamily

class Puma(Felinae):
    def __init__(self, subfamily, genus):
        super(Puma, self).__init__(subfamily)
        self.genus = genus
```
