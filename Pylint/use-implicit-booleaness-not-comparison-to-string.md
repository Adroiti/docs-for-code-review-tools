Pattern: Use of empty string in boolean context

Issue: -

## Description

Empty string are considered false in a boolean context. Following this check blindly in weakly typed codebase can create hard to debug issues. If the value can be something else that is falsey but not a string (for example `None`, an empty sequence, or `0`) the code will not be equivalent.


Example of **incorrect** code:

```python
def important_string_manipulation(x: str, y: str) -> None:
    if x == "":  # [use-implicit-booleaness-not-comparison-to-string]
        print("x is an empty string")

    if y != "":  # [use-implicit-booleaness-not-comparison-to-string]
        print("y is not an empty string")
```

Example of **correct** code:

```python
def important_string_manipulation(x: str, y: str) -> None:
    if not x:
        print("x is an empty string")

    if y:
        print("y is not an empty string")
```
