Pattern: Missing documentation

Issue: -

## Description

Docstrings help you remember the intention of a class. This is especially important as your codebase grows and it becomes harder to remember the implementation details of each object. Other developers will also have it easier to understand your code.

Example of **incorrect** code:

```python
def complex(real=0.0, imag=0.0):
    if imag == 0.0 and real == 0.0:
        return complex_zero
    ...
```

Example of **correct** code:

```python
def complex(real=0.0, imag=0.0):
    """Form a complex number.

    Keyword arguments:
    real -- the real part (default 0.0)
    imag -- the imaginary part (default 0.0)
    """
    if imag == 0.0 and real == 0.0:
        return complex_zero
    ...
```

## Further Reading

* [Related link(s) to get more details or background on issue pattern](https://www.python.org)
