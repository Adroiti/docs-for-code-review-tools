Pattern: Missing use of `singledispatch`

Issue: -

## Description

`singledispatchmethod` should decorate class/instance methods and not functions. Use `singledispatch` for those cases.

Example of **incorrect** code:

```python
from functools import singledispatchmethod


class Board:
    @singledispatchmethod  # [singledispatchmethod-function]
    @staticmethod
    def convert_position(position):
        pass

    @convert_position.register  # [singledispatchmethod-function]
    @staticmethod
    def _(position: str) -> tuple:
        position_a, position_b = position.split(",")
        return (int(position_a), int(position_b))

    @convert_position.register  # [singledispatchmethod-function]
    @staticmethod
    def _(position: tuple) -> str:
        return f"{position[0]},{position[1]}"
```

Example of **correct** code:

```python
from functools import singledispatchmethod


class Board:
    @singledispatchmethod
    def convert_position(cls, position):
        pass

    @singledispatchmethod
    @classmethod
    def _(cls, position: str) -> tuple:
        position_a, position_b = position.split(",")
        return (int(position_a), int(position_b))

    @singledispatchmethod
    @classmethod
    def _(cls, position: tuple) -> str:
        return f"{position[0]},{position[1]}"
```