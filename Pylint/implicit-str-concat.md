Pattern: Implicitly concatenated string literal 

Issue: -

## Description

String literals are implicitly concatenated in a literal iterable definition.


Example of **incorrect** code:

```python
TEST_LIST = ['a' 'b']  # [implicit-str-concat]
```

Example of **correct** code:

```python
# No warning for bytes
TEST_LIST = [b'A' b'B']
```