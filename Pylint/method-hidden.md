Pattern: Use of hidden method via attribute

Issue: -

## Description

If method and attribute have the same name, Python prioritizes attribute making the method effectively hidden. This may lead to confusion as `TypeError` will be raised at runtime. Modify the code so that method and attribute names are unique.


Example of **incorrect** code:

```python
class Felinae:
    def __init__(self, name):
        self.name = name
        self.family = "Felidae"

    # hidden
    def family(self):
        return self.name;
```

Example of **correct** code:

```python
class Felinae:
    def __init__(self, name):
        self.name = name
        self.family = "Felidae"
    # removed family method
```
