Pattern: Useless ignored parameter documentation

Issue: -

## Description

Please remove the ignored parameter documentation.

Example of **incorrect** code:

```python
def even_test():
    for i in range(10):
        if i % 2:
            print("number is even")
    else:  # [useless-else-on-loop]
        print("list is empty")
```

Example of **correct** code:

```python
def smarter_test(_new: str) -> str:
    """We're speaking about _new without really documenting it.

    :return: comment
    """
    return ""
```
