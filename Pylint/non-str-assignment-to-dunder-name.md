Pattern: Non-string value assigned to `__name__`

Issue: -

## Description

Ensures that only strings are assigned to `__name__` attributes

Example of **incorrect** code:

```python
class ExampleClass():
    pass
	
ExampleClass.__name__ = 1  # [non-str-assignment-to-dunder-name]	
```

Example of **correct** code:

```python
class ExampleClass():
    pass
	
ExampleClass.__name__ = "test"
```