Pattern: Avoid empty docstrings

Issue: -

## Description

Used when a module, function, class or method has an empty docstring. Provide content for docstring or remove empty docstring to resolve this issue.


Example of **incorrect** code:

```python
def complex(real=0.0, imag=0.0):
    """"""
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

* [PEP 8 - Documentation Strings](https://www.python.org/dev/peps/pep-0008/#documentation-strings)
