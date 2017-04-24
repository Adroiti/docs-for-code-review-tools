Pattern: Name is used prior to global declaration
Issue: -

## Description

Emitted when a name is used prior a global declaration which results in an error since Python 3.6.


Example of **incorrect** code:

```python
CONST = 1

def test():
    CONST

    global CONST
```

Example of **correct** code:

```python
```python
CONST = 1

def test():
    global CONST
    CONST
```
