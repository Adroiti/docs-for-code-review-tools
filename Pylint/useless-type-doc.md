Pattern: Useless ignored parameter type documentation

Issue: -

## Description

Please remove the ignored parameter type documentation.

Example of **incorrect** code:

```python
# +1: [useless-type-doc,useless-param-doc]
def function_useless_doc(public_param: int, _some_private_param: bool = False) -> None:
    """does things

    Args:
        public_param: an ordinary parameter
        _some_private_param (bool): private param

    """
    for _ in range(public_param):
        ...
    if _some_private_param:
        ...
    else:
        ...
```

Example of **correct** code:

```python
def function_ok(_new: str) -> str:
    """We're speaking about _new without really documenting it.

    :return: comment
    """
    return ""
```