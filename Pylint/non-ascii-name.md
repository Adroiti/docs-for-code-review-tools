Pattern: Use of non-ASCII name

Issue: -

## Description

Used when the name contains at least one non-ASCII unicode character.

Example of **incorrect** code:

```python
def úóíéá(): # [non-ascii-name]
    """test"""
```

Example of **correct** code:

```python
def sampleMethod():
    """test"""
```