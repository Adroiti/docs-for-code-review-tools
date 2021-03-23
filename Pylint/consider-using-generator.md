Pattern: Missing use of generator

Issue: -

## Description

If your container can be large using a generator will bring better performance.

Example of **incorrect** code:

```python
list([0 for y in list(range(10))]) # [consider-using-generator]
```

Example of **correct** code:

```python
list(0 for y in list(range(10)))
```