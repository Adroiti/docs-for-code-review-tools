Pattern: Missing use of `singledispatchmethod`

Issue: -

## Description

`singledispatch` should decorate functions and not class/instance methods. Use `singledispatchmethod` for those cases.

Example of **incorrect** code:

```python
from functools import singledispatch


class Board:
    @singledispatch  # [singledispatch-method]
    @classmethod
    def convert_position(cls, position):
        pass

    @convert_position.register  # [singledispatch-method]
    @classmethod
    def _(cls, position: str) -> tuple:
        position_a, position_b = position.split(",")
        return (int(position_a), int(position_b))

    @convert_position.register  # [singledispatch-method]
    @classmethod
    def _(cls, position: tuple) -> str:
        return f"{position[0]},{position[1]}"
```

Example of **correct** code:

```python
from functools import singledispatch


class Board:
    @singledispatch
    @staticmethod
    def convert_position(position):
        pass

    @convert_position.register
    @staticmethod
    def _(position: str) -> tuple:
        position_a, position_b = position.split(",")
        return (int(position_a), int(position_b))

    @convert_position.register
    @staticmethod
    def _(position: tuple) -> str:
        return f"{position[0]},{position[1]}"
```

